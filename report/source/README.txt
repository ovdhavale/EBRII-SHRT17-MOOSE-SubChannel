EBR-II SHRT-17 XX09 Part A - Overleaf v3 (low-similarity rewrite)
================================================================

Upload this ZIP directly to Overleaf and compile main.tex.

Design of this revision
-----------------------
- Explanatory prose was rewritten from scratch rather than adapted sentence-by-sentence
  from Argonne or MOOSE documentation.
- The public MOOSE input listing was removed from the report body.
- Only the small DP_assembly postprocessor added for this portfolio study is reproduced.
- Public benchmark facts, equations, property correlations, numerical identifiers and
  experimental data remain cited to their sources. These items may necessarily match
  source material because changing technical equations/names/numbers would be incorrect.
- Original figures, mesh-sensitivity values, hand-check results and error metrics are
  identified as present-study work.

Important limitation
--------------------
No document can be guaranteed to receive a particular score from a proprietary similarity
checker. Bibliographic entries, equations, software class names, benchmark titles and exact
numerical data can still be detected as matching text even when properly cited. This revision
is intended to minimize avoidable prose/code overlap while preserving technical accuracy and
source attribution.

Files
-----
main.tex                     Main report
refs.bib                     Bibliography
figures/temperature_field.png Present-study ParaView rendering
figures/ttc_validation.png    Present-study experiment/model comparison
code/pressure_drop_postprocessor.i  Present-study MOOSE addition
data/*.csv                    Present-study processed result tables

Basic overlap sanity check
--------------------------
As a limited heuristic check, the body text on report pages 1-3 was normalized and compared
against the supplied Argonne benchmark PDF using exact six-word sequences. No exact six-word
sequence was found in common after URL/punctuation normalization. This is not a substitute
for a commercial similarity database and does not predict any proprietary similarity score;
it only checks direct phrase overlap against that one supplied source.
