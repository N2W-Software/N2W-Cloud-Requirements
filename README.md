# N2W Backup & Recovery: minimum cloud permissions

The minimum permissions N2W Backup & Recovery needs in each cloud, for every version since 4.5.0:
AWS IAM policies, Azure and Azure Government custom roles, and GCP custom roles.

## Download

Open [Releases](../../releases) and pick your N2W version; the newest is under
[Latest](../../releases/latest). Each release carries:

| File | Contents |
|---|---|
| `N2W-<version>-AWS-permissions.zip` | IAM policies per edition, and the DR account policies |
| `N2W-<version>-Azure-permissions.zip` | the custom role per edition |
| `N2W-<version>-Azure-Gov-permissions.zip` | the custom role per edition, for Azure Government |
| `N2W-<version>-GCP-permissions.zip` | the custom role per edition, and the grants it cannot carry |
| `N2W-<version>-minimum-permissions.zip` | all of the above |

Every zip has a README with instructions and the permissions added and removed since the previous
version. The release notes list the same changes.

## Versions

The history of `main` starts with the LICENSE, then this README. After them, each N2W version is
one commit, tagged with the version (`5.0.2`), whose parent is the previous version. To see what
changed between any two versions, compare their tags, for example
[`4.6.2...5.0.2`](../../compare/4.6.2...5.0.2).

If a published version is corrected, its commit and tag are replaced and its release is rebuilt
under the same address.

## Layout

| Path | Contents |
|---|---|
| `aws/` | `aws_policy_permissions_<Edition>_<n>.json`: one customer managed policy per file |
| `aws/dr-account/` | `basic_dr_permissions.json`, `secured_dr_account_permissions.json` |
| `azure/`, `azure-gov/` | `azure[_gov]_policy_permissions_<Edition>_1.json`: the custom role definition |
| `gcp/` | `gcp_iam_permissions_<Edition>_1.yaml`: the custom role |
| `VERSION` | the N2W version this commit holds |

Editions are `Standard`, `Advanced` and `Enterprise_BYOL`. The Free edition has not been offered since
4.4.0, so its files are not published.

This repository is generated from the N2W product source, and changes made here are overwritten.
For help, contact [N2W support](https://support.n2ws.com).

© N2W Software, Inc. All rights reserved. See [LICENSE](LICENSE).
