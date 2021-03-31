# exoscale_security_group_rules

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_security_group_rules" {
  source = "./modules/exoscale/r/exoscale_security_group_rules"

  # security_group - (optional) is a type of string
  security_group = null
  # security_group_id - (optional) is a type of string
  security_group_id = null

  egress = [{
    cidr_list                = []
    description              = null
    icmp_code                = null
    icmp_type                = null
    ids                      = []
    ports                    = []
    protocol                 = null
    user_security_group_list = []
  }]

  ingress = [{
    cidr_list                = []
    description              = null
    icmp_code                = null
    icmp_type                = null
    ids                      = []
    ports                    = []
    protocol                 = null
    user_security_group_list = []
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "security_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "egress" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cidr_list                = set(string)
      description              = string
      icmp_code                = number
      icmp_type                = number
      ids                      = set(string)
      ports                    = set(string)
      protocol                 = string
      user_security_group_list = set(string)
    }
  ))
  default = []
}

variable "ingress" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cidr_list                = set(string)
      description              = string
      icmp_code                = number
      icmp_type                = number
      ids                      = set(string)
      ports                    = set(string)
      protocol                 = string
      user_security_group_list = set(string)
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
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_security_group_rules" "this" {
  security_group    = var.security_group
  security_group_id = var.security_group_id

  dynamic "egress" {
    for_each = var.egress
    content {
      cidr_list                = egress.value["cidr_list"]
      description              = egress.value["description"]
      icmp_code                = egress.value["icmp_code"]
      icmp_type                = egress.value["icmp_type"]
      ports                    = egress.value["ports"]
      protocol                 = egress.value["protocol"]
      user_security_group_list = egress.value["user_security_group_list"]
    }
  }

  dynamic "ingress" {
    for_each = var.ingress
    content {
      cidr_list                = ingress.value["cidr_list"]
      description              = ingress.value["description"]
      icmp_code                = ingress.value["icmp_code"]
      icmp_type                = ingress.value["icmp_type"]
      ports                    = ingress.value["ports"]
      protocol                 = ingress.value["protocol"]
      user_security_group_list = ingress.value["user_security_group_list"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
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
  value       = exoscale_security_group_rules.this.id
}

output "security_group" {
  description = "returns a string"
  value       = exoscale_security_group_rules.this.security_group
}

output "security_group_id" {
  description = "returns a string"
  value       = exoscale_security_group_rules.this.security_group_id
}

output "this" {
  value = exoscale_security_group_rules.this
}
```

[top](#index)