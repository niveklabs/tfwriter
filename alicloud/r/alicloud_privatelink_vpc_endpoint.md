# alicloud_privatelink_vpc_endpoint

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_privatelink_vpc_endpoint" {
  source = "./modules/alicloud/r/alicloud_privatelink_vpc_endpoint"

  # dry_run - (optional) is a type of bool
  dry_run = null
  # endpoint_description - (optional) is a type of string
  endpoint_description = null
  # security_group_ids - (required) is a type of set of string
  security_group_ids = []
  # service_id - (optional) is a type of string
  service_id = null
  # service_name - (optional) is a type of string
  service_name = null
  # vpc_endpoint_name - (optional) is a type of string
  vpc_endpoint_name = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "endpoint_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(required)"
  type        = set(string)
}

variable "service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
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
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_privatelink_vpc_endpoint" "this" {
  dry_run              = var.dry_run
  endpoint_description = var.endpoint_description
  security_group_ids   = var.security_group_ids
  service_id           = var.service_id
  service_name         = var.service_name
  vpc_endpoint_name    = var.vpc_endpoint_name
  vpc_id               = var.vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bandwidth" {
  description = "returns a number"
  value       = alicloud_privatelink_vpc_endpoint.this.bandwidth
}

output "connection_status" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint.this.connection_status
}

output "endpoint_business_status" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint.this.endpoint_business_status
}

output "endpoint_domain" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint.this.endpoint_domain
}

output "id" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint.this.id
}

output "service_name" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint.this.service_name
}

output "status" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint.this.status
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint.this
}
```

[top](#index)