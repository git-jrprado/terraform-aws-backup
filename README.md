# terraform-aws-backup

[![Lint Status](https://github.com/DNXLabs/terraform-aws-backup/workflows/Lint/badge.svg)](https://github.com/DNXLabs/terraform-aws-backup/actions)
[![LICENSE](https://img.shields.io/github/license/DNXLabs/terraform-aws-backup)](https://github.com/DNXLabs/terraform-aws-backup/blob/master/LICENSE)

<!--- BEGIN_TF_DOCS --->

## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12.20 |

## Providers

| Name | Version |
|------|---------|
| aws | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| name | Name of the backup vault to create. | `string` | `""` | no |
| rule\_completion\_window | The amount of time AWS Backup attempts a backup before canceling the job and returning an error | `number` | `120` | no |
| rule\_lifecycle\_cold\_storage\_after | Specifies the number of days after creation that a recovery point is moved to cold storage | `number` | `30` | no |
| rule\_lifecycle\_delete\_after | Specifies the number of days after creation that a recovery point is deleted. Must be 90 days greater than `cold_storage_after` | `number` | `120` | no |
| rule\_schedule | A CRON expression specifying when AWS Backup initiates a backup job | `string` | `null` | no |
| rule\_start\_window | The amount of time in minutes before beginning a backup | `number` | `60` | no |
| selection\_resources | An array of strings that either contain Amazon Resource Names (ARNs) or match patterns of resources to assign to a backup plan | `list` | `[]` | no |
| selection\_tag | List of objects with key, type e value to filter resources in selection | `list(object)` | `type="STRINGEQUALS",key="Backup",value="True"` | no |
| vault\_kms\_key\_arn | The server-side encryption key that is used to protect your backups | `string` | `null` | no |

## Outputs

No output.

<!--- END_TF_DOCS --->

## Authors

Module managed by [DNX Solutions](https://github.com/DNXLabs).

## License

Apache 2 Licensed. See [LICENSE](https://github.com/DNXLabs/terraform-aws-backup/blob/master/LICENSE) for full details.
