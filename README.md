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
decoding risk, and no corrected-parser raw rerun is available. The complete
scope statement, data-access matrix, and parser-risk note are included under
`docs/` inside the downloadable companion archive.

## Downloads

- [`HIERAREPAIR_COMPANION_AGGREGATE_ARTIFACT.zip`](HIERAREPAIR_COMPANION_AGGREGATE_ARTIFACT.zip):
  complete companion artifact described below.
- [`HIERAREPAIR_ARXIV_V1_SOURCE.tar.gz`](HIERAREPAIR_ARXIV_V1_SOURCE.tar.gz):
  standalone manuscript source package.
- [`hierarepair_arxiv_v1.pdf`](hierarepair_arxiv_v1.pdf): compiled manuscript.

After extracting the companion archive, its top-level `hierarepair/` directory
has the following layout:

- `raw/phaseB/`: five frozen aggregate JSON records; no raw corpus text.
- `gates/`, `paper/`, `decisions/`: frozen supporting evidence used by the
  aggregate builders.
- `scripts/`: aggregate table/figure builders and section validators.
- `preprint/`: generated aggregate tables, Figure 1, and recomputed records.
- `manuscript/`: compile-ready final manuscript source.
- `hierarepair_arxiv_v1.pdf`: compiled manuscript draft.

## Rebuild

Python dependencies for the aggregate builders are listed in
`requirements-aggregate.txt` inside the companion archive. After extracting
the archive and entering its `hierarepair/` directory, the section builders can
be run into a separate output directory, for example:

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

The environment documented in the archive's `docs/AGGREGATE_ENVIRONMENT.md`
is the observed aggregate-check environment, not the unavailable original
raw-pipeline environment and not a promise of cross-platform byte identity.

To compile the paper, follow the archive's `manuscript/README_COMPILE.txt` from
inside the `manuscript/` directory, or use the standalone source package above.

## Citation

Citation metadata, including both authors' ORCID identifiers, is provided in
[`CITATION.cff`](CITATION.cff). A DOI or archival preprint identifier has not
yet been assigned.

## Licensing

This repository uses scoped dual licensing; no single license applies to every
file:

- author-created software code is available under the
  [MIT License](LICENSE-CODE);
- to the extent the authors hold the relevant rights, author-created aggregate
  records, aggregate-derived tables and figures, and project documentation are
  available under [CC BY 4.0](LICENSE-DATA-DOCS);
- the manuscript PDF, article text and TeX source, and bibliography remain
  copyright the authors, with no additional reuse license granted here;
- no rights to third-party raw corpora or other third-party materials are
  granted.

See the repository-wide [scope notice](LICENSE) before reusing material.
