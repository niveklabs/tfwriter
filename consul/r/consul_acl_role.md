# consul_acl_role

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
module "consul_acl_role" {
  source = "./modules/consul/r/consul_acl_role"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # policies - (optional) is a type of set of string
  policies = []

  service_identities = [{
    datacenters  = []
    service_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A free form human readable description of the role."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the ACL role."
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policies" {
  description = "(optional) - The list of policies that should be applied to the role."
  type        = set(string)
  default     = null
}

variable "service_identities" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      datacenters  = set(string)
      service_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "consul_acl_role" "this" {
  description = var.description
  name        = var.name
  namespace   = var.namespace
  policies    = var.policies

  dynamic "service_identities" {
    for_each = var.service_identities
    content {
      datacenters  = service_identities.value["datacenters"]
      service_name = service_identities.value["service_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_acl_role.this.id
}

output "this" {
  value = consul_acl_role.this
}
```

[top](#index)