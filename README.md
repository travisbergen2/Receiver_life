# Receiver Life

Room XII of the Fractal Youniverse collection — live at **https://fractalyouniverse.org/Receiver_life/**
(mirror: https://travisbergen2.github.io/Receiver_life/).

A cellular automaton where every cell is an RPCS-1 receiver: four parameters
(TI — temporal integration, SG — signal gain, UE — update elasticity, FT — filter
threshold) moving through four slots (one narrator slot `+`, three `−` slots), with
strategies that stay on the slot. Color shows which parameter holds the narrator slot;
brightness shows activity.

Built by Travis Bergen (October 2026). Successor to Room IV, *Bergen's Game of Life*,
which stays live at https://travisbergen2.github.io/Bergen-s_Game_of_Life/.

## How each step works

- **All parameters start high** (0.75–1.0), so early on everything changes and switches fast.
- **FT** filters neighbor signals: a neighbor only counts if its activity is above 0.6 × FT.
  Signal that gets filtered out pushes FT down.
- **SG** scales the incoming signal; a mismatch between what the cell expected and got pushes SG down.
- **TI** sets integration speed: lower TI means faster integration. Leftover lag pushes TI down.
- **UE** damps everything: the size of every parameter change and the slot-switching rate both
  scale with UE. Fast changing wears UE down, so it slows over time.
- **Strategies live on slots.** Each parameter receives its own data channel, and that data shapes
  the strategy of whatever slot it sits in. The strategy then biases the next parameter to move into
  that slot. Uncheck *Strategy stays on slot* to make strategies follow the parameter instead, as a comparison.
- Activity follows a smoothed Game of Life rule on the counted signal. An **extreme event** resets a
  patch to high parameters and scrambles its activity.

## Controls

Pause / Step / New world · Speed slider · tap mode (Inspect a cell, or trigger an Extreme event) ·
*Strategy stays on slot* · *Random extreme events*. Read-outs: generation, % active cells,
slot switches per step, mean parameter settings over time, and who holds the narrator slot.

## Running it

Open `index.html` in any modern browser. The page is self-contained: one external request
(the Google Fonts stylesheet), no analytics, no network calls, nothing stored.

## What this is and is not

An RPCS-1 toy — a dynamical picture of the receiver primitives defined in IMM Paper 9
(https://doi.org/10.5281/zenodo.19697792). The update rules are the author's design choices,
not fitted to data; nothing here measures humans or models, and nothing here bears on any
mathematical conjecture.

## Provenance

`index.html` sha256 `aa9d2de31b07c2af…` (full hash in the publish log, 2026-10-13).
