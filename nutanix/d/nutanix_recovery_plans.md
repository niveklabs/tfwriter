# nutanix_recovery_plans

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_recovery_plans" {
  source = "./modules/nutanix/d/nutanix_recovery_plans"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nutanix_recovery_plans" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_recovery_plans.this.api_version
}

output "entities" {
  description = "returns a list of object"
  value       = data.nutanix_recovery_plans.this.entities
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_recovery_plans.this.id
}

output "this" {
  value = nutanix_recovery_plans.this
}
```

[top](#index)