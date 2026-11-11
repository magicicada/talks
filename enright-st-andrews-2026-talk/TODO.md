# Train checklist — St Andrews talk, 12 November 2026

Everything here can be done offline. No internet, no `-shell-escape`, no font
installs: Fira comes from your TeX Live tree.

**File:** `enright-st-andrews-2026.tex` in this folder.
**Build:** open it in TeXShop and press Typeset (the magic comment selects XeLaTeX),
or on the command line, twice:

    xelatex enright-st-andrews-2026.tex
    xelatex enright-st-andrews-2026.tex

**After each rebuild**, line numbers below shift. Re-find things by searching for
the quoted text rather than trusting the line number.

---

## State as of leaving

- 53 pages. **Main talk = p1–p42** (ends on *Summary and Thanks!*).
  **p43–p53 are the c-closedness back-up**, not part of the talk.
- Title: *Temporal graphs: parameters and games*. Date set to 12 November 2026.
- Order: temporal graphs → problems → motivation → parameterisation → games → thanks.
- **42 slides for a 45-minute slot.** That is the thing to fix. Target ~34–36.

### Page map (main talk)

| p | slide | p | slide |
|---|---|---|---|
| 1 | title | 18 | So we need parameterised approaches! |
| 2 | The Plan | 19 | Restricting the underlying structure |
| 3 | Temporal graphs | 20 | Temporal and underlying structure (sampler) |
| 4–8 | Everything is harder (5 overlays) | 21 | Temporal parameters (VIM) |
| 9 | Problems on temporal graphs | 22 | VIM decomposition DPs |
| 10 | why are you ruining your life | 23 | Temporal graph problems |
| 11 | It all started with cows | 24 | Ex: Temporal Hamiltonian Path |
| 12 | Diseases travel forward in time | 25 | meta-algorithm ("Much as I love these DPs") |
| 13 | Humans get diseases too | 26 | But there's more! (TIM) |
| 14 | What do you do with an NP-hard problem? | 27 | TIM is more complicated |
| 15 | Parameterised algorithmics | 28 | We wanted parameters for denser graphs |
| 16 | The classic example (Vertex Cover) | 29–30 | Neighbourhood diversity ×2 |
| 17 | Where does the parameter come from? | 31–32 | Temporal Neighbourhood Diversity ×2 |
|  |  | 33–34 | Tractability with tnd ×2 |
|  |  | 35 | cliquewidth conjecture |
|  |  | 36–41 | games (6 slides) |
|  |  | 42 | Summary and Thanks! |

---

## 1. Must do

- [ ] **Fred and Georg's surnames.** Line ~1181, search `TODO Jess`. The slide
      (p40, *How bad can a schedule be?*) currently ends "Work in progress with
      Fred and Georg, begun at Dagstuhl." Your `temporal-cops` notes only ever
      use first names, which is why this is blank.

- [ ] **Decide how hard to claim the hypercube result** (p41). It is currently
      set in a `Claim` environment reading $\hat c_{\max}(Q_k) \ge k$, with
      "believed, under internal review" underneath. That matches `additional.tex`,
      where it is `\begin{claim}` and Fred's margin objection is answered by
      Georg but never closed. Upgrade to a theorem only if you have since settled
      that exchange.

---

## 2. Cutting down (the main job)

Cut by **commenting frames out** (`%` the whole `\begin{frame}…\end{frame}`)
rather than deleting, so you can put them back if the room is quick.

Ranked by how little they cost you:

- [ ] **p30 — the second *Neighbourhood diversity* slide.** p29 and p30 carry the
      same definition text; only the picture changes (graph vs decomposition).
      Easiest single slide in the deck to lose. **Saves 1.**
- [ ] **p32 — the second *Temporal Neighbourhood Diversity* slide** (the
      non-example). Same situation. The example on p31 carries the idea.
      **Saves 1.** Though the non-example is the one that shows why the
      definition is fussy, so consider cutting p31 and keeping p32 instead.
- [ ] **p25 — the meta-algorithm slide** ("Much as I love these DPs they do start
      to feel a little similar"). The formal $(k,X)$-machinery it points at is
      already commented out, so it promises something the talk does not deliver.
      **Saves 1.**
- [ ] **p23 — *Temporal graph problems*.** It introduces Temporal Hamiltonian Path,
      which p24 then works through anyway. Merge the one-line definition into p24.
      **Saves 1.**
- [ ] **p12 — *Diseases and cattle travel only forward in time*.** The motivation
      runs p10–p13; four slides is generous. The cow-TARDIS picture is the fun one,
      so p11 or p13 could go instead. **Saves 1.**
- [ ] **p14 — *What do you do with an NP-hard problem?*** For a combinatorics
      audience the list (approximate / heuristic / exponential) is the least
      surprising slide of the four-slide parameterised intro. Cutting it leaves
      p15–p17, which still define FPT, give Vertex Cover, and discuss choosing a
      parameter. **Saves 1.**
- [ ] **One of the five *Everything is harder* overlays (p4–p8).** The static
      Eulerian circuit (p5) exists to set up TempEuler (p6); the two StarExp
      overlays (p7–p8) are yes-instance then no-instance. Dropping one StarExp
      overlay costs the least. **Saves 1.**

Taking the first six gets you to 36. That is still brisk but deliverable.

**Do not cut** p19 (*Restricting the underlying structure*) — it is the slide
that justifies the whole parameterisation move, and a pure maths audience will
want the hardness-even-on-paths examples.

---

## 3. Games fixes

- [ ] **p39, *Even cycles are interesting again* — $\ell$ is undefined on the
      slide.** Line ~1154 says "every edge-periodic cycle with
      $n \ge 2\ell\cdot\mathrm{lcm}(L)$ is robber-win", but $\ell$ never appears
      anywhere else. In Erlebach & Spooner, $\ell = 1$ when
      $\mathrm{lcm}(L) \ge 2\max L$ and $\ell = 2$ otherwise. Since $\ell \le 2$
      always, the safe fix is to replace the bound with
      $n \ge 4\,\mathrm{lcm}(L)$, which is implied and needs no extra notation.
      **This is the one actual error in the games section.**

- [ ] **p38, *Cops and robbers, periodically*.** The cited results decide
      cop-win versus robber-win; Erlebach & Spooner do **not** define a cop
      number for edge-periodic graphs. The slide is written to respect that —
      keep it that way if you reword.

- [ ] **p41, *Hypercubes* — the computations quoted are $d=6 \to 8$ and
      $d=7 \to 12$ only.** I deliberately left out $d=8 \to 18$ and
      $d=9 \to {>}28$, because `additional.tex` attributes those to "an even more
      efficient but maybe incorrect implementation". Add them only if that
      implementation has since been checked.

- [ ] **p41 figure caption.** The $P_4 \square P_4$ claim ($\hat c_{\max} \ge 3$,
      period 9) rests on a proof sketch resting on that hand-drawn figure, so the
      caption says "we think 3 cops are needed". Firm it up only if the sketch has
      become a proof.

- [ ] **Optional — an open problem to close the games section.** Your
      `patrolling-cop` notes observe that patrolling on a *periodic temporal
      graph* appears not to have been studied. That is a natural last line, and
      it is your own observation.

- [ ] **Optional — a burning contrast.** Line ~1007 has a commented-out theorem:
      *Temporal Graph Burning is NP-hard even when restricted to graphs with
      constant temporal modular-width.* Uncommenting it next to the FPT-by-tnd
      result on p33–34 makes a sharp "the parameter really matters" pair.

---

## 4. Cosmetic, only if there is time

Six overfull `\vbox` warnings, i.e. content slightly taller than the frame.
None of them look broken on screen; they have all been there since the AARMS
version. Search the log for `Overfull \vbox` after a rebuild.

Affected: the title page, *Temporal graphs* (p3), *It all started with cows*
(p11), both *Temporal Neighbourhood Diversity* slides (p31–32), and
*$c$-closedness* in the back-up block (p44).

---

## 5. If something breaks

- The deck as it leaves here compiles clean: 53 pages, no errors, no missing
  characters. If a build fails after an edit, the usual cause is an unbalanced
  `\begin{frame}`/`\end{frame}` from commenting a frame out halfway.
- A pre-edit copy of today's file is NOT in this folder — but `git` is not in use
  here either, so **make a copy before you start cutting**:
  `cp enright-st-andrews-2026.tex enright-st-andrews-2026.tex.bak`
- The AARMS version of the same material is intact in
  `../enright-aarms-2026-talk/` if you need to look at an earlier form of a slide.
