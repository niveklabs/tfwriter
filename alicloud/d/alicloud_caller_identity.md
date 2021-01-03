# alicloud_caller_identity

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_caller_identity" {
  source = "./modules/alicloud/d/alicloud_caller_identity"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "alicloud_caller_identity" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = data.alicloud_caller_identity.this.account_id
}

output "arn" {
  description = "returns a string"
  value       = data.alicloud_caller_identity.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_caller_identity.this.id
}

output "identity_type" {
  description = "returns a string"
  value       = data.alicloud_caller_identity.this.identity_type
}

output "this" {
  value = alicloud_caller_identity.this
}
```

[top](#index)