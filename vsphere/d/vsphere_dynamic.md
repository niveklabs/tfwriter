# vsphere_dynamic

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
module "vsphere_dynamic" {
  source = "./modules/vsphere/d/vsphere_dynamic"

  # filter - (required) is a type of set of string
  filter = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(required) - List of tag IDs to match target."
  type        = set(string)
}

variable "name_regex" {
  description = "(optional) - A regular expression used to match against managed object names."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - The type of managed object to return."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_dynamic" "this" {
  filter     = var.filter
  name_regex = var.name_regex
  type       = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_dynamic.this.id
}

output "this" {
  value = vsphere_dynamic.this
}
```

[top](#index)