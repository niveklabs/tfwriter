# alicloud_network_acl_entries

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_network_acl_entries" {
  source = "./modules/alicloud/r/alicloud_network_acl_entries"

  # network_acl_id - (required) is a type of string
  network_acl_id = null

  egress = [{
    description         = null
    destination_cidr_ip = null
    entry_type          = null
    name                = null
    policy              = null
    port                = null
    protocol            = null
  }]

  ingress = [{
    description    = null
    entry_type     = null
    name           = null
    policy         = null
    port           = null
    protocol       = null
    source_cidr_ip = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "network_acl_id" {
  description = "(required)"
  type        = string
}

variable "egress" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description         = string
      destination_cidr_ip = string
      entry_type          = string
      name                = string
      policy              = string
      port                = string
      protocol            = string
    }
  ))
  default = []
}

variable "ingress" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description    = string
      entry_type     = string
      name           = string
      policy         = string
      port           = string
      protocol       = string
      source_cidr_ip = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_network_acl_entries" "this" {
  # network_acl_id - (required) is a type of string
  network_acl_id = var.network_acl_id

  dynamic "egress" {
    for_each = var.egress
    content {
      # description - (optional) is a type of string
      description = egress.value["description"]
      # destination_cidr_ip - (optional) is a type of string
      destination_cidr_ip = egress.value["destination_cidr_ip"]
      # entry_type - (optional) is a type of string
      entry_type = egress.value["entry_type"]
      # name - (optional) is a type of string
      name = egress.value["name"]
      # policy - (optional) is a type of string
      policy = egress.value["policy"]
      # port - (optional) is a type of string
      port = egress.value["port"]
      # protocol - (optional) is a type of string
      protocol = egress.value["protocol"]
    }
  }

  dynamic "ingress" {
    for_each = var.ingress
    content {
      # description - (optional) is a type of string
      description = ingress.value["description"]
      # entry_type - (optional) is a type of string
      entry_type = ingress.value["entry_type"]
      # name - (optional) is a type of string
      name = ingress.value["name"]
      # policy - (optional) is a type of string
      policy = ingress.value["policy"]
      # port - (optional) is a type of string
      port = ingress.value["port"]
      # protocol - (optional) is a type of string
      protocol = ingress.value["protocol"]
      # source_cidr_ip - (optional) is a type of string
      source_cidr_ip = ingress.value["source_cidr_ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_network_acl_entries.this.id
}

output "this" {
  value = alicloud_network_acl_entries.this
}
```

[top](#index)