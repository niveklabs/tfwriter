# fortios_endpointcontrol_forticlientems

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
module "fortios_endpointcontrol_forticlientems" {
  source = "./modules/fortios/r/fortios_endpointcontrol_forticlientems"

  # address - (required) is a type of string
  address = null
  # admin_password - (optional) is a type of string
  admin_password = null
  # admin_type - (optional) is a type of string
  admin_type = null
  # admin_username - (required) is a type of string
  admin_username = null
  # https_port - (optional) is a type of number
  https_port = null
  # listen_port - (optional) is a type of number
  listen_port = null
  # name - (optional) is a type of string
  name = null
  # rest_api_auth - (optional) is a type of string
  rest_api_auth = null
  # serial_number - (required) is a type of string
  serial_number = null
  # upload_port - (optional) is a type of number
  upload_port = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "admin_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_username" {
  description = "(required)"
  type        = string
}

variable "https_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "listen_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rest_api_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "serial_number" {
  description = "(required)"
  type        = string
}

variable "upload_port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_endpointcontrol_forticlientems" "this" {
  address        = var.address
  admin_password = var.admin_password
  admin_type     = var.admin_type
  admin_username = var.admin_username
  https_port     = var.https_port
  listen_port    = var.listen_port
  name           = var.name
  rest_api_auth  = var.rest_api_auth
  serial_number  = var.serial_number
  upload_port    = var.upload_port
}
```

[top](#index)

### Outputs

```terraform
output "admin_type" {
  description = "returns a string"
  value       = fortios_endpointcontrol_forticlientems.this.admin_type
}

output "https_port" {
  description = "returns a number"
  value       = fortios_endpointcontrol_forticlientems.this.https_port
}

output "id" {
  description = "returns a string"
  value       = fortios_endpointcontrol_forticlientems.this.id
}

output "listen_port" {
  description = "returns a number"
  value       = fortios_endpointcontrol_forticlientems.this.listen_port
}

output "name" {
  description = "returns a string"
  value       = fortios_endpointcontrol_forticlientems.this.name
}

output "rest_api_auth" {
  description = "returns a string"
  value       = fortios_endpointcontrol_forticlientems.this.rest_api_auth
}

output "upload_port" {
  description = "returns a number"
  value       = fortios_endpointcontrol_forticlientems.this.upload_port
}

output "this" {
  value = fortios_endpointcontrol_forticlientems.this
}
```

[top](#index)