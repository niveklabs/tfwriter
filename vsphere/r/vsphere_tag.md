# vsphere_tag

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
module "vsphere_tag" {
  source = "./modules/vsphere/r/vsphere_tag"

  # category_id - (required) is a type of string
  category_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "category_id" {
  description = "(required) - The unique identifier of the parent category in which this tag will be created."
  type        = string
}

variable "description" {
  description = "(optional) - The description of the tag."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The display name of the tag. The name must be unique within its category."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_tag" "this" {
  # category_id - (required) is a type of string
  category_id = var.category_id
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
  value       = vsphere_tag.this.id
}

output "this" {
  value = vsphere_tag.this
}
```

[top](#index)