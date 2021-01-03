# fortios_waf_signature

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_waf_signature" {
  source = "./modules/fortios/r/fortios_waf_signature"

  # desc - (optional) is a type of string
  desc = null
  # fosid - (optional) is a type of number
  fosid = null
}
```

[top](#index)

### Variables

```terraform
variable "desc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_waf_signature" "this" {
  desc  = var.desc
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "desc" {
  description = "returns a string"
  value       = fortios_waf_signature.this.desc
}

output "fosid" {
  description = "returns a number"
  value       = fortios_waf_signature.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_waf_signature.this.id
}

output "this" {
  value = fortios_waf_signature.this
}
```

[top](#index)