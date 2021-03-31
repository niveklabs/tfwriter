# vsphere_content_library

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
module "vsphere_content_library" {
  source = "./modules/vsphere/d/vsphere_content_library"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the content library."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_content_library" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_content_library.this.id
}

output "this" {
  value = vsphere_content_library.this
}
```

[top](#index)