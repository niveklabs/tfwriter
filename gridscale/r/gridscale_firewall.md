# gridscale_firewall

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.8.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_firewall" {
  source = "./modules/gridscale/r/gridscale_firewall"

  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null

  rules_v4_in = [{
    action   = null
    comment  = null
    dst_cidr = null
    dst_port = null
    order    = null
    protocol = null
    src_cidr = null
    src_port = null
  }]

  rules_v4_out = [{
    action   = null
    comment  = null
    dst_cidr = null
    dst_port = null
    order    = null
    protocol = null
    src_cidr = null
    src_port = null
  }]

  rules_v6_in = [{
    action   = null
    comment  = null
    dst_cidr = null
    dst_port = null
    order    = null
    protocol = null
    src_cidr = null
    src_port = null
  }]

  rules_v6_out = [{
    action   = null
    comment  = null
    dst_cidr = null
    dst_port = null
    order    = null
    protocol = null
    src_cidr = null
    src_port = null
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
variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters"
  type        = string
}

variable "rules_v4_in" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      comment  = string
      dst_cidr = string
      dst_port = string
      order    = number
      protocol = string
      src_cidr = string
      src_port = string
    }
  ))
  default = []
}

variable "rules_v4_out" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      comment  = string
      dst_cidr = string
      dst_port = string
      order    = number
      protocol = string
      src_cidr = string
      src_port = string
    }
  ))
  default = []
}

variable "rules_v6_in" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      comment  = string
      dst_cidr = string
      dst_port = string
      order    = number
      protocol = string
      src_cidr = string
      src_port = string
    }
  ))
  default = []
}

variable "rules_v6_out" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      comment  = string
      dst_cidr = string
      dst_port = string
      order    = number
      protocol = string
      src_cidr = string
      src_port = string
    }
  ))
  default = []
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
resource "gridscale_firewall" "this" {
  labels = var.labels
  name   = var.name

  dynamic "rules_v4_in" {
    for_each = var.rules_v4_in
    content {
      action   = rules_v4_in.value["action"]
      comment  = rules_v4_in.value["comment"]
      dst_cidr = rules_v4_in.value["dst_cidr"]
      dst_port = rules_v4_in.value["dst_port"]
      order    = rules_v4_in.value["order"]
      protocol = rules_v4_in.value["protocol"]
      src_cidr = rules_v4_in.value["src_cidr"]
      src_port = rules_v4_in.value["src_port"]
    }
  }

  dynamic "rules_v4_out" {
    for_each = var.rules_v4_out
    content {
      action   = rules_v4_out.value["action"]
      comment  = rules_v4_out.value["comment"]
      dst_cidr = rules_v4_out.value["dst_cidr"]
      dst_port = rules_v4_out.value["dst_port"]
      order    = rules_v4_out.value["order"]
      protocol = rules_v4_out.value["protocol"]
      src_cidr = rules_v4_out.value["src_cidr"]
      src_port = rules_v4_out.value["src_port"]
    }
  }

  dynamic "rules_v6_in" {
    for_each = var.rules_v6_in
    content {
      action   = rules_v6_in.value["action"]
      comment  = rules_v6_in.value["comment"]
      dst_cidr = rules_v6_in.value["dst_cidr"]
      dst_port = rules_v6_in.value["dst_port"]
      order    = rules_v6_in.value["order"]
      protocol = rules_v6_in.value["protocol"]
      src_cidr = rules_v6_in.value["src_cidr"]
      src_port = rules_v6_in.value["src_port"]
    }
  }

  dynamic "rules_v6_out" {
    for_each = var.rules_v6_out
    content {
      action   = rules_v6_out.value["action"]
      comment  = rules_v6_out.value["comment"]
      dst_cidr = rules_v6_out.value["dst_cidr"]
      dst_port = rules_v6_out.value["dst_port"]
      order    = rules_v6_out.value["order"]
      protocol = rules_v6_out.value["protocol"]
      src_cidr = rules_v6_out.value["src_cidr"]
      src_port = rules_v6_out.value["src_port"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = gridscale_firewall.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_firewall.this.create_time
}

output "description" {
  description = "returns a string"
  value       = gridscale_firewall.this.description
}

output "id" {
  description = "returns a string"
  value       = gridscale_firewall.this.id
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_firewall.this.location_name
}

output "network" {
  description = "returns a set of object"
  value       = gridscale_firewall.this.network
}

output "private" {
  description = "returns a bool"
  value       = gridscale_firewall.this.private
}

output "status" {
  description = "returns a string"
  value       = gridscale_firewall.this.status
}

output "this" {
  value = gridscale_firewall.this
}
```

[top](#index)