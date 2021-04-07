# ovh_vrack_iploadbalancing

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_vrack_iploadbalancing" {
  source = "./modules/ovh/r/ovh_vrack_iploadbalancing"

  # ip_loadbalancing - (required) is a type of string
  ip_loadbalancing = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_loadbalancing" {
  description = "(required) - Your ipLoadbalancing"
  type        = string
}

variable "service_name" {
  description = "(required) - The internal name of your vrack"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_vrack_iploadbalancing" "this" {
  # ip_loadbalancing - (required) is a type of string
  ip_loadbalancing = var.ip_loadbalancing
  # service_name - (required) is a type of string
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_vrack_iploadbalancing.this.id
}

output "this" {
  value = ovh_vrack_iploadbalancing.this
}
```

[top](#index)