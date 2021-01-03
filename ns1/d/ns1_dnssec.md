# ns1_dnssec

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_dnssec" {
  source = "./modules/ns1/d/ns1_dnssec"

  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ns1_dnssec" "this" {
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "delegation" {
  description = "returns a list of object"
  value       = data.ns1_dnssec.this.delegation
}

output "id" {
  description = "returns a string"
  value       = data.ns1_dnssec.this.id
}

output "keys" {
  description = "returns a list of object"
  value       = data.ns1_dnssec.this.keys
}

output "this" {
  value = ns1_dnssec.this
}
```

[top](#index)