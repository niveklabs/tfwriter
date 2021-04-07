# profitbricks_k8s_cluster

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "profitbricks_k8s_cluster" {
  source = "./modules/profitbricks/r/profitbricks_k8s_cluster"

  # k8s_version - (optional) is a type of string
  k8s_version = null
  # name - (required) is a type of string
  name = null

  maintenance_window = [{
    day_of_the_week = null
    time            = null
  }]

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
variable "k8s_version" {
  description = "(optional) - The desired kubernetes version"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The desired name for the cluster"
  type        = string
}

variable "maintenance_window" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      day_of_the_week = string
      time            = string
    }
  ))
  default = []
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

### Resource

```terraform
resource "profitbricks_k8s_cluster" "this" {
  # k8s_version - (optional) is a type of string
  k8s_version = var.k8s_version
  # name - (required) is a type of string
  name = var.name

  dynamic "maintenance_window" {
    for_each = var.maintenance_window
    content {
      # day_of_the_week - (required) is a type of string
      day_of_the_week = maintenance_window.value["day_of_the_week"]
      # time - (required) is a type of string
      time = maintenance_window.value["time"]
    }
  }

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
output "id" {
  description = "returns a string"
  value       = profitbricks_k8s_cluster.this.id
}

output "this" {
  value = profitbricks_k8s_cluster.this
}
```

[top](#index)