# alicloud_privatelink_vpc_endpoints

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_privatelink_vpc_endpoints" {
  source = "./modules/alicloud/d/alicloud_privatelink_vpc_endpoints"

  # connection_status - (optional) is a type of string
  connection_status = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # service_name - (optional) is a type of string
  service_name = null
  # status - (optional) is a type of string
  status = null
  # vpc_endpoint_name - (optional) is a type of string
  vpc_endpoint_name = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_details" {
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

variable "service_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_endpoint_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_privatelink_vpc_endpoints" "this" {
  connection_status = var.connection_status
  enable_details    = var.enable_details
  ids               = var.ids
  name_regex        = var.name_regex
  output_file       = var.output_file
  service_name      = var.service_name
  status            = var.status
  vpc_endpoint_name = var.vpc_endpoint_name
  vpc_id            = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "endpoints" {
  description = "returns a list of object"
  value       = data.alicloud_privatelink_vpc_endpoints.this.endpoints
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_privatelink_vpc_endpoints.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_privatelink_vpc_endpoints.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_privatelink_vpc_endpoints.this.names
}

output "this" {
  value = alicloud_privatelink_vpc_endpoints.this
}
```

[top](#index)