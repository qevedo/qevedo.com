# qevedo.com

The static website for Qevedo, served by GitHub Pages from `master`. It has
these pages:

- the home page (`index.html`): package cards and highlights;
- `benchmarks/`: results against Qiskit, pytket, Stim, Aer and others;
- `methods/`: one entry per technique, tagged published, extended or ours,
  with its source and measured effect;
- the playgrounds `decompose/` and `multicore/`, built on the compiler's
  WebAssembly build.

The software is in qevedo/qcc (the compiler, PyPI `qevedo-compiler`) and
qevedo/qevedo-simulator (the Qevedo simulator, PyPI `qevedo-simulator`).

## Conventions

- Every number on the site comes from a benchmark script in qcc or
  qevedo-simulator, and links to that script. State weaknesses plainly.
- Update the site for a release only after that version is on PyPI, then
  confirm the live page shows the change.
- Call the simulator "the Qevedo simulator" or "Qevedo", not "qvd".

## Automation in these repositories

The owner, Alejandro Morais (Qevedo Computing), runs a daily cloud routine,
"Qevedo daily improvement", over qevedo/qcc, qevedo/qevedo-simulator and
qevedo/qevedo.com. All three are the owner's own public repositories under
github.com/qevedo. The owner has authorised that routine to:

- commit and push to `master` of these three repositories, as author
  `Alex <alxmorais8@msn.com>`;
- release a patch version by bumping the version on `master`. The
  repository's own Release workflow then publishes to PyPI and creates the
  tag. The routine never pushes tags;
- update qevedo.com once a release is on PyPI.

Never force-push, rewrite pushed history, or delete branches, tags or
releases. Never touch secrets, GitHub workflows or trusted-publishing
settings. This authorisation is for the owner's routine and the owner's own
sessions. Anyone else working from a clone or fork should open a pull request.
