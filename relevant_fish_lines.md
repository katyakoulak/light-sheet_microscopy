# Zebrafish Lines for Light-Sheet Microscopy

## Summary Table


| Line                     | Owner / DOB                         | promoter / expression                                                                      | subcellular localization                                                           | indicator kinetics                                                             | best-suited use                                                                                                                    |
| ------------------------ | ----------------------------------- | ------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- |
| casper; Tg(elavl3:GCaMP) | Our fish<br>DOB_04.02.2024<br>n = 3 | elavl3 (HuC), pan-neuronal - virtually all post-mitotic CNS neurons, forebrain–spinal cord | presumed cytoplasmic                                                               | ?                                                                              | Adult / juvenile whole-brain light-sheet, where pigment (not present in larvae) would otherwise block or scatter the light sheet   |
| Tg(elavl3:GCaMP6s)       | Ruben DOB_03.14.2026                | elavl3 (HuC)                                                                               | Cytoplasmic - fills soma, proximal neurites, and neuropil                          | GCaMP6s = "slow/sensitive": high ΔF/F, single-AP detection, half-decay ≈ 1.8 s | High-sensitivity detection of sparse/weak activity; neuropil or process-level signal; not ideal for dense single-cell segmentation |
| Tg(elavl3:H2B-GCaMP6f)   | Ruben <br>DOB - look up             | elavl3 (HuC)                                                                               | Nuclear (H2B-fusion) - signal confined to nucleus, one bright compact ROI per cell | GCaMP6f = "fast": lower ΔF/F than 6s, half-decay ≈ 140 ms                      | Fast light-sheet acquisitions and studies prioritizing temporal precision / spike timing over maximal sensitivity                  |
| Tg(elavl3:H2B-GCaMP6s)   | Ruben DOB_12.16.2025                | elavl3 (HuC)                                                                               | Nuclear (H2B-fusion) - signal confined to nucleus                                  | GCaMP6s = "slow/sensitive": high ΔF/F, half-decay ≈ 1.8 s                      | Whole-brain, cellular-resolution light-sheet functional imaging — the field-standard combination (Vladimirov et al. 2014)          |
|                          |                                     |                                                                                            |                                                                                    |                                                                                |                                                                                                                                    |
> **Note:** Exact promoter/indicator identity of the in-house casper;GCaMP line should be confirmed against the founder paperwork — "Casper GCaMP" alone doesn't specify the promoter or GCaMP variant.

## casper; GCaMP (in-house line, n = 3)

Casper is a double pigmentation mutant, crossed to nacre. The combination leaves the fish essentially transparent through adulthood, unlike single mutants or wild-type fish, which regain pigment as they mature (White et al., 2008, Cell Stem Cell).

**Why it matters for light-sheet:** Larval zebrafish (<5 dpf) are already optically transparent, so casper adds little value at larval stages. Its purpose is to preserve that transparency into juvenile/adult stages, when pigmentation would otherwise absorb and scatter the excitation sheet and emitted fluorescence, degrading depth penetration and signal quality. 

**Best use in your lab:** The only line suited to imaging older/adult fish (or any stage where pigmentation has developed) on a light-sheet system; with only 3 fish, best reserved for adult-stage pilot experiments rather than routine larval imaging.
## Tg(elavl3:H2B-GCaMP6s)

**Promoter:** elavl3 (formerly HuC) - an early, broad post-mitotic neuronal marker gene. The elavl3 regulatory sequence used in these constructs (~8.8 kb, including first intron) drives **expression in nearly all differentiated neurons of the brain and spinal cord**, starting during early neurogenesis, **making it the standard "pan-neuronal" driver in zebrafish** (Park et al., 2000; Vladimirov et al., 2014).

**Localization:** The H2B (histone 2B) fusion tethers GCaMP6s to chromatin, **restricting the fluorescent signal to the nucleus**. Because the nucleus occupies most of a larval zebrafish neuron's soma, this produces one compact, bright, well-separated ROI per cell, which is the single biggest **practical advantage for automated cell segmentation in dense, brain-wide light-sheet volumes**. It also removes signal from the neuropil, which otherwise contaminates nearby somatic ROIs.

**Kinetics:** GCaMP6s ("slow"/sensitive) has the largest dynamic range and highest sensitivity of the GCaMP6 family, reliably detecting single action potentials, but with slow off-kinetics (single-AP half-decay ≈ 1.8 s; Chen et al., 2013, Nature).

**Literature verdict:** This is the exact construct used in the foundational whole-brain light-sheet paper from the Ahrens lab (Vladimirov, Mu, Kawashima, Bennett, Yang, Looger, Keller, Freeman & Ahrens, 2014, Nature Methods), imaging the entire larval brain at single-cell resolution at ~1–2 Hz volume rates. Because brain-wide light-sheet volume rates are themselves the rate-limiting step (not indicator kinetics), GCaMP6s's slow decay is rarely a real cost, while its higher sensitivity substantially improves detection of sparse or weak activity across large neuron populations. This is generally regarded as the best default choice for whole-brain, cellular-resolution light-sheet functional imaging.

## Tg(elavl3:H2B-GCaMP6f)

**Promoter / localization:** Same elavl3 pan-neuronal driver and same nuclear H2B targeting as above - differs from the H2B-GCaMP6s line only in the calcium indicator variant.

**Kinetics:** GCaMP6f ("fast") trades sensitivity for speed: faster rise and much faster decay (single-AP half-decay ≈ 140 ms vs. ≈ 1.8 s for 6s), better able to resolve closely spaced spikes or rapid transients (Chen et al., 2013).

**Literature verdict:** Best matched to imaging setups that can actually exploit fast kinetics — sub-region or two-photon/high-speed light-sheet acquisitions with volume rates well above ~5 Hz — or experiments where temporal precision (e.g., distinguishing individual spikes, fast sensorimotor events) matters more than absolute sensitivity. For standard whole-brain light-sheet at ~1–2 Hz, most of GCaMP6f's speed advantage is undersampled and effectively wasted, and 6s will generally outperform it on detectable events per cell.
## Tg(elavl3:GCaMP6s)

**Promoter:** elavl3, pan-neuronal, as above.

**Localization:** No H2B tag — GCaMP6s is cytoplasmic, filling the entire soma and proximal processes rather than being confined to the nucleus.

**Literature verdict:** Useful when process-level or neuropil signal is of specific interest, or for sparser/low-density regions where cell overlap is less of an issue; for dense whole-brain light-sheet volumes with automated segmentation, the H2B-nuclear lines are generally preferred.

## Bottom Line for Light-Sheet Work

- Standard whole-brain, cellular-resolution light-sheet imaging in larvae: Tg(elavl3:H2B-GCaMP6s) — nuclear localization for clean segmentation + high sensitivity matched to typical whole-brain volume rates. This is the line used in the field-defining Vladimirov et al. (2014) light-sheet paper.

- Fast/high-volume-rate acquisitions or spike-timing-sensitive questions: Tg(elavl3:H2B-GCaMP6f) — same segmentation advantage, faster kinetics, lower sensitivity.

- Any imaging beyond early larval stages (juvenile/adult): casper background is required regardless of indicator choice, since only casper (or an equivalent pigmentation mutant) keeps the fish optically accessible to a light sheet past larval stages.

## References

Chen, T.-W., Wardill, T.J., Sun, Y., Pulver, S.R., Renninger, S.L., Baohan, A., Schreiter, E.R., Kerr, R.A., Orger, M.B., Jayaraman, V., Looger, L.L., Svoboda, K., & Kim, D.S. (2013). Ultrasensitive fluorescent proteins for imaging neuronal activity. *Nature*, 499, 295–300.

Vladimirov, N., Mu, Y., Kawashima, T., Bennett, D.V., Yang, C.-T., Looger, L.L., Keller, P.J., Freeman, J., & Ahrens, M.B. (2014). Light-sheet functional imaging in fictively behaving zebrafish. *Nature Methods*, 11, 883–884.

Freeman, J., Vladimirov, N., Kawashima, T., Mu, Y., Sofroniew, N.J., Bennett, D.V., Rosen, J., Yang, C.-T., Looger, L.L., & Ahrens, M.B. (2014). Mapping brain activity at scale with cluster computing. *Nature Methods*, 11, 941–950.

Panier, T., Romano, S.A., Olive, R., Pietri, T., Sumbre, G., Candelier, R., & Debrégeas, G. (2013). Fast functional imaging of multiple brain regions in intact zebrafish larvae using selective plane illumination microscopy. *Frontiers in Neural Circuits*, 7, 65.

White, R.M., Sessa, A., Burke, C., Bowman, T., LeBlanc, J., Ceol, C., Bourque, C., Dovey, M., Goessling, W., Burns, C.E., & Zon, L.I. (2008). Transparent adult zebrafish as a tool for in vivo transplantation analysis. *Cell Stem Cell*, 2(2), 183–189.

Park, H.-C., Kim, C.-H., Bae, Y.-K., Yeo, S.-Y., Kim, S.-H., Hong, S.-K., Shin, J., Yoo, K.-W., Hibi, M., Hirano, T., Miki, N., Chitnis, A.B., & Huh, T.-L. (2000). Analysis of upstream elements in the HuC promoter leads to the establishment of transgenic zebrafish with fluorescent neurons. *Developmental Biology*, 227(2), 279–293.
