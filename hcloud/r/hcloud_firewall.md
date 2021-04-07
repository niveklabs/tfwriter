# hcloud_firewall

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_firewall" {
  source = "./modules/hcloud/r/hcloud_firewall"

  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null

  rule = [{
    destination_ips = []
    direction       = null
    port            = null
    protocol        = null
    source_ips      = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      destination_ips = set(string)
      direction       = string
      port            = string
      protocol        = string
      source_ips      = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_firewall" "this" {
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name

  dynamic "rule" {
    for_each = var.rule
    content {
      # destination_ips - (optional) is a type of set of string
      destination_ips = rule.value["destination_ips"]
      # direction - (required) is a type of string
      direction = rule.value["direction"]
      # port - (optional) is a type of string
      port = rule.value["port"]
      # protocol - (required) is a type of string
      protocol = rule.value["protocol"]
      # source_ips - (optional) is a type of set of string
      source_ips = rule.value["source_ips"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_firewall.this.id
}

output "this" {
  value = hcloud_firewall.this
}
```

[top](#index)