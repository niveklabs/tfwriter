# profitbricks_server

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_server" {
  source = "./modules/profitbricks/d/profitbricks_server"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # name - (optional) is a type of string
  name = null

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
variable "datacenter_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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
data "profitbricks_server" "this" {
  datacenter_id = var.datacenter_id
  name          = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = data.profitbricks_server.this.availability_zone
}

output "boot_cdrom" {
  description = "returns a string"
  value       = data.profitbricks_server.this.boot_cdrom
}

output "boot_volume" {
  description = "returns a string"
  value       = data.profitbricks_server.this.boot_volume
}

output "cdroms" {
  description = "returns a list of object"
  value       = data.profitbricks_server.this.cdroms
}

output "cores" {
  description = "returns a number"
  value       = data.profitbricks_server.this.cores
}

output "cpu_family" {
  description = "returns a string"
  value       = data.profitbricks_server.this.cpu_family
}

output "id" {
  description = "returns a string"
  value       = data.profitbricks_server.this.id
}

output "nics" {
  description = "returns a list of object"
  value       = data.profitbricks_server.this.nics
}

output "ram" {
  description = "returns a number"
  value       = data.profitbricks_server.this.ram
}

output "vm_state" {
  description = "returns a string"
  value       = data.profitbricks_server.this.vm_state
}

output "volumes" {
  description = "returns a list of object"
  value       = data.profitbricks_server.this.volumes
}

output "this" {
  value = profitbricks_server.this
}
```

[top](#index)