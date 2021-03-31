# hcloud_firewall

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/hcloud/d/hcloud_firewall"

  # labels - (optional) is a type of map of string
  labels = {}
  # most_recent - (optional) is a type of bool
  most_recent = null
  # name - (optional) is a type of string
  name = null
  # with_selector - (optional) is a type of string
  with_selector = null

  rule = [{
    direction  = null
    port       = null
    protocol   = null
    source_ips = []
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

variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_selector" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      direction  = string
      port       = string
      protocol   = string
      source_ips = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_firewall" "this" {
  labels        = var.labels
  most_recent   = var.most_recent
  name          = var.name
  with_selector = var.with_selector

  dynamic "rule" {
    for_each = var.rule
    content {
      direction  = rule.value["direction"]
      port       = rule.value["port"]
      protocol   = rule.value["protocol"]
      source_ips = rule.value["source_ips"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a number"
  value       = data.hcloud_firewall.this.id
}

output "name" {
  description = "returns a string"
  value       = data.hcloud_firewall.this.name
}

output "this" {
  value = hcloud_firewall.this
}
```

[top](#index)