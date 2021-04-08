# vcd_vapp

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_vapp" {
  source = "./modules/vcd/d/vcd_vapp"

  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - A name for the vApp, unique within the VDC"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_vapp" "this" {
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_vapp.this.description
}

output "guest_properties" {
  description = "returns a map of string"
  value       = data.vcd_vapp.this.guest_properties
}

output "href" {
  description = "returns a string"
  value       = data.vcd_vapp.this.href
}

output "id" {
  description = "returns a string"
  value       = data.vcd_vapp.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.vcd_vapp.this.metadata
}

output "status" {
  description = "returns a number"
  value       = data.vcd_vapp.this.status
}

output "status_text" {
  description = "returns a string"
  value       = data.vcd_vapp.this.status_text
}

output "this" {
  value = vcd_vapp.this
}
```

[top](#index)