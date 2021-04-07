# consul_acl_token

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_acl_token" {
  source = "./modules/consul/d/consul_acl_token"

  # accessor_id - (required) is a type of string
  accessor_id = null
  # description - (optional) is a type of string
  description = null
  # local - (optional) is a type of bool
  local = null
  # namespace - (optional) is a type of string
  namespace = null

  policies = [{
    id   = null
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accessor_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policies" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "consul_acl_token" "this" {
  # accessor_id - (required) is a type of string
  accessor_id = var.accessor_id
  # description - (optional) is a type of string
  description = var.description
  # local - (optional) is a type of bool
  local = var.local
  # namespace - (optional) is a type of string
  namespace = var.namespace

  dynamic "policies" {
    for_each = var.policies
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.consul_acl_token.this.id
}

output "this" {
  value = consul_acl_token.this
}
```

[top](#index)