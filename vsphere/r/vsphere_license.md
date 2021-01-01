# vsphere_license

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
module "vsphere_license" {
  source = "./modules/vsphere/r/vsphere_license"

  # labels - (optional) is a type of map of string
  labels = {}
  # license_key - (required) is a type of string
  license_key = null
}
```

[top](#index)

### Variables

```hcl
variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "license_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "vsphere_license" "this" {
  labels      = var.labels
  license_key = var.license_key
}
```

[top](#index)

### Outputs

```hcl
output "edition_key" {
  description = "returns a string"
  value       = vsphere_license.this.edition_key
}

output "id" {
  description = "returns a string"
  value       = vsphere_license.this.id
}

output "name" {
  description = "returns a string"
  value       = vsphere_license.this.name
}

output "total" {
  description = "returns a number"
  value       = vsphere_license.this.total
}

output "used" {
  description = "returns a number"
  value       = vsphere_license.this.used
}

output "this" {
  value = vsphere_license.this
}
```

[top](#index)