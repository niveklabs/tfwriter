# oci_email_sender

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
module "oci_email_sender" {
  source = "./modules/oci/d/oci_email_sender"

  # sender_id - (required) is a type of string
  sender_id = null
}
```

[top](#index)

### Variables

```terraform
variable "sender_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_email_sender" "this" {
  sender_id = var.sender_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_email_sender.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_email_sender.this.defined_tags
}

output "email_address" {
  description = "returns a string"
  value       = data.oci_email_sender.this.email_address
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_email_sender.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_email_sender.this.id
}

output "is_spf" {
  description = "returns a bool"
  value       = data.oci_email_sender.this.is_spf
}

output "state" {
  description = "returns a string"
  value       = data.oci_email_sender.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_email_sender.this.time_created
}

output "this" {
  value = oci_email_sender.this
}
```

[top](#index)