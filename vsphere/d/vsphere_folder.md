# vsphere_folder

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
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_folder" {
  source = "./modules/vsphere/d/vsphere_folder"

  # path - (required) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "path" {
  description = "(required) - The absolute path of the folder."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_folder" "this" {
  path = var.path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_folder.this.id
}

output "this" {
  value = vsphere_folder.this
}
```

[top](#index)