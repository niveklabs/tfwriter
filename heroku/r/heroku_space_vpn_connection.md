# heroku_space_vpn_connection

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    heroku = ">= 4.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_space_vpn_connection" {
  source = "./modules/heroku/r/heroku_space_vpn_connection"

  # name - (required) is a type of string
  name = null
  # public_ip - (required) is a type of string
  public_ip = null
  # routable_cidrs - (required) is a type of set of string
  routable_cidrs = []
  # space - (required) is a type of string
  space = null

  timeouts = [{
    create = null
  }]

  tunnels = [{
    ip             = null
    pre_shared_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "public_ip" {
  description = "(required)"
  type        = string
}

variable "routable_cidrs" {
  description = "(required)"
  type        = set(string)
}

variable "space" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}

variable "tunnels" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip             = string
      pre_shared_key = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "heroku_space_vpn_connection" "this" {
  name           = var.name
  public_ip      = var.public_ip
  routable_cidrs = var.routable_cidrs
  space          = var.space

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

  dynamic "tunnels" {
    for_each = var.tunnels
    content {
      ip             = tunnels.value["ip"]
      pre_shared_key = tunnels.value["pre_shared_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_space_vpn_connection.this.id
}

output "ike_version" {
  description = "returns a number"
  value       = heroku_space_vpn_connection.this.ike_version
}

output "space_cidr_block" {
  description = "returns a string"
  value       = heroku_space_vpn_connection.this.space_cidr_block
}

output "this" {
  value = heroku_space_vpn_connection.this
}
```

[top](#index)