# vsphere_content_library_item

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vsphere_content_library_item" {
  source = "./modules/vsphere/d/vsphere_content_library_item"

  # library_id - (required) is a type of string
  library_id = null
  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "library_id" {
  description = "(required) - ID of the content library to contain item."
  type        = string
}

variable "name" {
  description = "(required) - The name of the content library item."
  type        = string
}

variable "type" {
  description = "(required) - Type of content library item."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_content_library_item" "this" {
  library_id = var.library_id
  name       = var.name
  type       = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_content_library_item.this.id
}

output "this" {
  value = vsphere_content_library_item.this
}
```

[top](#index)