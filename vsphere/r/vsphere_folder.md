# vsphere_folder

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
module "vsphere_folder" {
  source = "./modules/vsphere/r/vsphere_folder"

  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # datacenter_id - (optional) is a type of string
  datacenter_id = null
  # path - (required) is a type of string
  path = null
  # tags - (optional) is a type of set of string
  tags = []
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```hcl
variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "datacenter_id" {
  description = "(optional) - The ID of the datacenter. Can be ignored if creating a datacenter folder, otherwise required."
  type        = string
  default     = null
}

variable "path" {
  description = "(required) - The path of the folder and any parents, relative to the datacenter and folder type being defined."
  type        = string
}

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(required) - The type of the folder."
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "vsphere_folder" "this" {
  custom_attributes = var.custom_attributes
  datacenter_id     = var.datacenter_id
  path              = var.path
  tags              = var.tags
  type              = var.type
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = vsphere_folder.this.id
}

output "this" {
  value = vsphere_folder.this
}
```

[top](#index)