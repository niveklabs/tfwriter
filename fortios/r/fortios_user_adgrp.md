# fortios_user_adgrp

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
module "fortios_user_adgrp" {
  source = "./modules/fortios/r/fortios_user_adgrp"

  # connector_source - (optional) is a type of string
  connector_source = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (required) is a type of string
  name = null
  # server_name - (optional) is a type of string
  server_name = null
}
```

[top](#index)

### Variables

```terraform
variable "connector_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "server_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_adgrp" "this" {
  # connector_source - (optional) is a type of string
  connector_source = var.connector_source
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # name - (required) is a type of string
  name = var.name
  # server_name - (optional) is a type of string
  server_name = var.server_name
}
```

[top](#index)

### Outputs

```terraform
output "connector_source" {
  description = "returns a string"
  value       = fortios_user_adgrp.this.connector_source
}

output "fosid" {
  description = "returns a number"
  value       = fortios_user_adgrp.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_user_adgrp.this.id
}

output "server_name" {
  description = "returns a string"
  value       = fortios_user_adgrp.this.server_name
}

output "this" {
  value = fortios_user_adgrp.this
}
```

[top](#index)