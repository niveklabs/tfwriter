# exoscale_secondary_ipaddress

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_secondary_ipaddress" {
  source = "./modules/exoscale/r/exoscale_secondary_ipaddress"

  # compute_id - (required) is a type of string
  compute_id = null
  # ip_address - (required) is a type of string
  ip_address = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compute_id" {
  description = "(required)"
  type        = string
}

variable "ip_address" {
  description = "(required) - Elastic IP address"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_secondary_ipaddress" "this" {
  compute_id = var.compute_id
  ip_address = var.ip_address

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = exoscale_secondary_ipaddress.this.id
}

output "network_id" {
  description = "returns a string"
  value       = exoscale_secondary_ipaddress.this.network_id
}

output "nic_id" {
  description = "returns a string"
  value       = exoscale_secondary_ipaddress.this.nic_id
}

output "this" {
  value = exoscale_secondary_ipaddress.this
}
```

[top](#index)