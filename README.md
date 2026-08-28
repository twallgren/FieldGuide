# Field Guide

Scored evaluations of AI-engineering techniques.
Published at **fieldguide.taylorwallgren.com**.

A living reference, not a blog. Entries are revised as evidence arrives,
and each carries the history of what its score used to be and why it
changed.

Every technique is scored on four signed deltas against a stated baseline,
carries an explicit confidence level, records the sources that disagree,
and is allowed to conclude that it did not earn its place.

## Structure

```
index.html          the method + the index
techniques/         one file per technique, maintained over time
style.css           design tokens + components
CNAME               fieldguide.taylorwallgren.com
```

No build step. Edit HTML, commit, push.

## Deploy

1. Push to a GitHub repo (any name — the custom domain does the work).
2. Settings -> Pages: source = deploy from branch, `main`, `/ (root)`.
3. Settings -> Pages -> Custom domain: `fieldguide.taylorwallgren.com`
   (the `CNAME` file is already committed).
4. DNS at the registrar — one record:

   ```
   CNAME   fieldguide   twallgren.github.io
   ```

5. Once DNS propagates, tick **Enforce HTTPS**.

This lives on a subdomain rather than a path under the apex so it can move
to its own domain later with a DNS change and a one-line `CNAME` edit —
no migration, no broken structure.

## Adding or revising an entry

Copy `techniques/multi-agent-debate.html` and replace, in order:

- `<title>` and the `<meta name="description">`
- the kicker: class (`no-regret` / `trade` / `dial`), date, and the
  two-tone bar (`--neg`/`--pos` split for a trade)
- title and standfirst
- the confidence box: fill 1, 2 or 3 meter segments and match the
  `.on` classes on the scale labels underneath
- `.baseline` — always state it, always before any number
- the four `.delta-card`s, and their `.track` fills
- `.meta-row` (dial, effort, levers, mechanisms)
- `.when` — the regime it is correct under, and the one it is not
- the `.arg` blocks, one per axis
- the `.plog__entry` list, tagged `challenges` or `nuances`

Then add a `.trow` to the index in `index.html` with its **Updated** stamp,
and update the class counts on the three `.class-card`s.

**When revising an existing entry** — which is the normal case, not the
exception — change the scores, bump the kicker's `Last updated` date and
the index stamp, and add a `.history__entry` at the top of the Score
history section saying what moved and why. A re-examination that changes
nothing still gets an entry; a catalogue that logs only movement looks
less stable than it is.

## Where the scores come from

Each evaluation is drawn from a private research corpus: a technique is
scored on four signed deltas against a stated baseline, with a confidence
level and a log of sources that disagree. The rubric is published in full
on the method page — the site does not ask you to take the scoring on
trust.
