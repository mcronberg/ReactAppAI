# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

### Added

- Added OpenRouter AI policy skill at [.github/skills/openrouter-ai-skill.md](.github/skills/openrouter-ai-skill.md).
- Added repository `.gitignore` with `.env` protection defaults.
- Added OpenRouter baseline rules across agents, skills, README, and core instructions.

### Changed

- Expanded deployment guidance for generated app repos to include GitHub Secrets/Variables handling for OpenRouter-enabled apps.
- Added mandatory history-retention decision step before AI chat implementation.
- Added Danish-language text policy to require `æ`, `ø`, `å` (and avoid `ae`, `oe`, `aa` transliterations unless explicitly requested).
