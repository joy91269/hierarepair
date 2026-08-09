# HieraRepair companion aggregate artifact

This repository accompanies the manuscript:

> **A Symmetric Layer--Union Audit of Component Collapse in Hierarchical Procedural Corpora**  
> Jiuyi Zheng and Gan Xu, University of Missouri.

It publishes the frozen **aggregate-level** evidence used in the paper, the
generated scientific tables and Figure 1, the corresponding builders and
consistency checks, and a compile-ready manuscript source tree.

## What this artifact supports

- Inspection of the six-source fixed panel and the frozen edge-family lattice.
- Regeneration of the aggregate-derived scientific tables for Sections 3--8.
- Regeneration of the native-LaTeX Figure 1 from frozen aggregate inputs.
- Inspection of the two post hoc editorial derivatives (panel summary and
  spanning-forest sensitivity bounds).
- Offline compilation of the supplied manuscript source.

The principal descriptive result is that MyFixit and Doc2Dial pass the
individual-layer audit but fail under the union. The observed two-of-six panel
fraction is descriptive and is not a prevalence estimate. The registered
mechanism-discrimination condition is not met because the bridge predictor is
not distinguished from the density control.

## Scope boundary

This is **not** a raw-data end-to-end release. It excludes:

- all third-party raw corpora;
- private literature PDFs and extracted full text;
- project conversations, review bundles, and superseded history;
- the recovered raw runner as a trusted public execution entry point.

The raw corpora must be obtained from their original providers under their
respective terms. The recovered Human Know-How loader has an unresolved
decoding risk, and no corrected-parser raw rerun is available. See
[`docs/PUBLIC_ARTIFACT_SCOPE.md`](docs/PUBLIC_ARTIFACT_SCOPE.md),
[`docs/DATA_ACCESS_AND_LICENSE_MATRIX.md`](docs/DATA_ACCESS_AND_LICENSE_MATRIX.md),
and
[`docs/SECTION11_HUMAN_KNOWHOW_DECODE_RISK_NOTE.md`](docs/SECTION11_HUMAN_KNOWHOW_DECODE_RISK_NOTE.md).

## Repository map

- `raw/phaseB/`: five frozen aggregate JSON records; no raw corpus text.
- `gates/`, `paper/`, `decisions/`: frozen supporting evidence used by the
  aggregate builders.
- `scripts/`: aggregate table/figure builders and section validators.
- `preprint/`: generated aggregate tables, Figure 1, and recomputed records.
- `manuscript/`: compile-ready final manuscript source.
- `hierarepair_arxiv_v1.pdf`: compiled manuscript draft.

## Rebuild

Python dependencies for the aggregate builders are listed in
`requirements-aggregate.txt`. From the repository root, the section builders
can be run into a separate output directory, for example:

```sh
python3 scripts/build_section4.py --project-root . --output-root /tmp/hierarepair-rebuild
python3 scripts/build_section5.py --project-root . --output-root /tmp/hierarepair-rebuild
python3 scripts/build_section6.py --project-root . --output-root /tmp/hierarepair-rebuild
python3 scripts/build_section7.py \
  --source decisions/HIERAREPAIR_COMPLETE_RESEARCH_EXPLORATION_REVIEW_20260724.md \
  --output-root /tmp/hierarepair-rebuild
python3 scripts/build_section8.py \
  --source gates/gate_a_literature_collision_v0_1.md \
  --output-root /tmp/hierarepair-rebuild
```

The matching section checks can then be run against the distributed aggregate
preprint tree. For example:

```sh
python3 scripts/validate_section4.py \
  --project-root . --preprint-root preprint \
  --output /tmp/section4_validation.json
python3 scripts/validate_section5.py \
  --project-root . --preprint-root preprint \
  --output /tmp/section5_validation.json
python3 scripts/validate_section6.py \
  --project-root . --preprint-root preprint \
  --output /tmp/section6_validation.json
python3 scripts/validate_section7.py \
  --source decisions/HIERAREPAIR_COMPLETE_RESEARCH_EXPLORATION_REVIEW_20260724.md \
  --preprint-root preprint --output /tmp/section7_validation.json
python3 scripts/validate_section8.py \
  --source gates/gate_a_literature_collision_v0_1.md \
  --preprint-root preprint --output /tmp/section8_validation.json
```

Section 3 additionally uses ReportLab and, for the native-LaTeX figure,
Tectonic and Poppler:

```sh
python3 preprint/build_section3.py \
  --project-root . \
  --output-root /tmp/hierarepair-rebuild \
  --tectonic /path/to/tectonic \
  --pdftoppm /path/to/pdftoppm
```

The environment documented in `docs/AGGREGATE_ENVIRONMENT.md` is the observed
aggregate-check environment, not the unavailable original raw-pipeline
environment and not a promise of cross-platform byte identity.

To compile the paper, follow `manuscript/README_COMPILE.txt` from inside the
`manuscript/` directory.

## Citation

Citation metadata, including both authors' ORCID identifiers, is provided in
[`CITATION.cff`](CITATION.cff). A DOI or archival preprint identifier has not
yet been assigned.

## License status

No standalone license for the authors' code or aggregate records has yet been
specified. No rights to third-party raw corpora are granted by this repository.
The repository is public for inspection and review; a reuse license should be
added only after an explicit author decision.
