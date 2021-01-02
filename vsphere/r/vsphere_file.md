# vsphere_file

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
module "vsphere_file" {
  source = "./modules/vsphere/r/vsphere_file"

  # create_directories - (optional) is a type of bool
  create_directories = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # datastore - (required) is a type of string
  datastore = null
  # destination_file - (required) is a type of string
  destination_file = null
  # source_datacenter - (optional) is a type of string
  source_datacenter = null
  # source_datastore - (optional) is a type of string
  source_datastore = null
  # source_file - (required) is a type of string
  source_file = null
}
```

[top](#index)

### Variables

```terraform
variable "create_directories" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "datastore" {
  description = "(required)"
  type        = string
}

variable "destination_file" {
  description = "(required)"
  type        = string
}

variable "source_datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_datastore" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_file" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_file" "this" {
  create_directories = var.create_directories
  datacenter         = var.datacenter
  datastore          = var.datastore
  destination_file   = var.destination_file
  source_datacenter  = var.source_datacenter
  source_datastore   = var.source_datastore
  source_file        = var.source_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_file.this.id
}

output "this" {
  value = vsphere_file.this
}
```

[top](#index)