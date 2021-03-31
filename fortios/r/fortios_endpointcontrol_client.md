# fortios_endpointcontrol_client

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
module "fortios_endpointcontrol_client" {
  source = "./modules/fortios/r/fortios_endpointcontrol_client"

  # ad_groups - (optional) is a type of string
  ad_groups = null
  # fosid - (optional) is a type of number
  fosid = null
  # ftcl_uid - (optional) is a type of string
  ftcl_uid = null
  # info - (optional) is a type of string
  info = null
  # src_ip - (optional) is a type of string
  src_ip = null
  # src_mac - (optional) is a type of string
  src_mac = null
}
```

[top](#index)

### Variables

```terraform
variable "ad_groups" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ftcl_uid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "info" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src_mac" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_endpointcontrol_client" "this" {
  ad_groups = var.ad_groups
  fosid     = var.fosid
  ftcl_uid  = var.ftcl_uid
  info      = var.info
  src_ip    = var.src_ip
  src_mac   = var.src_mac
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_endpointcontrol_client.this.fosid
}

output "ftcl_uid" {
  description = "returns a string"
  value       = fortios_endpointcontrol_client.this.ftcl_uid
}

output "id" {
  description = "returns a string"
  value       = fortios_endpointcontrol_client.this.id
}

output "info" {
  description = "returns a string"
  value       = fortios_endpointcontrol_client.this.info
}

output "src_ip" {
  description = "returns a string"
  value       = fortios_endpointcontrol_client.this.src_ip
}

output "src_mac" {
  description = "returns a string"
  value       = fortios_endpointcontrol_client.this.src_mac
}

output "this" {
  value = fortios_endpointcontrol_client.this
}
```

[top](#index)