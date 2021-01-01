# vsphere_storage_policy

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
module "vsphere_storage_policy" {
  source = "./modules/vsphere/d/vsphere_storage_policy"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required) - The display name of the storage policy."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "vsphere_storage_policy" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.vsphere_storage_policy.this.id
}

output "this" {
  value = vsphere_storage_policy.this
}
```

[top](#index)