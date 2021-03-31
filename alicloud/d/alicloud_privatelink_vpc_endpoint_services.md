# alicloud_privatelink_vpc_endpoint_services

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
module "alicloud_privatelink_vpc_endpoint_services" {
  source = "./modules/alicloud/d/alicloud_privatelink_vpc_endpoint_services"

  # auto_accept_connection - (optional) is a type of bool
  auto_accept_connection = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # service_business_status - (optional) is a type of string
  service_business_status = null
  # status - (optional) is a type of string
  status = null
  # vpc_endpoint_service_name - (optional) is a type of string
  vpc_endpoint_service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_accept_connection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
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

variable "service_business_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_endpoint_service_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_privatelink_vpc_endpoint_services" "this" {
  auto_accept_connection    = var.auto_accept_connection
  ids                       = var.ids
  name_regex                = var.name_regex
  output_file               = var.output_file
  service_business_status   = var.service_business_status
  status                    = var.status
  vpc_endpoint_service_name = var.vpc_endpoint_service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_privatelink_vpc_endpoint_services.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_privatelink_vpc_endpoint_services.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_privatelink_vpc_endpoint_services.this.names
}

output "services" {
  description = "returns a list of object"
  value       = data.alicloud_privatelink_vpc_endpoint_services.this.services
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_services.this
}
```

[top](#index)