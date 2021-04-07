# vsphere_storage_policy

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
module "vsphere_storage_policy" {
  source = "./modules/vsphere/d/vsphere_storage_policy"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The display name of the storage policy."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_storage_policy" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_storage_policy.this.id
}

output "this" {
  value = vsphere_storage_policy.this
}
```

[top](#index)