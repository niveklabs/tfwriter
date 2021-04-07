# tencentcloud_alb_server_attachment

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_alb_server_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_alb_server_attachment"

  # listener_id - (required) is a type of string
  listener_id = null
  # loadbalancer_id - (required) is a type of string
  loadbalancer_id = null
  # location_id - (optional) is a type of string
  location_id = null

  backends = [{
    instance_id = null
    port        = null
    weight      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "listener_id" {
  description = "(required) - listener ID."
  type        = string
}

variable "loadbalancer_id" {
  description = "(required) - loadbalancer ID."
  type        = string
}

variable "location_id" {
  description = "(optional) - location ID, only support for layer 7 loadbalancer."
  type        = string
  default     = null
}

variable "backends" {
  description = "nested block: NestingSet, min items: 1, max items: 100"
  type = set(object(
    {
      instance_id = string
      port        = number
      weight      = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_alb_server_attachment" "this" {
  listener_id     = var.listener_id
  loadbalancer_id = var.loadbalancer_id
  location_id     = var.location_id

  dynamic "backends" {
    for_each = var.backends
    content {
      instance_id = backends.value["instance_id"]
      port        = backends.value["port"]
      weight      = backends.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_alb_server_attachment.this.id
}

output "location_id" {
  description = "returns a string"
  value       = tencentcloud_alb_server_attachment.this.location_id
}

output "protocol_type" {
  description = "returns a string"
  value       = tencentcloud_alb_server_attachment.this.protocol_type
}

output "this" {
  value = tencentcloud_alb_server_attachment.this
}
```

[top](#index)