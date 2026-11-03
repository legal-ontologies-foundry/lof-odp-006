# LOF-ODP-006: Relations between Norms

Draft ontology design pattern for the [Legal Ontologies Foundry](https://legal-ontologies-foundry.github.io/odp/odp-006/).
Status: **draft 0.1.0**, for review by the founding coordinators.

How items of legal content bear on one another: particularization;
derogation, substitutive or blocking, with its authorization recorded through
LOF-ODP-001 *performed under*; conflict between the legal positions they
ground, lifted to the content; and precedence determinations stating, on
grounds such as lex superior, lex specialis, lex posterior, or the primacy of
an overriding legal order (EU law, federal law), which content prevails and according to whom. Any determination makes
content *held to prevail over* other content; only a determination that is
itself legal content makes it *prevail over* it. SHACL shapes report
unresolved, contested, and unauthoritatively resolved conflicts.

## Files

| Path | Contents |
|---|---|
| `src/ontology/lof-odp-006-edit.ttl` | Editors' file |
| `src/ontology/imports/` | BFO 2020 core and the base releases of ODP-001 and 003 |
| `src/ontology/alternatives/` | ODP-003 Option B base, for testing under both placements |
| `src/examples/gdpr-norm-relations.ttl` | Worked example: GDPR, ePrivacy Art. 5(3) and TDDDG § 25, BDSG §§ 26(2) and 27(2), primacy of EU law, a court's holding |
| `src/shapes/norm-relations.shacl.ttl` | Unresolved, contested, and unauthoritatively resolved conflicts; well-formed determinations |
| `src/mappings/odp-006-standards.sssom.tsv` | Alignment with LOMO, Akoma Ntoso and LegalRuleML (SSSOM) |
| `src/sparql/` | QC checks (`*-violation.sparql`) and competency questions (`cq*.rq`) |

## Building and testing

```
cd src/ontology
make test           # HermiT consistency + seven SPARQL QC checks + ROBOT report
make test-options   # worked example under both ODP-003 options
make shacl          # shapes report (needs: pip install pyshacl)
make cq             # competency questions
make release VERSION=0.1.0
```

Verified on 0.1.0: consistent and OWL 2 DL; the example is consistent under
both ODP-003 options; content conflict, *held to prevail over* and (from the
court's holding only) *prevails over* are inferred as documented; the shapes
report the two deliberate defects (an unresolved conflict and a contested
precedence, both warnings), the cookie conflict as resolved only without legal
force (information), and the two readings that name no source (warnings).

## License

[CC BY 4.0](LICENSE). Term ID range ODP006_0001000 to 0001999 (first editor).
