# alicloud_ram_saml_providers

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_saml_providers" {
  source = "./modules/alicloud/d/alicloud_ram_saml_providers"

  # enable_details - (optional) is a type of bool
  enable_details = null
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
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

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
data "alicloud_ram_saml_providers" "this" {
  enable_details = var.enable_details
  ids            = var.ids
  name_regex     = var.name_regex
  output_file    = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ram_saml_providers.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ram_saml_providers.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ram_saml_providers.this.names
}

output "providers" {
  description = "returns a list of object"
  value       = data.alicloud_ram_saml_providers.this.providers
}

output "this" {
  value = alicloud_ram_saml_providers.this
}
```

[top](#index)