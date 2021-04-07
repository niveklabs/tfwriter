# nutanix_category_key

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
module "nutanix_category_key" {
  source = "./modules/nutanix/d/nutanix_category_key"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_category_key" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_category_key.this.api_version
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_category_key.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_category_key.this.id
}

output "system_defined" {
  description = "returns a bool"
  value       = data.nutanix_category_key.this.system_defined
}

output "values" {
  description = "returns a list of string"
  value       = data.nutanix_category_key.this.values
}

output "this" {
  value = nutanix_category_key.this
}
```

[top](#index)