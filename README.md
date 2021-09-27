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
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.12 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_kms_alias.key_alias](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/kms_alias) | resource |
| [aws_kms_key.key](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/kms_key) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_additional_tags"></a> [additional\_tags](#input\_additional\_tags) | Additional tags to be added to kms-cmk | `map(string)` | `{}` | no |
| <a name="input_alias_name"></a> [alias\_name](#input\_alias\_name) | The name of the key alias | `string` | n/a | yes |
| <a name="input_deletion_window_in_days"></a> [deletion\_window\_in\_days](#input\_deletion\_window\_in\_days) | The duration in days after which the key is deleted after destruction of the resource | `string` | `30` | no |
| <a name="input_description"></a> [description](#input\_description) | The description of this KMS key | `string` | n/a | yes |
| <a name="input_environment"></a> [environment](#input\_environment) | The environment this KMS key belongs to | `string` | n/a | yes |
| <a name="input_key_policy"></a> [key\_policy](#input\_key\_policy) | The policy of the key usage | `string` | `""` | no |
| <a name="input_product_domain"></a> [product\_domain](#input\_product\_domain) | The name of the product domain | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_key_alias_arn"></a> [key\_alias\_arn](#output\_key\_alias\_arn) | The arn of the key alias |
| <a name="output_key_alias_name"></a> [key\_alias\_name](#output\_key\_alias\_name) | The name of the key alias |
| <a name="output_key_arn"></a> [key\_arn](#output\_key\_arn) | The arn of the key |
| <a name="output_key_id"></a> [key\_id](#output\_key\_id) | The globally unique identifier for the key |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->


## Contributing

This module accepting or open for any contributions from anyone, please see the [CONTRIBUTING.md](https://github.com/traveloka/terraform-aws-kms/blob/master/CONTRIBUTING.md) for more detail about how to contribute to this module.

## License

This module is under Apache License 2.0 - see the [LICENSE](https://github.com/traveloka/terraform-aws-kms/blob/master/LICENSE) file for details.