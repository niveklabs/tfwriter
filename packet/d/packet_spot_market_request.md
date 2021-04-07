# packet_spot_market_request

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_spot_market_request" {
  source = "./modules/packet/d/packet_spot_market_request"

  # request_id - (required) is a type of string
  request_id = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "request_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "packet_spot_market_request" "this" {
  # request_id - (required) is a type of string
  request_id = var.request_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
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
output "device_ids" {
  description = "returns a list of string"
  value       = data.packet_spot_market_request.this.device_ids
}

output "id" {
  description = "returns a string"
  value       = data.packet_spot_market_request.this.id
}

output "this" {
  value = packet_spot_market_request.this
}
```

[top](#index)