# vsphere_custom_attribute

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
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_custom_attribute" {
  source = "./modules/vsphere/r/vsphere_custom_attribute"

  # managed_object_type - (optional) is a type of string
  managed_object_type = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "managed_object_type" {
  description = "(optional) - Object type for which the custom attribute is valid. If not specified, the attribute is valid for all managed object types."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The display name of the custom attribute."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_custom_attribute" "this" {
  managed_object_type = var.managed_object_type
  name                = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_custom_attribute.this.id
}

output "this" {
  value = vsphere_custom_attribute.this
}
```

[top](#index)