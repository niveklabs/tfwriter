# vsphere_custom_attribute

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
module "vsphere_custom_attribute" {
  source = "./modules/vsphere/d/vsphere_custom_attribute"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The display name of the custom attribute."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_custom_attribute" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_custom_attribute.this.id
}

output "managed_object_type" {
  description = "returns a string"
  value       = data.vsphere_custom_attribute.this.managed_object_type
}

output "this" {
  value = vsphere_custom_attribute.this
}
```

[top](#index)