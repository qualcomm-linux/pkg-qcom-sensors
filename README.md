# pkg-sensors

This repository contains the Debian packaging for Qualcomm Sensors prebuilt binaries within the Qualcomm Linux ecosystem. It provides the essential structure and configuration necessary to integrate with the [qcom-build-utils](https://github.com/qualcomm-linux/qcom-build-utils) repository, enabling standardized Debian package building processes.

## Packages

This repository produces the following Debian packages from prebuilt binaries:

| Package | Version | Description |
|---------|---------|-------------|
| `qcom-sensors-api` | 1.0.2 | Qualcomm Sensors API library |
| `qcom-sensors-core` | 1.0.2 | Qualcomm Sensors core library |
| `qcom-sensors-registry` | 1.0.2 | Qualcomm Sensors registry service |
| `qcom-sensors-services` | 1.0.4 | Qualcomm Sensors services daemon |
| `qcom-sensors-test-core` | 1.0.2 | Qualcomm Sensors test core library |
| `qcom-sensors-test-apps` | 1.0.2 | Qualcomm Sensors test applications |

## Prebuilt Source

Individual per-package tarballs are also available in the same directory:
- `qcom-sensors-api_1.0.2_arm64.tar.gz`
- `qcom-sensors-core_1.0.2_arm64.tar.gz`
- `qcom-sensors-registry_1.0.2_arm64.tar.gz`
- `qcom-sensors-services_1.0.4_arm64.tar.gz`
- `qcom-sensors-test-apps_1.0.2_arm64.tar.gz`
- `qcom-sensors-test-core_1.0.2_arm64.tar.gz`

## Repository Structure

```
pkg-sensors/
├── debian/
│   ├── changelog        # Package version history
│   ├── control          # Package metadata and dependencies
│   ├── copyright        # License information
│   ├── rules            # Build rules (installs prebuilt files)
│   └── source/
│       ├── format       # Debian source format (3.0 quilt)
│       └── options      # Source build options
├── upstream.conf        # Prebuilt tarball location configuration
├── LICENSE.txt
├── README.md
├── CONTRIBUTING.md
├── SECURITY.md
└── CODE-OF-CONDUCT.md
```

## Building

The `debian/rules` file extracts prebuilt binaries from the tarball and installs them into the appropriate package staging directories under `data/<package-name>/arm64/`.

## Branches

- **main**: Primary branch containing workflow logic and documentation.
- **qcom/ubuntu/***: Orphan branch containing the `debian/` packaging files.

## Workflows

The `main` branch includes the following workflows in the `.github/workflows/` directory:

- **qcom-preflight-checks.yml**: Sanity check workflow.
- **stale-issues.yml**: Workflow for managing stale issues.
- **build-debian-package.yml**: Builds the Debian packages.
- **pr-pre-post-merge.yml**: Executes during PR and after merge.
- **promote-upstream.yml**: Promotes the package to a new upstream release.

## License

pkg-sensors is licensed under the [BSD-3-Clause License](https://spdx.org/licenses/BSD-3-Clause.html). See [LICENSE.txt](LICENSE.txt) for the full license text.
