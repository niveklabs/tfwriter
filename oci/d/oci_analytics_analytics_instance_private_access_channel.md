# oci_analytics_analytics_instance_private_access_channel

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_analytics_analytics_instance_private_access_channel" {
  source = "./modules/oci/d/oci_analytics_analytics_instance_private_access_channel"

  # analytics_instance_id - (required) is a type of string
  analytics_instance_id = null
  # private_access_channel_key - (required) is a type of string
  private_access_channel_key = null
}
```

[top](#index)

### Variables

```terraform
variable "analytics_instance_id" {
  description = "(required)"
  type        = string
}

variable "private_access_channel_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_analytics_analytics_instance_private_access_channel" "this" {
  # analytics_instance_id - (required) is a type of string
  analytics_instance_id = var.analytics_instance_id
  # private_access_channel_key - (required) is a type of string
  private_access_channel_key = var.private_access_channel_key
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance_private_access_channel.this.display_name
}

output "egress_source_ip_addresses" {
  description = "returns a list of string"
  value       = data.oci_analytics_analytics_instance_private_access_channel.this.egress_source_ip_addresses
}

output "id" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance_private_access_channel.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance_private_access_channel.this.ip_address
}

output "key" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance_private_access_channel.this.key
}

output "private_source_dns_zones" {
  description = "returns a list of object"
  value       = data.oci_analytics_analytics_instance_private_access_channel.this.private_source_dns_zones
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance_private_access_channel.this.subnet_id
}

output "vcn_id" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance_private_access_channel.this.vcn_id
}

output "this" {
  value = oci_analytics_analytics_instance_private_access_channel.this
}
```

[top](#index)