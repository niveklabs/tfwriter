# dome9_cloudaccount_aws

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloudaccount_aws" {
  source = "./modules/dome9/d/dome9_cloudaccount_aws"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "dome9_cloudaccount_aws" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "allow_read_only" {
  description = "returns a bool"
  value       = data.dome9_cloudaccount_aws.this.allow_read_only
}

output "creation_date" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_aws.this.creation_date
}

output "external_account_number" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_aws.this.external_account_number
}

output "full_protection" {
  description = "returns a bool"
  value       = data.dome9_cloudaccount_aws.this.full_protection
}

output "iam_safe" {
  description = "returns a set of object"
  value       = data.dome9_cloudaccount_aws.this.iam_safe
}

output "id" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_aws.this.id
}

output "is_fetching_suspended" {
  description = "returns a bool"
  value       = data.dome9_cloudaccount_aws.this.is_fetching_suspended
}

output "name" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_aws.this.name
}

output "net_sec" {
  description = "returns a set of object"
  value       = data.dome9_cloudaccount_aws.this.net_sec
}

output "organizational_unit_id" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_aws.this.organizational_unit_id
}

output "vendor" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_aws.this.vendor
}

output "this" {
  value = dome9_cloudaccount_aws.this
}
```

[top](#index)