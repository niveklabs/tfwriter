# vsphere_tag_category

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "vsphere_tag_category" {
  source = "./modules/vsphere/d/vsphere_tag_category"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required) - The display name of the category."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_tag_category" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "associable_types" {
  description = "returns a set of string"
  value       = data.vsphere_tag_category.this.associable_types
}

output "cardinality" {
  description = "returns a string"
  value       = data.vsphere_tag_category.this.cardinality
}

output "description" {
  description = "returns a string"
  value       = data.vsphere_tag_category.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vsphere_tag_category.this.id
}

output "this" {
  value = vsphere_tag_category.this
}
```

[top](#index)