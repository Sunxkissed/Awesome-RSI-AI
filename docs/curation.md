# Curation Notes

[Back to the resource list](../README.md)

## Source Snapshot

This companion was prepared from the supplied PDF of [Recursive Self-Improvement in AI: A Survey, v1](https://doi.org/10.20944/preprints202609.2680.v1), posted September 30, 2026. The survey describes a narrative review, with a main literature cutoff of September 12, 2026 and a historical supplement dated September 20. The repository's initial link checks were performed on October 23, 2026; this is a verification date, not an expanded literature cutoff.

The curated README contains **92 selected papers and surveys**. Its sections follow the source survey's mechanisms and evaluation concerns. Each paper entry links to the primary source and the original numbered reference. Author-linked code and project resources are optional additions.

## Verification Scope

For curated entries, primary paper pages were inspected to check bibliographic identity and first-public year. Descriptions draw on the source survey and primary abstracts. Code and project links were followed from author-provided paper links. This is not an independent replication, implementation audit, or a new full-text review of every experiment.

The [curated JSON index](../data/curated.json) mirrors the README's selected entries, categories, descriptions, optional resources, source numbers, and check dates. It is separate from the [complete bibliography archive](references.md).

The complete archive preserves **405 numbered references** from the PDF. All 405 source URLs were matched to embedded PDF hyperlink annotations; line wrapping and obvious text-extraction artifacts were repaired. Raw extracted citations and import provenance remain in [references.json](../data/references.json). The archive does not claim independent external verification of all 405 entries.

## Source Discrepancy

Section 2.2 states that the bibliography contains 404 distinct works, whereas the PDF's reference section is numbered continuously from 1 through 405. No duplicate source identifiers were found during import. Distinct identifiers alone do not prove distinct research works. The repository preserves the source numbering and reports the discrepancy rather than silently deleting or renumbering an entry.

## Editorial Choices

- Entries describe mechanisms and evaluation roles; inclusion is not a claim that a method establishes sustained RSI.
- Local-refinement methods and collapse studies are included as comparisons and boundary evidence.
- Years use the first public version where checked; a later conference year or revision can differ.
- The complete archive preserves versioned URLs from the PDF. Curated entries may use an unversioned paper page that exposes later revisions; the list's coverage remains tied to the survey snapshot.
- Related paper versions are not added as separate curated entries simply to increase the list's size.
- Quantitative cross-paper leaderboards are omitted because the protocols, tasks, and budgets differ.

## Maintenance

Add new resources through focused pull requests following [CONTRIBUTING.md](../CONTRIBUTING.md). Keep the README and curated JSON index aligned. Preserve archive numbering and record source-supported corrections explicitly. Mark post-cutoff additions so readers can distinguish the original survey snapshot from later maintenance.

This initial organization, bibliography extraction, and source checking used AI assistance. Verification scope is reported above so that readers can distinguish imported metadata, checked primary records, and experimental validation.
