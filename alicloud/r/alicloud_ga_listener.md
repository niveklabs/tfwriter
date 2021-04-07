# alicloud_ga_listener

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
module "alicloud_ga_listener" {
  source = "./modules/alicloud/r/alicloud_ga_listener"

  # accelerator_id - (required) is a type of string
  accelerator_id = null
  # client_affinity - (optional) is a type of string
  client_affinity = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # protocol - (optional) is a type of string
  protocol = null
  # proxy_protocol - (optional) is a type of bool
  proxy_protocol = null

  certificates = [{
    id = null
  }]

  port_ranges = [{
    from_port = null
    to_port   = null
  }]

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
variable "accelerator_id" {
  description = "(required)"
  type        = string
}

variable "client_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_protocol" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "certificates" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = string
    }
  ))
  default = []
}

variable "port_ranges" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      from_port = number
      to_port   = number
    }
  ))
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
resource "alicloud_ga_listener" "this" {
  # accelerator_id - (required) is a type of string
  accelerator_id = var.accelerator_id
  # client_affinity - (optional) is a type of string
  client_affinity = var.client_affinity
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # proxy_protocol - (optional) is a type of bool
  proxy_protocol = var.proxy_protocol

  dynamic "certificates" {
    for_each = var.certificates
    content {
      # id - (optional) is a type of string
      id = certificates.value["id"]
    }
  }

  dynamic "port_ranges" {
    for_each = var.port_ranges
    content {
      # from_port - (required) is a type of number
      from_port = port_ranges.value["from_port"]
      # to_port - (required) is a type of number
      to_port = port_ranges.value["to_port"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ga_listener.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ga_listener.this.status
}

output "this" {
  value = alicloud_ga_listener.this
}
```

[top](#index)