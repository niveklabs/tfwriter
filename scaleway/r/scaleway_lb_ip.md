# scaleway_lb_ip

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
module "scaleway_lb_ip" {
  source = "./modules/scaleway/r/scaleway_lb_ip"

  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null
  # reverse - (optional) is a type of string
  reverse = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "reverse" {
  description = "(optional) - The reverse domain name for this IP"
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
resource "scaleway_lb_ip" "this" {
  project_id = var.project_id
  region     = var.region
  reverse    = var.reverse

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
  value       = scaleway_lb_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = scaleway_lb_ip.this.ip_address
}

output "lb_id" {
  description = "returns a string"
  value       = scaleway_lb_ip.this.lb_id
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_lb_ip.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_lb_ip.this.project_id
}

output "region" {
  description = "returns a string"
  value       = scaleway_lb_ip.this.region
}

output "reverse" {
  description = "returns a string"
  value       = scaleway_lb_ip.this.reverse
}

output "this" {
  value = scaleway_lb_ip.this
}
```

[top](#index)