# vsphere_custom_attribute

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
module "vsphere_custom_attribute" {
  source = "./modules/vsphere/d/vsphere_custom_attribute"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required) - The display name of the custom attribute."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_custom_attribute" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
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