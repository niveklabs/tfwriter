# okta_app

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_app" {
  source = "./modules/okta/d/okta_app"

  # active_only - (optional) is a type of bool
  active_only = null
  # label - (optional) is a type of string
  label = null
  # label_prefix - (optional) is a type of string
  label_prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "active_only" {
  description = "(optional) - Search only ACTIVE applications."
  type        = bool
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_app" "this" {
  active_only  = var.active_only
  label        = var.label
  label_prefix = var.label_prefix
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.okta_app.this.description
}

output "id" {
  description = "returns a string"
  value       = data.okta_app.this.id
}

output "name" {
  description = "returns a string"
  value       = data.okta_app.this.name
}

output "status" {
  description = "returns a string"
  value       = data.okta_app.this.status
}

output "this" {
  value = okta_app.this
}
```

[top](#index)