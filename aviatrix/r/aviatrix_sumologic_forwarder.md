# aviatrix_sumologic_forwarder

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_sumologic_forwarder" {
  source = "./modules/aviatrix/r/aviatrix_sumologic_forwarder"

  # access_id - (required) is a type of string
  access_id = null
  # access_key - (required) is a type of string
  access_key = null
  # custom_configuration - (optional) is a type of string
  custom_configuration = null
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = []
  # source_category - (optional) is a type of string
  source_category = null
}
```

[top](#index)

### Variables

```terraform
variable "access_id" {
  description = "(required) - Access ID."
  type        = string
}

variable "access_key" {
  description = "(required) - Access key."
  type        = string
}

variable "custom_configuration" {
  description = "(optional) - Custom configuration."
  type        = string
  default     = null
}

variable "excluded_gateways" {
  description = "(optional) - List of excluded gateways."
  type        = set(string)
  default     = null
}

variable "source_category" {
  description = "(optional) - Source category."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_sumologic_forwarder" "this" {
  # access_id - (required) is a type of string
  access_id = var.access_id
  # access_key - (required) is a type of string
  access_key = var.access_key
  # custom_configuration - (optional) is a type of string
  custom_configuration = var.custom_configuration
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = var.excluded_gateways
  # source_category - (optional) is a type of string
  source_category = var.source_category
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_sumologic_forwarder.this.id
}

output "status" {
  description = "returns a string"
  value       = aviatrix_sumologic_forwarder.this.status
}

output "this" {
  value = aviatrix_sumologic_forwarder.this
}
```

[top](#index)