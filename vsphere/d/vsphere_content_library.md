# vsphere_content_library

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
module "vsphere_content_library" {
  source = "./modules/vsphere/d/vsphere_content_library"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required) - The name of the content library."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_content_library" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.vsphere_content_library.this.id
}

output "this" {
  value = vsphere_content_library.this
}
```

[top](#index)