# vcd_org

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
module "vcd_org" {
  source = "./modules/vcd/d/vcd_org"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Organization name for lookup"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vcd_org" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "can_publish_catalogs" {
  description = "returns a bool"
  value       = data.vcd_org.this.can_publish_catalogs
}

output "delay_after_power_on_seconds" {
  description = "returns a number"
  value       = data.vcd_org.this.delay_after_power_on_seconds
}

output "deployed_vm_quota" {
  description = "returns a number"
  value       = data.vcd_org.this.deployed_vm_quota
}

output "description" {
  description = "returns a string"
  value       = data.vcd_org.this.description
}

output "full_name" {
  description = "returns a string"
  value       = data.vcd_org.this.full_name
}

output "id" {
  description = "returns a string"
  value       = data.vcd_org.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.vcd_org.this.is_enabled
}

output "stored_vm_quota" {
  description = "returns a number"
  value       = data.vcd_org.this.stored_vm_quota
}

output "vapp_lease" {
  description = "returns a list of object"
  value       = data.vcd_org.this.vapp_lease
}

output "vapp_template_lease" {
  description = "returns a list of object"
  value       = data.vcd_org.this.vapp_template_lease
}

output "this" {
  value = vcd_org.this
}
```

[top](#index)