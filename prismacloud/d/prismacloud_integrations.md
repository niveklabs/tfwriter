# prismacloud_integrations

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.0.8"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_integrations" {
  source = "./modules/prismacloud/d/prismacloud_integrations"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "prismacloud_integrations" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.prismacloud_integrations.this.id
}

output "listing" {
  description = "returns a list of object"
  value       = data.prismacloud_integrations.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.prismacloud_integrations.this.total
}

output "this" {
  value = prismacloud_integrations.this
}
```

[top](#index)