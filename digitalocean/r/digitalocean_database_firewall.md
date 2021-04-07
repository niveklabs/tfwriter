# digitalocean_database_firewall

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_database_firewall" {
  source = "./modules/digitalocean/r/digitalocean_database_firewall"

  # cluster_id - (required) is a type of string
  cluster_id = null

  rule = [{
    created_at = null
    type       = null
    uuid       = null
    value      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      created_at = string
      type       = string
      uuid       = string
      value      = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_database_firewall" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id

  dynamic "rule" {
    for_each = var.rule
    content {
      # type - (required) is a type of string
      type = rule.value["type"]
      # value - (required) is a type of string
      value = rule.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_database_firewall.this.id
}

output "this" {
  value = digitalocean_database_firewall.this
}
```

[top](#index)