# akamai_groups

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_groups" {
  source = "./modules/akamai/d/akamai_groups"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_groups" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.akamai_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.akamai_groups.this.id
}

output "this" {
  value = akamai_groups.this
}
```

[top](#index)