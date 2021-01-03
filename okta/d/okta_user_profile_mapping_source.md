# okta_user_profile_mapping_source

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_user_profile_mapping_source" {
  source = "./modules/okta/d/okta_user_profile_mapping_source"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "okta_user_profile_mapping_source" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.okta_user_profile_mapping_source.this.id
}

output "name" {
  description = "returns a string"
  value       = data.okta_user_profile_mapping_source.this.name
}

output "type" {
  description = "returns a string"
  value       = data.okta_user_profile_mapping_source.this.type
}

output "this" {
  value = okta_user_profile_mapping_source.this
}
```

[top](#index)