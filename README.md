# pkg-qcom-sensors

This repository contains the Debian packaging for Qualcomm Sensors prebuilt
binaries within the Qualcomm Linux ecosystem. It integrates with
[qcom-build-utils](https://github.com/qualcomm-linux/qcom-build-utils) for
standardized Debian package building.

## Packages

This repository produces the following Debian packages from prebuilt binaries:

| Package | Description |
|---------|-------------|
| `qcom-sensors-api` | Qualcomm Sensors API runtime libraries |
| `qcom-sensors-api-dev` | Qualcomm Sensors API development files |
| `qcom-sensors-test-core` | Qualcomm Sensors test core runtime libraries |
| `qcom-sensors-test-core-dev` | Qualcomm Sensors test core development files |
| `qcom-sensors-test-apps` | Qualcomm Sensors test applications |

## Repository Structure

```
pkg-qcom-sensors/
├── debian/
│   ├── changelog        # Package version history
│   ├── control          # Package metadata and dependencies
│   ├── copyright        # License information
│   ├── rules            # Build rules (installs prebuilt files)
│   ├── watch            # Upstream tarball location (Artifactory)
│   └── source/
│       ├── format       # Debian source format (3.0 quilt)
│       └── options      # Source build options
└── .github/
    └── workflows/       # CI/CD workflows

```

## Branches

- `qli/debian/latest` — packaging for Debian forky (Debusine path)
- `qli/debian/trixie` — packaging for Debian trixie (Debusine path)
- `qcom/ubuntu/resolute` — packaging for Ubuntu resolute (local builder path)

## License

Licensed under the [BSD-3-Clause-Clear License](LICENSE.txt).
