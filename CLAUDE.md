# rulespec-co Agent Notes

This repo stores Colombia RuleSpec source registry materials, oracle references, and encoded policy rules. All encoded law lives under a single `co/` namespace.

## Scope

- `co/statutes/`: Colombiaian laws — Ley 100 de 1993, Ley 2010 de 2019 (ET Art. 241 UVT schedule), Ley 1532 de 2012, and other primary law needed for tax-benefit modeling.
- `co/regulations/`: executive decrees, reglamentos, and institutional resolutions (DIAN resolutions, UVT-value resolutions, program decrees) made under the laws.
- `co/policies/`: social-protection programme rules set administratively (Ingreso Solidario, Colombia Mayor and Jóvenes en Acción programme rules).
- `programs/`: declarative compose specs (one per jurisdiction/program/period).
- `data/coverage/`, `data/oracles/`: coverage backlog and comparison references. These are never legal authority.

## Do

- Start from the furthest upstream source: Registro Oficial texts and official consolidations (SRI compilations, IESS prints, ministry legal-basis records — record the host in manifest metadata), decrees and institutional resolutions next, agency guidance last.
- Add RuleSpec under `co/statutes/`, `co/regulations/`, or `co/policies/` with companion `.test.yaml` files.
- Cite corpus paths from modules via `module.source_verification.corpus_citation_path` (or `corpus_citation_paths`).
- Use the COLMOD v6.0 policy window (2019–25) as the validation frame: health SIC 12.5% (4/8.5); pension SIC 16% (4/12); FSP bands; UVT-banded PIT per Ley 2010; VAT 19/5/0. Indexed/annual values must be corpus-grounded, never invented.
- Keep exact oracle versions in `data/oracles/oracle-index.json`. The SOUTHMOD bundle is licensed and non-redistributable — never commit bundle bytes, dataset rows, or model XML.
- Sync `axiom-encode` and `.axiom/toolchain.toml` before substantial encoding runs.

## Do Not

- Use DIAN calculators or third-party tax alerts as the first legal source when a law or instrument governs the rule.
- Invent, round, or interpolate any Colombiaian monetary amount, rate band, or threshold. Every number must come verbatim from a captured official provision.
- Migrate COLMOD, EUROMOD/SOUTHMOD, or agency calculator code mechanically as RuleSpec.
- Add generated source payload dumps, formula artifacts, `parameters.yaml`, or standalone YAML fixtures outside allowed RuleSpec roots.
- Hand-copy statute text into RuleSpec without a corpus `citation_path`.
