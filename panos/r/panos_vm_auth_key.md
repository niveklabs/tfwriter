# panos_vm_auth_key

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_vm_auth_key" {
  source = "./modules/panos/r/panos_vm_auth_key"

  # hours - (optional) is a type of number
  hours = null
}
```

[top](#index)

### Variables

```terraform
variable "hours" {
  description = "(optional) - The VM auth key lifetime"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_vm_auth_key" "this" {
  # hours - (optional) is a type of number
  hours = var.hours
}
```

[top](#index)

### Outputs

```terraform
output "auth_key" {
  description = "returns a string"
  value       = panos_vm_auth_key.this.auth_key
}

output "expiry" {
  description = "returns a string"
  value       = panos_vm_auth_key.this.expiry
}

output "id" {
  description = "returns a string"
  value       = panos_vm_auth_key.this.id
}

output "valid" {
  description = "returns a bool"
  value       = panos_vm_auth_key.this.valid
}

output "this" {
  value = panos_vm_auth_key.this
}
```

[top](#index)