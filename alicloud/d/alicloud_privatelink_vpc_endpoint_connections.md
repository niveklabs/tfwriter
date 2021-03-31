# alicloud_privatelink_vpc_endpoint_connections

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
module "alicloud_privatelink_vpc_endpoint_connections" {
  source = "./modules/alicloud/d/alicloud_privatelink_vpc_endpoint_connections"

  # endpoint_id - (optional) is a type of string
  endpoint_id = null
  # endpoint_owner_id - (optional) is a type of number
  endpoint_owner_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # service_id - (required) is a type of string
  service_id = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_owner_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_id" {
  description = "(required)"
  type        = string
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
data "alicloud_privatelink_vpc_endpoint_connections" "this" {
  endpoint_id       = var.endpoint_id
  endpoint_owner_id = var.endpoint_owner_id
  output_file       = var.output_file
  service_id        = var.service_id
  status            = var.status
}
```

[top](#index)

### Outputs

```terraform
output "connections" {
  description = "returns a list of object"
  value       = data.alicloud_privatelink_vpc_endpoint_connections.this.connections
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_privatelink_vpc_endpoint_connections.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_privatelink_vpc_endpoint_connections.this.ids
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_connections.this
}
```

[top](#index)