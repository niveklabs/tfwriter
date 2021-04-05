# alicloud_fc_custom_domains

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
module "alicloud_fc_custom_domains" {
  source = "./modules/alicloud/d/alicloud_fc_custom_domains"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_fc_custom_domains" "this" {
  ids         = var.ids
  name_regex  = var.name_regex
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "domains" {
  description = "returns a list of object"
  value       = data.alicloud_fc_custom_domains.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_fc_custom_domains.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_fc_custom_domains.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_fc_custom_domains.this.names
}

output "this" {
  value = alicloud_fc_custom_domains.this
}
```

[top](#index)