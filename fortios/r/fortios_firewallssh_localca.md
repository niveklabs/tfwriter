# fortios_firewallssh_localca

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewallssh_localca" {
  source = null

  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # private_key - (required) is a type of string
  private_key = null
  # public_key - (required) is a type of string
  public_key = null
  # source - (optional) is a type of string
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(required)"
  type        = string
}

variable "public_key" {
  description = "(required)"
  type        = string
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallssh_localca" "this" {
  # name - (optional) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # private_key - (required) is a type of string
  private_key = var.private_key
  # public_key - (required) is a type of string
  public_key = var.public_key
  # source - (optional) is a type of string
  source = var.source
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewallssh_localca.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallssh_localca.this.name
}

output "source" {
  description = "returns a string"
  value       = fortios_firewallssh_localca.this.source
}

output "this" {
  value = fortios_firewallssh_localca.this
}
```

[top](#index)