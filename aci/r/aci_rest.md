# aci_rest

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_rest" {
  source = "./modules/aci/r/aci_rest"

  # class_name - (optional) is a type of string
  class_name = null
  # content - (optional) is a type of map of string
  content = {}
  # path - (required) is a type of string
  path = null
  # payload - (optional) is a type of string
  payload = null
}
```

[top](#index)

### Variables

```terraform
variable "class_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "payload" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_rest" "this" {
  class_name = var.class_name
  content    = var.content
  path       = var.path
  payload    = var.payload
}
```

[top](#index)

### Outputs

```terraform
output "class_name" {
  description = "returns a string"
  value       = aci_rest.this.class_name
}

output "dn" {
  description = "returns a string"
  value       = aci_rest.this.dn
}

output "id" {
  description = "returns a string"
  value       = aci_rest.this.id
}

output "this" {
  value = aci_rest.this
}
```

[top](#index)