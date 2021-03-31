# digitalocean_firewall

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "digitalocean_firewall" {
  source = "./modules/digitalocean/d/digitalocean_firewall"

  # droplet_ids - (optional) is a type of set of number
  droplet_ids = []
  # firewall_id - (required) is a type of string
  firewall_id = null
  # tags - (optional) is a type of set of string
  tags = []

  inbound_rule = [{
    port_range                = null
    protocol                  = null
    source_addresses          = []
    source_droplet_ids        = []
    source_load_balancer_uids = []
    source_tags               = []
  }]

  outbound_rule = [{
    destination_addresses          = []
    destination_droplet_ids        = []
    destination_load_balancer_uids = []
    destination_tags               = []
    port_range                     = null
    protocol                       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "droplet_ids" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "firewall_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "inbound_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      port_range                = string
      protocol                  = string
      source_addresses          = set(string)
      source_droplet_ids        = set(number)
      source_load_balancer_uids = set(string)
      source_tags               = set(string)
    }
  ))
  default = []
}

variable "outbound_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      destination_addresses          = set(string)
      destination_droplet_ids        = set(number)
      destination_load_balancer_uids = set(string)
      destination_tags               = set(string)
      port_range                     = string
      protocol                       = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_firewall" "this" {
  droplet_ids = var.droplet_ids
  firewall_id = var.firewall_id
  tags        = var.tags

  dynamic "inbound_rule" {
    for_each = var.inbound_rule
    content {
      port_range                = inbound_rule.value["port_range"]
      protocol                  = inbound_rule.value["protocol"]
      source_addresses          = inbound_rule.value["source_addresses"]
      source_droplet_ids        = inbound_rule.value["source_droplet_ids"]
      source_load_balancer_uids = inbound_rule.value["source_load_balancer_uids"]
      source_tags               = inbound_rule.value["source_tags"]
    }
  }

  dynamic "outbound_rule" {
    for_each = var.outbound_rule
    content {
      destination_addresses          = outbound_rule.value["destination_addresses"]
      destination_droplet_ids        = outbound_rule.value["destination_droplet_ids"]
      destination_load_balancer_uids = outbound_rule.value["destination_load_balancer_uids"]
      destination_tags               = outbound_rule.value["destination_tags"]
      port_range                     = outbound_rule.value["port_range"]
      protocol                       = outbound_rule.value["protocol"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.digitalocean_firewall.this.created_at
}

output "droplet_ids" {
  description = "returns a set of number"
  value       = data.digitalocean_firewall.this.droplet_ids
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_firewall.this.id
}

output "name" {
  description = "returns a string"
  value       = data.digitalocean_firewall.this.name
}

output "pending_changes" {
  description = "returns a list of object"
  value       = data.digitalocean_firewall.this.pending_changes
}

output "status" {
  description = "returns a string"
  value       = data.digitalocean_firewall.this.status
}

output "tags" {
  description = "returns a set of string"
  value       = data.digitalocean_firewall.this.tags
}

output "this" {
  value = digitalocean_firewall.this
}
```

[top](#index)