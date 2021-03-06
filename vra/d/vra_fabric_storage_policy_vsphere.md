# vra_fabric_storage_policy_vsphere

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_fabric_storage_policy_vsphere" {
  source = "./modules/vra/d/vra_fabric_storage_policy_vsphere"

  # filter - (optional) is a type of string
  filter = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vra_fabric_storage_policy_vsphere" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "cloud_account_ids" {
  description = "returns a list of string"
  value       = data.vra_fabric_storage_policy_vsphere.this.cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_fabric_storage_policy_vsphere.this.created_at
}

output "external_id" {
  description = "returns a string"
  value       = data.vra_fabric_storage_policy_vsphere.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_fabric_storage_policy_vsphere.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_fabric_storage_policy_vsphere.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_fabric_storage_policy_vsphere.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_fabric_storage_policy_vsphere.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_fabric_storage_policy_vsphere.this.org_id
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_fabric_storage_policy_vsphere.this.updated_at
}

output "this" {
  value = vra_fabric_storage_policy_vsphere.this
}
```

[top](#index)