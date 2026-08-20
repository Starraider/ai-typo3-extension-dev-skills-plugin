# TYPO3 Extension Development Skills

An Agent Plugins 1.0.0 package of reusable skills for TYPO3 v13 and v14 extension development. It provides portable Agent Skills only; it does not bundle an MCP server.

## Included Skills

- [TYPO3 Extbase Plugin](skills/typo3-extbase-plugin/README.md) — build or extend Extbase frontend plugins, including domain models, repositories, controllers, TCA, TypoScript, and registration.
- [TYPO3 FlexForms](skills/typo3-flexforms/README.md) — create, modernize, and troubleshoot TYPO3 v14 FlexForms.
- [TYPO3 Scheduler Task](skills/typo3-scheduler-task/README.md) — create or migrate TYPO3 v14 scheduler tasks using native TCA configuration.
- [TYPO3 Translatable Extension Data](skills/typo3-translatable-extension-data/README.md) — configure localized custom records and language-aware Extbase retrieval.

## Package Layout

`plugin.json` is the portable Agent Plugins v1 manifest. Skills are discovered from immediate child directories of `skills/`; each skill's `SKILL.md` is the operational instruction source. The `agents/openai.yaml` files are retained as client-specific presentation metadata and are not part of the portable plugin contract.

## Installation

Install this complete plugin directory through an Agent Plugins-compatible client. For standalone skill use, install an individual `skills/<name>/` directory in the target client's project skill location; each skill README documents the supported paths and portable behavior.

## Validation

From the plugin root, run the Agent Plugin validator and the `new-skill` validator for every immediate child skill:

```bash
python3 /path/to/agent-plugin-builder/scripts/validate_agent_plugin.py --strict .
for skill in skills/*; do
  /path/to/new-skill/scripts/validate-skill.sh "$skill" --strict-portable
done
```

When available, also run `skills-ref validate` for each skill and perform the TYPO3-specific runtime checks described in its README. Runtime schema, cache, backend, frontend, and Scheduler checks require an authorized TYPO3 environment.

## Compatibility

The package follows [Agent Plugins 1.0.0](https://agent-plugins.org/specification) and the [Agent Skills specification](https://agentskills.io/specification). Individual skill descriptions state their TYPO3-version scope.

## License

This project and all contained Agent Skills are licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](LICENSE).

Copyright (c) 2026 Sven Kalbhenn ([https://www.skom.de](https://www.skom.de)).
