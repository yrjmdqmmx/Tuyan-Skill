# Tuyan scientific figure Skill

Knowledge **1.2.0**. Full scientific-figure taxonomy, versioned journal rules, local PNG/SVG workflows and artifact-bound qualitative review.

Install the complete [tuyan-scientific-figure](tuyan-scientific-figure) directory; see the [installation guide](tuyan-scientific-figure/references/client-installation.md). Node.js 24+ is needed for local helpers; no npm installation or model call is needed. Preserve existing installations before updating.

Public indices: [domestic](https://tuyansci.cn/.well-known/skills/index.json) and [mirror](https://www.paperbanana.asia/.well-known/skills/index.json). Hosted anonymous MCP: https://api.paperbanana.asia/mcp . Research data never goes to MCP.

This repository is exported from the production Tuyan monorepo with scripts/sync-agent-distributions.mjs. distribution.json records source revision, knowledge versions and file hashes. Do not independently edit generated runtime or snapshot files.

Run npm test for offline contract/provenance validation. These tests do not establish real-model quality or publisher acceptance. Bundled validator licenses are in references/runtime-licenses.txt within the Skill.
