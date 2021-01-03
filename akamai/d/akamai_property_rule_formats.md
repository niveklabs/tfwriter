# akamai_property_rule_formats

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_property_rule_formats" {
  source = "./modules/akamai/d/akamai_property_rule_formats"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_property_rule_formats" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_property_rule_formats.this.id
}

output "rule_format" {
  description = "returns a list of string"
  value       = data.akamai_property_rule_formats.this.rule_format
}

output "this" {
  value = akamai_property_rule_formats.this
}
```

[top](#index)