# fortios_switchcontrollerptp_policy

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
module "fortios_switchcontrollerptp_policy" {
  source = "./modules/fortios/r/fortios_switchcontrollerptp_policy"

  # name - (optional) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
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

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerptp_policy" "this" {
  name   = var.name
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerptp_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontrollerptp_policy.this.name
}

output "status" {
  description = "returns a string"
  value       = fortios_switchcontrollerptp_policy.this.status
}

output "this" {
  value = fortios_switchcontrollerptp_policy.this
}
```

[top](#index)