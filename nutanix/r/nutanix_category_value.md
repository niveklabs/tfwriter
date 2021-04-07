# nutanix_category_value

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_category_value" {
  source = "./modules/nutanix/r/nutanix_category_value"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_category_value" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # value - (required) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_category_value.this.api_version
}

output "description" {
  description = "returns a string"
  value       = nutanix_category_value.this.description
}

output "id" {
  description = "returns a string"
  value       = nutanix_category_value.this.id
}

output "system_defined" {
  description = "returns a bool"
  value       = nutanix_category_value.this.system_defined
}

output "this" {
  value = nutanix_category_value.this
}
```

[top](#index)