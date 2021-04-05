# scaleway_instance_ip

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
module "scaleway_instance_ip" {
  source = "./modules/scaleway/r/scaleway_instance_ip"

  # project_id - (optional) is a type of string
  project_id = null
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
variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
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
resource "scaleway_instance_ip" "this" {
  project_id = var.project_id
  zone       = var.zone

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
output "address" {
  description = "returns a string"
  value       = scaleway_instance_ip.this.address
}

output "id" {
  description = "returns a string"
  value       = scaleway_instance_ip.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_instance_ip.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_instance_ip.this.project_id
}

output "reverse" {
  description = "returns a string"
  value       = scaleway_instance_ip.this.reverse
}

output "server_id" {
  description = "returns a string"
  value       = scaleway_instance_ip.this.server_id
}

output "zone" {
  description = "returns a string"
  value       = scaleway_instance_ip.this.zone
}

output "this" {
  value = scaleway_instance_ip.this
}
```

[top](#index)