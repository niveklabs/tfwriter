# vsphere_tag

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

```hcl
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

```hcl
resource "vsphere_tag" "this" {
  category_id = var.category_id
  description = var.description
  name        = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = vsphere_tag.this.id
}

output "this" {
  value = vsphere_tag.this
}
```

[top](#index)