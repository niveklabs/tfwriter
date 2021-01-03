# consul_prepared_query

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.10.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_prepared_query" {
  source = "./modules/consul/r/consul_prepared_query"

  # connect - (optional) is a type of bool
  connect = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # ignore_check_ids - (optional) is a type of list of string
  ignore_check_ids = []
  # name - (required) is a type of string
  name = null
  # near - (optional) is a type of string
  near = null
  # node_meta - (optional) is a type of map of string
  node_meta = {}
  # only_passing - (optional) is a type of bool
  only_passing = null
  # service - (required) is a type of string
  service = null
  # service_meta - (optional) is a type of map of string
  service_meta = {}
  # session - (optional) is a type of string
  session = null
  # stored_token - (optional) is a type of string
  stored_token = null
  # tags - (optional) is a type of set of string
  tags = []
  # token - (optional) is a type of string
  token = null

  dns = [{
    ttl = null
  }]

  failover = [{
    datacenters = []
    nearest_n   = null
  }]

  template = [{
    regexp = null
    type   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "connect" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_check_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "near" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_meta" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "only_passing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "service" {
  description = "(required)"
  type        = string
}

variable "service_meta" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "session" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stored_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ttl = string
    }
  ))
  default = []
}

variable "failover" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      datacenters = list(string)
      nearest_n   = number
    }
  ))
  default = []
}

variable "template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      regexp = string
      type   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "consul_prepared_query" "this" {
  connect          = var.connect
  datacenter       = var.datacenter
  ignore_check_ids = var.ignore_check_ids
  name             = var.name
  near             = var.near
  node_meta        = var.node_meta
  only_passing     = var.only_passing
  service          = var.service
  service_meta     = var.service_meta
  session          = var.session
  stored_token     = var.stored_token
  tags             = var.tags
  token            = var.token

  dynamic "dns" {
    for_each = var.dns
    content {
      ttl = dns.value["ttl"]
    }
  }

  dynamic "failover" {
    for_each = var.failover
    content {
      datacenters = failover.value["datacenters"]
      nearest_n   = failover.value["nearest_n"]
    }
  }

  dynamic "template" {
    for_each = var.template
    content {
      regexp = template.value["regexp"]
      type   = template.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_prepared_query.this.id
}

output "this" {
  value = consul_prepared_query.this
}
```

[top](#index)