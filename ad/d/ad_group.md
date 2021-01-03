# ad_group

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
module "ad_group" {
  source = "./modules/ad/d/ad_group"

  # guid - (required) is a type of string
  guid = null
}
```

[top](#index)

### Variables

```terraform
variable "guid" {
  description = "(required) - The GUID of the Group object."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ad_group" "this" {
  guid = var.guid
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a string"
  value       = data.ad_group.this.category
}

output "container" {
  description = "returns a string"
  value       = data.ad_group.this.container
}

output "display_name" {
  description = "returns a string"
  value       = data.ad_group.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.ad_group.this.id
}

output "name" {
  description = "returns a string"
  value       = data.ad_group.this.name
}

output "sam_account_name" {
  description = "returns a string"
  value       = data.ad_group.this.sam_account_name
}

output "scope" {
  description = "returns a string"
  value       = data.ad_group.this.scope
}

output "this" {
  value = ad_group.this
}
```

[top](#index)