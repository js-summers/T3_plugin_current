# Recombinant Protein Production Planner

A local browser app for first-pass recombinant protein production planning.

## What it does now

- Accepts a common protein name, UniProt accession, or PDB ID.
- Resolves sequence records from UniProt, with PDB-to-UniProt mapping through RCSB.
- Computes useful physicochemical properties:
  - length, molecular weight, estimated pI, GRAVY, charge at pH 7
  - cysteine count, extinction coefficient, aliphatic index, N-glycosylation motifs
  - first-pass behavior flags for aggregation/folding concerns
- Searches Crossref and OpenAlex for recombinant production literature, then filters for target-protein relevance and yield/titer language.
- Adds targeted company white-paper and application-note search links for vendor-reported yields.
- Mines available metadata and abstracts for host/system names, quantitative or qualitative yield/titer mentions, and production behavior or failure terms.
- Shows a color-coded amino acid map of the full construct, separating N-terminal fusions, target protein, C-terminal fusions, and custom fusion sequence.
- Expands bacterial production risk review for glycosylation loss, size burden, disulfides, hydrophobicity, pI, charge, proteolysis, inclusion-body, endotoxin, and Salmonella-specific process concerns.
- Generates a draft host-biased codon-optimized DNA sequence.
- Includes Salmonella as a host option using an enteric-bacteria codon table draft.
- Designs draft Golden Gate primers for BsaI or BsmBI/Esp3I overhang cloning.
- Adds explicit stop-codon and vector-frame controls for insert design.
- Adds an advisory Cloning QC / Preflight panel for ORF integrity, Type IIS domestication, receiver-pair compatibility, primer quality, and fusion parsing.
- Suggests first-pass synonymous domestication edits when selected Type IIS sites are detected inside the insert.
- Accepts a pasted plasmid nucleotide sequence, identifies selected Type IIS sites, predicts receiver overhangs, and previews the plasmid-level construct after insert ligation when a receiver pair is found.
- Stores reusable plasmid backbones with marker/promoter/notes metadata, JSON library export, GenBank/JSON import, and delete support.
- Captures manually curated yield evidence from papers, vendor notes, or imported literature review work.
- Builds a rule-based expression strategy panel for host, compartment, solubility, secretion, and process risks.
- Captures PCR setup details before analysis and calculates amplicon extension plus thermocycler recommendations after the insert is generated.
- Calculates primer Tm with a basic GC-adjusted estimate and amplicon extension time from sec/kb.
- Exports an Excel-readable workbook with Summary, Physicochemical, Literature, Expression Strategy, Cloning, PCR, Cloning QC, Plasmid, QC, Project Wrap Up, and Inputs sheets.
- Exports AlphaFold-ready FASTA for the native protein and fusion construct.

## Placeholders

- Host secretion / folding prediction module.
- Bioreactor culture condition model.
- Direct AlphaFold 3 submission. The current version exports FASTA because public upload workflows can vary and usually require an authenticated browser session.

## Notes

This app is a planning tool. The preflight checks are advisory and do not block export. Primer designs, codon optimization, enzyme domestication, fusion boundaries, stop codons, scars, secretion signals, Type IIS cut interpretation, and vector frame should be reviewed before ordering DNA or running experiments.
