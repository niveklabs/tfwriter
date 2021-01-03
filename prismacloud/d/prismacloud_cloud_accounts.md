# prismacloud_cloud_accounts

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
module "prismacloud_cloud_accounts" {
  source = "./modules/prismacloud/d/prismacloud_cloud_accounts"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "prismacloud_cloud_accounts" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.prismacloud_cloud_accounts.this.id
}

output "listing" {
  description = "returns a list of object"
  value       = data.prismacloud_cloud_accounts.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.prismacloud_cloud_accounts.this.total
}

output "this" {
  value = prismacloud_cloud_accounts.this
}
```

[top](#index)