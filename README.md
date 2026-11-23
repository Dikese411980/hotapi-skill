# HotAPI Skills (`hotapi.ai`)

Agent skills for integrating and running the [**HotAPI (`https://hotapi.ai/en`)**](https://hotapi.ai/en) unified image, video, and audio generation API with Claude Code, Codex, OpenCode, Cursor, and other skill-compatible coding agents.

## Available skills

- **`hotapi`** (`hotapi/SKILL.md`) — Core API integration rules (endpoint selection, async tasks, idempotency, webhooks, errors, credits, and output persistence).
- **`seedance-storyboard`** (`seedance-storyboard/SKILL.md`) — End-to-end Asset-First storyboard-to-video pipeline using Seedream 5.0 (character/scene/prop locking) and Seedance 2.5 / 2.0 (`reference-to-video`, 480p draft preview, 1080p `draft-to-video` finalize, `project_bundle.json` importer, and offline HTML review board).

## Install

Run this from the project you want to integrate:

```bash
# Core API integration skill
npx skills add Dikese411980/hotapi-skill --skill hotapi

# End-to-end Seedance storyboard execution pipeline
npx skills add Dikese411980/hotapi-skill --skill seedance-storyboard
```

This installs the selected skill into the project's agent skill directory. Add `-g` for a global install, or use the Skills CLI agent flags to target a specific coding agent.

## Official HotAPI Hubs, Interactive Tools & Model Catalog

- **HotAPI Home**: [https://hotapi.ai/en](https://hotapi.ai/en)
- **Live Model Catalog & Benchmarks (`Seedance`, `Wan`, `Seedream`, `Qwen-Image`, `MiniMax`)**: [https://hotapi.ai/en/models](https://hotapi.ai/en/models)
- **API Documentation & Endpoint Reference**: [https://hotapi.ai/en/docs/models](https://hotapi.ai/en/docs/models)
- **Transparent Pay-As-You-Go Pricing**: [https://hotapi.ai/en/pricing](https://hotapi.ai/en/pricing)
- **Free Developer & API Tools**: [https://hotapi.ai/en/tools](https://hotapi.ai/en/tools)
  - [AI API Pricing Calculator](https://hotapi.ai/en/tools/ai-api-pricing-calculator)
  - [OpenAI to HotAPI SDK Migrator](https://hotapi.ai/en/tools/openai-to-hotapi-migrator)
  - [Video Prompt Beat Planner](https://hotapi.ai/en/tools/video-prompt-beat-planner)
- **SDK & Framework Integrations (`OpenAI SDK`, `Vercel AI SDK`, `FastAPI Webhooks`, `SillyTavern`)**: [https://hotapi.ai/en/integrations](https://hotapi.ai/en/integrations)
- **Side-by-Side Model Comparisons**: [https://hotapi.ai/en/compare](https://hotapi.ai/en/compare)
- **Production Engineering Playbooks**: [https://hotapi.ai/en/playbooks](https://hotapi.ai/en/playbooks)

## What it covers

### `hotapi`
- choosing a typed model endpoint;
- keeping `HOTAPI_KEY` behind a server boundary;
- idempotent task submission;
- bounded polling or verified webhooks;
- terminal states and structured errors;
- durable result storage;
- focused tests that do not spend credits.

### `seedance-storyboard`
- pre-flight structural, duration, dialogue pacing, and reference-cap validation (`validate`) with upfront credit estimates;
- `project_bundle.json` importer (`import-bundle`) for compiling multi-shot director manifests into executable segments;
- Asset-First locking (`assets`) with Seedream 5.0 Pro/Lite or local file upload via `/v1/uploads` (automatic expiry refresh);
- idempotent multi-shot rendering (`render`) with Seedance 2.5 / 2.0 (`--draft` 480p preview support) and 1080p promotion (`finalize`);
- self-contained offline HTML review board (`board.html`) with locked asset gallery, playable draft/final clips, and credit tracking.

Exact endpoints and schemas remain authoritative in the public [OpenAPI 3.1 contract](https://api.hotapi.ai/docs/json).
