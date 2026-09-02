# ENTICE nomenclature definitions

Nomenclature definitions for the ENTICE project (additions or overrides to common-definitions)

## Purpose and connection with other repositories

This repository contains codelists for the ENTICE project that are
compatible with the `nomenclature-iamc` Python package. It is intended to be
used, like the sibling
[`transience-nomenclature-definitions`](https://github.com/TRANSIENCE-MIC3/transience-nomenclature-definitions)
and
[`iamcompact-nomenclature-definitions`](https://github.com/i2amparis/iamcompact-nomenclature-definitions)
repositories, by the packages
[`nomenclature-adapter`](https://github.com/i2amparis/nomenclature-adapter) and
[`validation-ui`](https://github.com/i2amparis/validation-ui) for validating
model, scenario, variable and region names and units, and for defining
aggregation mappings between regions, via an `entice` validation profile. No
such profile has been added to `nomenclature-adapter` yet (see "Current
status" below).

Definitions of variables in this repository come in addition to or override
ones given in the official
[`common-definitions`](https://github.com/IAMconsortium/common-definitions)
repository maintained by the IAMconsortium.

## Organization

Codelist definitions are stored in the `/definitions/` folder, and region
mappings in the `/mappings/` folder, like for any `nomenclature` definitions
repository.

Each of these folders contain a subfolder named `common-definitions-overrides`,
which contains definitions that override existing definitions in
`common-definitions`. These subfolders generally mirror the subfolder structures
and file names in the `common-definitions` repository. Files and subfolders
outside of `common-definitions-overrides` are additional definitions that are
not present in `common-definitions`.

## Current status

This is a first scaffold of the repository, seeded with the generic
variable-definition additions that are shared between the TRANSIENCE and
IAM COMPACT nomenclature-definitions repositories (climate, energy prices,
macro-economy GDP/revenue overrides, population, techno-economic, and the
`common-definitions-tags` codelist tags), plus generic (non-project-specific)
region definitions (`common.yaml`, `countries.yaml`, `organizations.yaml`).

Deliberately **not yet** included, and left for follow-up work once the
relevant project details are known:

- **Vetting checks**: no sectoral validation or harmonization check is
  defined here yet (unlike `transience-nomenclature-definitions`'
  `vetting/` folder or `iamcompact-nomenclature-definitions`'
  `vetting/gdp_pop_harmonization.yaml`).
- **IAM COMPACT-specific content**, such as the GCAM native-region
  definitions and region mappings (`definitions/region/native_regions/` and
  `mappings/`) used in the TRANSIENCE/IAM COMPACT repositories -- these are
  tied to models used in those projects, not ENTICE.
- **ENTICE-specific model and scenario names**: `definitions/model/entice_models.yaml`
  and `definitions/scenario/entice_scenarios.yaml` are present but empty;
  see the `README.md` files in `definitions/model/` and
  `definitions/scenario/` for naming guidelines.
- A `nomenclature-adapter` profile (`profiles/entice.yaml`) pointing at this
  repository -- this repository is not yet wired into `nomenclature-adapter`
  or `validation-ui`.
