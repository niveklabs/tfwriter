# oci_mysql_channel

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_mysql_channel" {
  source = "./modules/oci/d/oci_mysql_channel"

  # channel_id - (required) is a type of string
  channel_id = null
}
```

[top](#index)

### Variables

```terraform
variable "channel_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_mysql_channel" "this" {
  channel_id = var.channel_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_mysql_channel.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_mysql_channel.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_mysql_channel.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_mysql_channel.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_mysql_channel.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_mysql_channel.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_mysql_channel.this.is_enabled
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_mysql_channel.this.lifecycle_details
}

output "source" {
  description = "returns a list of object"
  value       = data.oci_mysql_channel.this.source
}

output "state" {
  description = "returns a string"
  value       = data.oci_mysql_channel.this.state
}

output "target" {
  description = "returns a list of object"
  value       = data.oci_mysql_channel.this.target
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_mysql_channel.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_mysql_channel.this.time_updated
}

output "this" {
  value = oci_mysql_channel.this
}
```

[top](#index)