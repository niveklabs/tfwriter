# vsphere_tag_category

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
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

```terraform
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

```terraform
resource "vsphere_tag_category" "this" {
  # associable_types - (required) is a type of set of string
  associable_types = var.associable_types
  # cardinality - (required) is a type of string
  cardinality = var.cardinality
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_tag_category.this.id
}

output "this" {
  value = vsphere_tag_category.this
}
```

[top](#index)