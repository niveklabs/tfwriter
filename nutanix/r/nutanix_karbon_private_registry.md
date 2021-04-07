# nutanix_karbon_private_registry

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
module "nutanix_karbon_private_registry" {
  source = "./modules/nutanix/r/nutanix_karbon_private_registry"

  # cert - (optional) is a type of string
  cert = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # port - (required) is a type of number
  port = null
  # url - (required) is a type of string
  url = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_karbon_private_registry" "this" {
  # cert - (optional) is a type of string
  cert = var.cert
  # name - (required) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # port - (required) is a type of number
  port = var.port
  # url - (required) is a type of string
  url = var.url
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "endpoint" {
  description = "returns a string"
  value       = nutanix_karbon_private_registry.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = nutanix_karbon_private_registry.this.id
}

output "this" {
  value = nutanix_karbon_private_registry.this
}
```

[top](#index)