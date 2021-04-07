# oci_dns_resolver_endpoints

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_resolver_endpoints" {
  source = "./modules/oci/d/oci_dns_resolver_endpoints"

  # name - (optional) is a type of string
  name = null
  # resolver_id - (required) is a type of string
  resolver_id = null
  # scope - (required) is a type of string
  scope = null
  # state - (optional) is a type of string
  state = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolver_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_dns_resolver_endpoints" "this" {
  name        = var.name
  resolver_id = var.resolver_id
  scope       = var.scope
  state       = var.state

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoints.this.id
}

output "resolver_endpoints" {
  description = "returns a list of object"
  value       = data.oci_dns_resolver_endpoints.this.resolver_endpoints
}

output "this" {
  value = oci_dns_resolver_endpoints.this
}
```

[top](#index)