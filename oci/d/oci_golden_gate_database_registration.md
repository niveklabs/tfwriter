# oci_golden_gate_database_registration

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_golden_gate_database_registration" {
  source = "./modules/oci/d/oci_golden_gate_database_registration"

  # database_registration_id - (required) is a type of string
  database_registration_id = null
}
```

[top](#index)

### Variables

```terraform
variable "database_registration_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_golden_gate_database_registration" "this" {
  database_registration_id = var.database_registration_id
}
```

[top](#index)

### Outputs

```terraform
output "alias_name" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.alias_name
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.compartment_id
}

output "connection_string" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.connection_string
}

output "database_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.database_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_database_registration.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.display_name
}

output "fqdn" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.fqdn
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_database_registration.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.ip_address
}

output "key_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.key_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.lifecycle_details
}

output "password" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.password
  sensitive   = true
}

output "rce_private_ip" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.rce_private_ip
}

output "secret_compartment_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.secret_compartment_id
}

output "secret_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.secret_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.subnet_id
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_database_registration.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.time_updated
}

output "username" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.username
}

output "vault_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.vault_id
}

output "wallet" {
  description = "returns a string"
  value       = data.oci_golden_gate_database_registration.this.wallet
}

output "this" {
  value = oci_golden_gate_database_registration.this
}
```

[top](#index)