# terraform-aws-kms

[![Terraform Version](https://img.shields.io/badge/Terraform%20Version->=0.13.0,<0.13.7-blue.svg)](https://releases.hashicorp.com/terraform/)
[![Release](https://img.shields.io/github/release/traveloka/terraform-aws-kms.svg)](https://github.com/traveloka/terraform-aws-kms/releases)
[![Last Commit](https://img.shields.io/github/last-commit/traveloka/terraform-aws-kms.svg)](https://github.com/traveloka/terraform-aws-kms/commits/master)
[![Issues](https://img.shields.io/github/issues/traveloka/terraform-aws-kms.svg)](https://github.com/traveloka/terraform-aws-kms/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/traveloka/terraform-aws-kms.svg)](https://github.com/traveloka/terraform-aws-kms/pulls)
[![License](https://img.shields.io/github/license/traveloka/terraform-aws-kms.svg)](https://github.com/traveloka/terraform-aws-kms/blob/master/LICENSE)
![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)

## Table of Content


## Description

Terraform module which creates a KMS Customer Master Key (CMK) and its alias.


## Prerequisites



## Dependencies

This Terraform module have no dependencies to another modules


## Getting Started

### Usage
```hcl
module "cmk_key" {
  source  = "github.com/traveloka/terraform-aws-kms-cmk?ref=v0.1.0"

  product_domain          = "bei"
  alias_name              = "secret-parameter"
  environment             = "production"
  description             = "Key to encrypt and decrypt secret parameters"
  key_policy              = "${data.aws_iam_policy_document.cmk_key_policy.json}"
}
```

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_iam_role.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_caller_identity.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_environment"></a> [environment](#input\_environment) | Will be used in Environment tag | `string` | n/a | yes |
| <a name="input_product_domain"></a> [product\_domain](#input\_product\_domain) | Abbreviation of the product domain the created resources belong to | `string` | n/a | yes |
| <a name="input_region"></a> [region](#input\_region) | The region from which this module will be executed | `string` | `"ap-southeast-1"` | no |
| <a name="input_role_assume_policy"></a> [role\_assume\_policy](#input\_role\_assume\_policy) | IAM policy document that grants an entity permission to assume the role in JSON format. | `string` | n/a | yes |
| <a name="input_role_description"></a> [role\_description](#input\_role\_description) | The description of the role. | `string` | n/a | yes |
| <a name="input_role_force_detach_policies"></a> [role\_force\_detach\_policies](#input\_role\_force\_detach\_policies) | Specifies to force detaching any policies the role has before destroying it. | `bool` | `false` | no |
| <a name="input_role_max_session_duration"></a> [role\_max\_session\_duration](#input\_role\_max\_session\_duration) | The maximum session duration (in seconds) that you want to set for the specified role. If you do not specify a value for this setting, the default maximum of one hour is applied. This setting can have a value from 1 hour to 12 hours. | `number` | `3600` | no |
| <a name="input_role_name"></a> [role\_name](#input\_role\_name) | The name of the role. It will forces new resource on change. | `string` | n/a | yes |
| <a name="input_role_path"></a> [role\_path](#input\_role\_path) | The path to the role. See https://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html for more information. | `string` | `"/"` | no |
| <a name="input_role_permission_boundary"></a> [role\_permission\_boundary](#input\_role\_permission\_boundary) | IAM policy ARN limiting the maximum access this role can have | `string` | `""` | no |
| <a name="input_role_tags"></a> [role\_tags](#input\_role\_tags) | Additional tags to be put on iam role | `map(string)` | `{}` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_aws_account_id"></a> [aws\_account\_id](#output\_aws\_account\_id) | The AWS Account ID number of the account that owns or contains the calling entity. |
| <a name="output_aws_caller_arn"></a> [aws\_caller\_arn](#output\_aws\_caller\_arn) | The AWS ARN associated with the calling entity. |
| <a name="output_aws_caller_user_id"></a> [aws\_caller\_user\_id](#output\_aws\_caller\_user\_id) | The unique identifier of the calling entity. |
| <a name="output_role_arn"></a> [role\_arn](#output\_role\_arn) | The Amazon Resource Name (ARN) specifying the role. |
| <a name="output_role_create_date"></a> [role\_create\_date](#output\_role\_create\_date) | The creation date of the IAM role. |
| <a name="output_role_description"></a> [role\_description](#output\_role\_description) | The description of the role. |
| <a name="output_role_name"></a> [role\_name](#output\_role\_name) | The name of the role. |
| <a name="output_role_unique_id"></a> [role\_unique\_id](#output\_role\_unique\_id) | The stable and unique string identifying the role. |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->


## Contributing

This module accepting or open for any contributions from anyone, please see the [CONTRIBUTING.md](https://github.com/traveloka/terraform-aws-kms/blob/master/CONTRIBUTING.md) for more detail about how to contribute to this module.

## License

This module is under Apache License 2.0 - see the [LICENSE](https://github.com/traveloka/terraform-aws-kms/blob/master/LICENSE) file for details.