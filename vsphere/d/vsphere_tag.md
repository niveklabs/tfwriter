# vsphere_tag

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
module "vsphere_tag" {
  source = "./modules/vsphere/d/vsphere_tag"

  # category_id - (required) is a type of string
  category_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "category_id" {
  description = "(required) - The unique identifier of the parent category for this tag."
  type        = string
}

variable "name" {
  description = "(required) - The display name of the tag."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_tag" "this" {
  category_id = var.category_id
  name        = var.name
}
```

[top](#index)

### Outputs

```hcl
output "description" {
  description = "returns a string"
  value       = data.vsphere_tag.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vsphere_tag.this.id
}

output "this" {
  value = vsphere_tag.this
}
```

[top](#index)