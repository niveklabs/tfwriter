# cloudflare_api_token_permission_groups

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_api_token_permission_groups" {
  source = "./modules/cloudflare/d/cloudflare_api_token_permission_groups"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "cloudflare_api_token_permission_groups" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.cloudflare_api_token_permission_groups.this.id
}

output "permissions" {
  description = "returns a map of string"
  value       = data.cloudflare_api_token_permission_groups.this.permissions
}

output "this" {
  value = cloudflare_api_token_permission_groups.this
}
```

[top](#index)