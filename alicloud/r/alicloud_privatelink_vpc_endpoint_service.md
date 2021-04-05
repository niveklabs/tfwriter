# alicloud_privatelink_vpc_endpoint_service

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_privatelink_vpc_endpoint_service" {
  source = "./modules/alicloud/r/alicloud_privatelink_vpc_endpoint_service"

  # auto_accept_connection - (optional) is a type of bool
  auto_accept_connection = null
  # connect_bandwidth - (optional) is a type of number
  connect_bandwidth = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # payer - (optional) is a type of string
  payer = null
  # service_description - (optional) is a type of string
  service_description = null

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
variable "auto_accept_connection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "connect_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "payer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_description" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "alicloud_privatelink_vpc_endpoint_service" "this" {
  auto_accept_connection = var.auto_accept_connection
  connect_bandwidth      = var.connect_bandwidth
  dry_run                = var.dry_run
  payer                  = var.payer
  service_description    = var.service_description

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
output "connect_bandwidth" {
  description = "returns a number"
  value       = alicloud_privatelink_vpc_endpoint_service.this.connect_bandwidth
}

output "id" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_service.this.id
}

output "service_business_status" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_service.this.service_business_status
}

output "service_domain" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_service.this.service_domain
}

output "status" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_service.this.status
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_service.this
}
```

[top](#index)