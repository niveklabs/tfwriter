# vault_audit

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_audit" {
  source = "./modules/vault/r/vault_audit"

  # description - (optional) is a type of string
  description = null
  # local - (optional) is a type of bool
  local = null
  # options - (required) is a type of map of string
  options = {}
  # path - (optional) is a type of string
  path = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Human-friendly description of the audit device."
  type        = string
  default     = null
}

variable "local" {
  description = "(optional) - Specifies if the audit device is a local only. Local audit devices are not replicated nor (if a secondary) removed by replication."
  type        = bool
  default     = null
}

variable "options" {
  description = "(required) - Configuration options to pass to the audit device itself."
  type        = map(string)
}

variable "path" {
  description = "(optional) - Path in which to enable the audit device."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Type of the audit device, such as 'file'."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_audit" "this" {
  description = var.description
  local       = var.local
  options     = var.options
  path        = var.path
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_audit.this.id
}

output "path" {
  description = "returns a string"
  value       = vault_audit.this.path
}

output "this" {
  value = vault_audit.this
}
```

[top](#index)