# vcd_org_vdc

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
module "vcd_org_vdc" {
  source = "./modules/vcd/d/vcd_org_vdc"

  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "org" {
  description = "(optional) - Organization to create the VDC in"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_org_vdc" "this" {
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
}
```

[top](#index)

### Outputs

```terraform
output "allocation_model" {
  description = "returns a string"
  value       = data.vcd_org_vdc.this.allocation_model
}

output "allow_over_commit" {
  description = "returns a bool"
  value       = data.vcd_org_vdc.this.allow_over_commit
}

output "compute_capacity" {
  description = "returns a list of object"
  value       = data.vcd_org_vdc.this.compute_capacity
}

output "cpu_guaranteed" {
  description = "returns a number"
  value       = data.vcd_org_vdc.this.cpu_guaranteed
}

output "cpu_speed" {
  description = "returns a number"
  value       = data.vcd_org_vdc.this.cpu_speed
}

output "default_vm_sizing_policy_id" {
  description = "returns a string"
  value       = data.vcd_org_vdc.this.default_vm_sizing_policy_id
}

output "description" {
  description = "returns a string"
  value       = data.vcd_org_vdc.this.description
}

output "elasticity" {
  description = "returns a bool"
  value       = data.vcd_org_vdc.this.elasticity
}

output "enable_fast_provisioning" {
  description = "returns a bool"
  value       = data.vcd_org_vdc.this.enable_fast_provisioning
}

output "enable_thin_provisioning" {
  description = "returns a bool"
  value       = data.vcd_org_vdc.this.enable_thin_provisioning
}

output "enable_vm_discovery" {
  description = "returns a bool"
  value       = data.vcd_org_vdc.this.enable_vm_discovery
}

output "enabled" {
  description = "returns a bool"
  value       = data.vcd_org_vdc.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.vcd_org_vdc.this.id
}

output "include_vm_memory_overhead" {
  description = "returns a bool"
  value       = data.vcd_org_vdc.this.include_vm_memory_overhead
}

output "memory_guaranteed" {
  description = "returns a number"
  value       = data.vcd_org_vdc.this.memory_guaranteed
}

output "metadata" {
  description = "returns a map of string"
  value       = data.vcd_org_vdc.this.metadata
}

output "network_pool_name" {
  description = "returns a string"
  value       = data.vcd_org_vdc.this.network_pool_name
}

output "network_quota" {
  description = "returns a number"
  value       = data.vcd_org_vdc.this.network_quota
}

output "nic_quota" {
  description = "returns a number"
  value       = data.vcd_org_vdc.this.nic_quota
}

output "provider_vdc_name" {
  description = "returns a string"
  value       = data.vcd_org_vdc.this.provider_vdc_name
}

output "storage_profile" {
  description = "returns a list of object"
  value       = data.vcd_org_vdc.this.storage_profile
}

output "vm_quota" {
  description = "returns a number"
  value       = data.vcd_org_vdc.this.vm_quota
}

output "vm_sizing_policy_ids" {
  description = "returns a set of string"
  value       = data.vcd_org_vdc.this.vm_sizing_policy_ids
}

output "this" {
  value = vcd_org_vdc.this
}
```

[top](#index)