# dome9_cloud_security_group_rule

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
    dome9 = ">= 1.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloud_security_group_rule" {
  source = "./modules/dome9/d/dome9_cloud_security_group_rule"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "dome9_cloud_security_group_rule" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.dome9_cloud_security_group_rule.this.id
}

output "services" {
  description = "returns a set of object"
  value       = data.dome9_cloud_security_group_rule.this.services
}

output "this" {
  value = dome9_cloud_security_group_rule.this
}
```

[top](#index)