# fortios_firewall_trafficclass

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
module "fortios_firewall_trafficclass" {
  source = "./modules/fortios/r/fortios_firewall_trafficclass"

  # class_id - (optional) is a type of number
  class_id = null
  # class_name - (optional) is a type of string
  class_name = null
}
```

[top](#index)

### Variables

```terraform
variable "class_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "class_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_trafficclass" "this" {
  class_id   = var.class_id
  class_name = var.class_name
}
```

[top](#index)

### Outputs

```terraform
output "class_id" {
  description = "returns a number"
  value       = fortios_firewall_trafficclass.this.class_id
}

output "class_name" {
  description = "returns a string"
  value       = fortios_firewall_trafficclass.this.class_name
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_trafficclass.this.id
}

output "this" {
  value = fortios_firewall_trafficclass.this
}
```

[top](#index)