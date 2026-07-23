# rulespec-co

Colombia RuleSpec source registry.

This repository targets the Colombian tax-benefit surface simulated by COLMOD (the SOUTHMOD tax-benefit microsimulation model for Colombia, UNU-WIDER; v6.0, policy years 2019–25): personal income tax under the Estatuto Tributario as rewritten by Ley 2010 de 2019 (the UVT-denominated schedular system, Art. 241 bands applied from 2020; Ley 2277 de 2022 governs the 2023+ parameters — tranche-2 capture), health and pension social insurance contributions under Ley 100 de 1993 (health 12.5 percent split 4/8.5; pension 16 percent split 4/12; the solidarity fund FSP), the Familias en Acción conditional transfer under Ley 1532 de 2012, the 2020–22 Ingreso Solidario under Decreto Legislativo 518 de 2020, VAT (19/5/0 percent) and the national consumption tax.

All encoded law lives under a single `co/` namespace. The validation frame is COLMOD v6.0 (report CR-COLMOD-v6.0, Tables 2.9–2.27).

## Source Priority

Policy must come from the furthest upstream available source: Diario Oficial texts and official norm systems first (SUIN-Juriscol norm pages, the Función Pública EVA gestor normativo — record the host in manifest metadata; SUIN serves a leaf-only TLS chain, complete it from the leaf's AIA intermediate rather than disabling verification), decrees and DIAN resolutions next, agency guidance only after the governing instrument is identified.
