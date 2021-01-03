# fortios_logwebtrends_setting

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
module "fortios_logwebtrends_setting" {
  source = "./modules/fortios/r/fortios_logwebtrends_setting"

  # server - (optional) is a type of string
  server = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "server" {
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
resource "fortios_logwebtrends_setting" "this" {
  server = var.server
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_logwebtrends_setting.this.id
}

output "server" {
  description = "returns a string"
  value       = fortios_logwebtrends_setting.this.server
}

output "status" {
  description = "returns a string"
  value       = fortios_logwebtrends_setting.this.status
}

output "this" {
  value = fortios_logwebtrends_setting.this
}
```

[top](#index)