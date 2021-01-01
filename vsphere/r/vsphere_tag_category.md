# vsphere_tag_category

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/vsphere/r/vsphere_tag_category"

  # associable_types - (required) is a type of set of string
  associable_types = []
  # cardinality - (required) is a type of string
  cardinality = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "associable_types" {
  description = "(required) - Object types to which this category's tags can be attached."
  type        = set(string)
}

variable "cardinality" {
  description = "(required) - The associated cardinality of the category. Can be one of SINGLE (object can only be assigned one tag in this category) or MULTIPLE (object can be assigned multiple tags in this category)."
  type        = string
}

variable "description" {
  description = "(optional) - The description of the category."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The display name of the category."
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "vsphere_tag_category" "this" {
  associable_types = var.associable_types
  cardinality      = var.cardinality
  description      = var.description
  name             = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = vsphere_tag_category.this.id
}

output "this" {
  value = vsphere_tag_category.this
}
```

[top](#index)