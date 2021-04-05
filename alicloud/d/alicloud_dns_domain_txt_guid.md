# alicloud_dns_domain_txt_guid

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_dns_domain_txt_guid" {
  source = "./modules/alicloud/d/alicloud_dns_domain_txt_guid"

  # domain_name - (required) is a type of string
  domain_name = null
  # lang - (optional) is a type of string
  lang = null
  # output_file - (optional) is a type of string
  output_file = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_dns_domain_txt_guid" "this" {
  domain_name = var.domain_name
  lang        = var.lang
  output_file = var.output_file
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_dns_domain_txt_guid.this.id
}

output "rr" {
  description = "returns a string"
  value       = data.alicloud_dns_domain_txt_guid.this.rr
}

output "value" {
  description = "returns a string"
  value       = data.alicloud_dns_domain_txt_guid.this.value
}

output "this" {
  value = alicloud_dns_domain_txt_guid.this
}
```

[top](#index)