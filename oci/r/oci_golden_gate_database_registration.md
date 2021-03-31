# oci_golden_gate_database_registration

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "oci_golden_gate_database_registration" {
  source = "./modules/oci/r/oci_golden_gate_database_registration"

  # alias_name - (required) is a type of string
  alias_name = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # connection_string - (optional) is a type of string
  connection_string = null
  # database_id - (optional) is a type of string
  database_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # fqdn - (required) is a type of string
  fqdn = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # ip_address - (optional) is a type of string
  ip_address = null
  # key_id - (optional) is a type of string
  key_id = null
  # password - (required) is a type of string
  password = null
  # secret_compartment_id - (optional) is a type of string
  secret_compartment_id = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # username - (required) is a type of string
  username = null
  # vault_id - (optional) is a type of string
  vault_id = null
  # wallet - (optional) is a type of string
  wallet = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alias_name" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "connection_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "fqdn" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "secret_compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}

variable "vault_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wallet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_golden_gate_database_registration" "this" {
  alias_name            = var.alias_name
  compartment_id        = var.compartment_id
  connection_string     = var.connection_string
  database_id           = var.database_id
  defined_tags          = var.defined_tags
  description           = var.description
  display_name          = var.display_name
  fqdn                  = var.fqdn
  freeform_tags         = var.freeform_tags
  ip_address            = var.ip_address
  key_id                = var.key_id
  password              = var.password
  secret_compartment_id = var.secret_compartment_id
  subnet_id             = var.subnet_id
  username              = var.username
  vault_id              = var.vault_id
  wallet                = var.wallet

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "connection_string" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.connection_string
}

output "database_id" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.database_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_database_registration.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_database_registration.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.ip_address
}

output "key_id" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.key_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.lifecycle_details
}

output "rce_private_ip" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.rce_private_ip
}

output "secret_compartment_id" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.secret_compartment_id
}

output "secret_id" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.secret_id
}

output "state" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.subnet_id
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_database_registration.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.time_updated
}

output "vault_id" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.vault_id
}

output "wallet" {
  description = "returns a string"
  value       = oci_golden_gate_database_registration.this.wallet
}

output "this" {
  value = oci_golden_gate_database_registration.this
}
```

[top](#index)