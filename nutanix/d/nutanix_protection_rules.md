# nutanix_protection_rules

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
module "nutanix_protection_rules" {
  source = "./modules/nutanix/d/nutanix_protection_rules"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nutanix_protection_rules" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_protection_rules.this.api_version
}

output "entities" {
  description = "returns a list of object"
  value       = data.nutanix_protection_rules.this.entities
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_protection_rules.this.id
}

output "this" {
  value = nutanix_protection_rules.this
}
```

[top](#index)