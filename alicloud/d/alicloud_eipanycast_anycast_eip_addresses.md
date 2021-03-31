# alicloud_eipanycast_anycast_eip_addresses

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_eipanycast_anycast_eip_addresses" {
  source = "./modules/alicloud/d/alicloud_eipanycast_anycast_eip_addresses"

  # anycast_eip_address_name - (optional) is a type of string
  anycast_eip_address_name = null
  # bind_instance_ids - (optional) is a type of set of string
  bind_instance_ids = []
  # business_status - (optional) is a type of string
  business_status = null
  # ids - (optional) is a type of list of string
  ids = []
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # payment_type - (optional) is a type of string
  payment_type = null
  # service_location - (optional) is a type of string
  service_location = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "anycast_eip_address_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bind_instance_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "business_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "internet_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_location" {
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

### Datasource

```terraform
data "alicloud_eipanycast_anycast_eip_addresses" "this" {
  anycast_eip_address_name = var.anycast_eip_address_name
  bind_instance_ids        = var.bind_instance_ids
  business_status          = var.business_status
  ids                      = var.ids
  internet_charge_type     = var.internet_charge_type
  ip_address               = var.ip_address
  name_regex               = var.name_regex
  output_file              = var.output_file
  payment_type             = var.payment_type
  service_location         = var.service_location
  status                   = var.status
}
```

[top](#index)

### Outputs

```terraform
output "addresses" {
  description = "returns a list of object"
  value       = data.alicloud_eipanycast_anycast_eip_addresses.this.addresses
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_eipanycast_anycast_eip_addresses.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_eipanycast_anycast_eip_addresses.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_eipanycast_anycast_eip_addresses.this.names
}

output "this" {
  value = alicloud_eipanycast_anycast_eip_addresses.this
}
```

[top](#index)