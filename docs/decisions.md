# Technical Decisions Log

Each entry documents a decision made during the project, the context, and the reasoning behind it.

## [2026-08-15] Python version pinned to 3.11

**Decision:** Python 3.11 was setup 

**Why:** Databricks Connect does not support Python 3.12+ version, and several Databricks Runtimes still rely on Python 3.11,
		 so pinning to 3.11 ensures compatibility between local development and Databricks

## [2026-08-15] Dependency management with uv instead of pip/venv

**Decision:** Virtual environment was set up using uv.

**Why:** To manage dependencies deterministically via uv.lock, which pins exact library versions and prevents the kind of	
		 version conflicts we hit earlier (e.g numpy requiring Python 3.12+ while the project targets 3.11).

## [2026-08-15] Squash and merge as the PR merge strategy

**Decision:** to push to github using Squash and merge option

**Why:** We only want main's history to show one commit that summarizes each completed feature, instead of every intermediate commit
		 made while developing it.

## [2026-08-16] Databricks Free Edition instead of Community Edition

**Decision:** Use Databricks Free edition

**Why:** Databricks Community Edition was retired on January 1, 2026, and Free Edition is its official replacement - same core capabilities
		 (Notebooks, MLflow, Git integration via "Git Folder") serverless by default.
