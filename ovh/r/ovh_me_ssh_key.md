# ovh_me_ssh_key

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_ssh_key" {
  source = "./modules/ovh/r/ovh_me_ssh_key"

  # default - (optional) is a type of bool
  default = null
  # key - (required) is a type of string
  key = null
  # key_name - (required) is a type of string
  key_name = null
}
```

[top](#index)

### Variables

```terraform
variable "default" {
  description = "(optional) - True when this public Ssh key is used for rescue mode and reinstallations"
  type        = bool
  default     = null
}

variable "key" {
  description = "(required) - ASCII encoded public Ssh key"
  type        = string
}

variable "key_name" {
  description = "(required) - Name of this public Ssh key"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_me_ssh_key" "this" {
  # default - (optional) is a type of bool
  default = var.default
  # key - (required) is a type of string
  key = var.key
  # key_name - (required) is a type of string
  key_name = var.key_name
}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a bool"
  value       = ovh_me_ssh_key.this.default
}

output "id" {
  description = "returns a string"
  value       = ovh_me_ssh_key.this.id
}

output "this" {
  value = ovh_me_ssh_key.this
}
```

[top](#index)