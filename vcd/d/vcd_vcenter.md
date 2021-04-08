# vcd_vcenter

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
module "vcd_vcenter" {
  source = "./modules/vcd/d/vcd_vcenter"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of vCenter."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vcd_vcenter" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "connection_status" {
  description = "returns a string"
  value       = data.vcd_vcenter.this.connection_status
}

output "id" {
  description = "returns a string"
  value       = data.vcd_vcenter.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.vcd_vcenter.this.is_enabled
}

output "status" {
  description = "returns a string"
  value       = data.vcd_vcenter.this.status
}

output "vcenter_host" {
  description = "returns a string"
  value       = data.vcd_vcenter.this.vcenter_host
}

output "vcenter_version" {
  description = "returns a string"
  value       = data.vcd_vcenter.this.vcenter_version
}

output "this" {
  value = vcd_vcenter.this
}
```

[top](#index)