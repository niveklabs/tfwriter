# scaleway_instance_ip_reverse_dns

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_instance_ip_reverse_dns" {
  source = "./modules/scaleway/r/scaleway_instance_ip_reverse_dns"

  # ip_id - (required) is a type of string
  ip_id = null
  # reverse - (required) is a type of string
  reverse = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ip_id" {
  description = "(required) - The IP ID or IP address"
  type        = string
}

variable "reverse" {
  description = "(required) - The reverse DNS for this IP"
  type        = string
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_instance_ip_reverse_dns" "this" {
  ip_id   = var.ip_id
  reverse = var.reverse
  zone    = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = scaleway_instance_ip_reverse_dns.this.id
}

output "zone" {
  description = "returns a string"
  value       = scaleway_instance_ip_reverse_dns.this.zone
}

output "this" {
  value = scaleway_instance_ip_reverse_dns.this
}
```

[top](#index)