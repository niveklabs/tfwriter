# fortios_system_ips

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
module "fortios_system_ips" {
  source = "./modules/fortios/r/fortios_system_ips"

  # override_signature_hold_by_id - (optional) is a type of string
  override_signature_hold_by_id = null
  # signature_hold_time - (optional) is a type of string
  signature_hold_time = null
}
```

[top](#index)

### Variables

```terraform
variable "override_signature_hold_by_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signature_hold_time" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ips" "this" {
  override_signature_hold_by_id = var.override_signature_hold_by_id
  signature_hold_time           = var.signature_hold_time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_ips.this.id
}

output "override_signature_hold_by_id" {
  description = "returns a string"
  value       = fortios_system_ips.this.override_signature_hold_by_id
}

output "signature_hold_time" {
  description = "returns a string"
  value       = fortios_system_ips.this.signature_hold_time
}

output "this" {
  value = fortios_system_ips.this
}
```

[top](#index)