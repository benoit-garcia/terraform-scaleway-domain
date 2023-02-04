# Terraform / Scaleway

## Purpose

This repository is used to manage a domain on scaleway using terraform.

## Usage

- Setup the [scaleway provider](https://www.terraform.io/docs/providers/scaleway/index.html) in your tf file.
- Include this module in your tf file. Refer to [documentation](https://www.terraform.io/docs/modules/sources.html#generic-git-repository).

```hcl
module "my_domain" {
  source  = "scaleway-terraform-modules/domain/scaleway"
  version = "0.0.2"

}
```

<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement_terraform) | >= 0.13 |
| <a name="requirement_scaleway"></a> [scaleway](#requirement_scaleway) | >= 2.6.0 |

## Resources

| Name | Type |
|------|------|
| [scaleway_domain_record.dkim](https://registry.terraform.io/providers/scaleway/scaleway/latest/docs/resources/domain_record) | resource |
| [scaleway_domain_record.mx](https://registry.terraform.io/providers/scaleway/scaleway/latest/docs/resources/domain_record) | resource |
| [scaleway_domain_record.spf](https://registry.terraform.io/providers/scaleway/scaleway/latest/docs/resources/domain_record) | resource |
| [scaleway_domain_zone.this](https://registry.terraform.io/providers/scaleway/scaleway/latest/docs/resources/domain_zone) | resource |
| [scaleway_tem_domain.this](https://registry.terraform.io/providers/scaleway/scaleway/latest/docs/resources/tem_domain) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_domain"></a> [domain](#input_domain) | n/a | `string` | n/a | yes |
| <a name="input_mx_servers"></a> [mx_servers](#input_mx_servers) | n/a | ```list(object({ address = string priority = number }))``` | ```[ { "address": ".", "priority": 0 } ]``` | no |
| <a name="input_project_id"></a> [project_id](#input_project_id) | ID of the project the domain is associated with. Ressource will be created in the region set by the provider if null. | `string` | `"null"` | no |
| <a name="input_region"></a> [region](#input_region) | Region in which the domain should be created. Ressource will be created in the region set by the provider if null. | `string` | `"null"` | no |
| <a name="input_setup_tem"></a> [setup_tem](#input_setup_tem) | n/a | `bool` | `false` | no |
| <a name="input_subdomain"></a> [subdomain](#input_subdomain) | n/a | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_dns_zone"></a> [dns_zone](#output_dns_zone) | DNS Zone of the domain. |
| <a name="output_tem_id"></a> [tem_id](#output_tem_id) | ID of the Transaction Email Domain. |
| <a name="output_tem_status"></a> [tem_status](#output_tem_status) | Status of the Transaction Email Domain. |
<!-- END_TF_DOCS -->

## Authors

Module is maintained with help from [the community](https://github.com/scaleway-terraform-modules/terraform-scaleway-domain/graphs/contributors).

## License

Mozilla Public License 2.0 Licensed. See [LICENSE](https://github.com/scaleway-terraform-modules/.github/tree/master/LICENSE) for full details.
