---
name: external-api
description: MUST use when the solution depends on an Airflow/dbt/Terraform/OpenTofu/Proxmox/provider or other external API/configuration detail. Check the installed version and local API compatibility before editing; use Context7 for one precise uncertainty; then validate locally.
---

# External API workflow

Do not guess external APIs.

Before editing:

1. Determine the installed tool/library/provider version when possible.
2. Inspect existing local examples/configuration.
3. Test whether the intended import/resource/argument exists locally.

If an API detail is still uncertain, use Context7.

Context7 rules:
- one narrowly formulated API question;
- include the installed version;
- normally one resolve + one documentation query;
- no general tutorials;
- do not query again unless verification exposes a different API uncertainty.

After applying documentation, prove compatibility locally.

Examples:

Airflow:
- check airflow version;
- test imports;
- parse DAGs / inspect import errors.

dbt:
- dbt --version;
- dbt parse / compile / run as appropriate.

Terraform/OpenTofu:
- tofu validate;
- inspect provider/version constraints.

Do not finish just because Context7 supplied plausible syntax.
