# dome9_continuous_compliance_policy

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
module "dome9_continuous_compliance_policy" {
  source = "./modules/dome9/d/dome9_continuous_compliance_policy"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "dome9_continuous_compliance_policy" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.dome9_continuous_compliance_policy.this.id
}

output "notification_ids" {
  description = "returns a list of string"
  value       = data.dome9_continuous_compliance_policy.this.notification_ids
}

output "ruleset_id" {
  description = "returns a number"
  value       = data.dome9_continuous_compliance_policy.this.ruleset_id
}

output "target_external_id" {
  description = "returns a string"
  value       = data.dome9_continuous_compliance_policy.this.target_external_id
}

output "target_internal_id" {
  description = "returns a string"
  value       = data.dome9_continuous_compliance_policy.this.target_internal_id
}

output "target_type" {
  description = "returns a string"
  value       = data.dome9_continuous_compliance_policy.this.target_type
}

output "this" {
  value = dome9_continuous_compliance_policy.this
}
```

[top](#index)