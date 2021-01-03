# dome9_cloudaccount_azure

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
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloudaccount_azure" {
  source = "./modules/dome9/d/dome9_cloudaccount_azure"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "dome9_cloudaccount_azure" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "creation_date" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.id
}

output "name" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.name
}

output "operation_mode" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.operation_mode
}

output "organizational_unit_id" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.organizational_unit_id
}

output "organizational_unit_name" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.organizational_unit_name
}

output "organizational_unit_path" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.organizational_unit_path
}

output "subscription_id" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.subscription_id
}

output "tenant_id" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.tenant_id
}

output "vendor" {
  description = "returns a string"
  value       = data.dome9_cloudaccount_azure.this.vendor
}

output "this" {
  value = dome9_cloudaccount_azure.this
}
```

[top](#index)