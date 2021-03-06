# vsphere_datacenter

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
module "vsphere_datacenter" {
  source = "./modules/vsphere/r/vsphere_datacenter"

  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # folder - (optional) is a type of string
  folder = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "folder" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_datacenter" "this" {
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = var.custom_attributes
  # folder - (optional) is a type of string
  folder = var.folder
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_datacenter.this.id
}

output "moid" {
  description = "returns a string"
  value       = vsphere_datacenter.this.moid
}

output "this" {
  value = vsphere_datacenter.this
}
```

[top](#index)