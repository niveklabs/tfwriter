# ad_user

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_user" {
  source = "./modules/ad/d/ad_user"

  # guid - (required) is a type of string
  guid = null
}
```

[top](#index)

### Variables

```terraform
variable "guid" {
  description = "(required) - The GUID of the user object."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ad_user" "this" {
  guid = var.guid
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.ad_user.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.ad_user.this.id
}

output "principal_name" {
  description = "returns a string"
  value       = data.ad_user.this.principal_name
}

output "sam_account_name" {
  description = "returns a string"
  value       = data.ad_user.this.sam_account_name
}

output "this" {
  value = ad_user.this
}
```

[top](#index)