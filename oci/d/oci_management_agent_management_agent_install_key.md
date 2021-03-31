# oci_management_agent_management_agent_install_key

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_management_agent_management_agent_install_key" {
  source = "./modules/oci/d/oci_management_agent_management_agent_install_key"

  # management_agent_install_key_id - (required) is a type of string
  management_agent_install_key_id = null
}
```

[top](#index)

### Variables

```terraform
variable "management_agent_install_key_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_management_agent_management_agent_install_key" "this" {
  management_agent_install_key_id = var.management_agent_install_key_id
}
```

[top](#index)

### Outputs

```terraform
output "allowed_key_install_count" {
  description = "returns a number"
  value       = data.oci_management_agent_management_agent_install_key.this.allowed_key_install_count
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.compartment_id
}

output "created_by_principal_id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.created_by_principal_id
}

output "current_key_install_count" {
  description = "returns a number"
  value       = data.oci_management_agent_management_agent_install_key.this.current_key_install_count
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.id
}

output "key" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.key
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.time_created
}

output "time_expires" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.time_expires
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_install_key.this.time_updated
}

output "this" {
  value = oci_management_agent_management_agent_install_key.this
}
```

[top](#index)