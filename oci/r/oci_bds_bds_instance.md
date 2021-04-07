# oci_bds_bds_instance

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_bds_bds_instance" {
  source = "./modules/oci/r/oci_bds_bds_instance"

  # cluster_admin_password - (required) is a type of string
  cluster_admin_password = null
  # cluster_public_key - (required) is a type of string
  cluster_public_key = null
  # cluster_version - (required) is a type of string
  cluster_version = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_cloud_sql_configured - (optional) is a type of bool
  is_cloud_sql_configured = null
  # is_high_availability - (required) is a type of bool
  is_high_availability = null
  # is_secure - (required) is a type of bool
  is_secure = null

  cloud_sql_details = [{
    block_volume_size_in_gbs             = null
    ip_address                           = null
    is_kerberos_mapped_to_database_users = null
    kerberos_details = [{
      keytab_file    = null
      principal_name = null
    }]
    shape = null
  }]

  master_node = [{
    block_volume_size_in_gbs = null
    number_of_nodes          = null
    shape                    = null
    subnet_id                = null
  }]

  network_config = [{
    cidr_block              = null
    is_nat_gateway_required = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  util_node = [{
    block_volume_size_in_gbs = null
    number_of_nodes          = null
    shape                    = null
    subnet_id                = null
  }]

  worker_node = [{
    block_volume_size_in_gbs = null
    number_of_nodes          = null
    shape                    = null
    subnet_id                = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_admin_password" {
  description = "(required)"
  type        = string
}

variable "cluster_public_key" {
  description = "(required)"
  type        = string
}

variable "cluster_version" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_cloud_sql_configured" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_high_availability" {
  description = "(required)"
  type        = bool
}

variable "is_secure" {
  description = "(required)"
  type        = bool
}

variable "cloud_sql_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      block_volume_size_in_gbs             = string
      ip_address                           = string
      is_kerberos_mapped_to_database_users = bool
      kerberos_details = list(object(
        {
          keytab_file    = string
          principal_name = string
        }
      ))
      shape = string
    }
  ))
  default = []
}

variable "master_node" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      block_volume_size_in_gbs = string
      number_of_nodes          = number
      shape                    = string
      subnet_id                = string
    }
  ))
}

variable "network_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cidr_block              = string
      is_nat_gateway_required = bool
    }
  ))
  default = []
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

variable "util_node" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      block_volume_size_in_gbs = string
      number_of_nodes          = number
      shape                    = string
      subnet_id                = string
    }
  ))
}

variable "worker_node" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      block_volume_size_in_gbs = string
      number_of_nodes          = number
      shape                    = string
      subnet_id                = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "oci_bds_bds_instance" "this" {
  # cluster_admin_password - (required) is a type of string
  cluster_admin_password = var.cluster_admin_password
  # cluster_public_key - (required) is a type of string
  cluster_public_key = var.cluster_public_key
  # cluster_version - (required) is a type of string
  cluster_version = var.cluster_version
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (required) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # is_cloud_sql_configured - (optional) is a type of bool
  is_cloud_sql_configured = var.is_cloud_sql_configured
  # is_high_availability - (required) is a type of bool
  is_high_availability = var.is_high_availability
  # is_secure - (required) is a type of bool
  is_secure = var.is_secure

  dynamic "cloud_sql_details" {
    for_each = var.cloud_sql_details
    content {
      # block_volume_size_in_gbs - (required) is a type of string
      block_volume_size_in_gbs = cloud_sql_details.value["block_volume_size_in_gbs"]
      # shape - (required) is a type of string
      shape = cloud_sql_details.value["shape"]
    }
  }

  dynamic "master_node" {
    for_each = var.master_node
    content {
      # block_volume_size_in_gbs - (required) is a type of string
      block_volume_size_in_gbs = master_node.value["block_volume_size_in_gbs"]
      # number_of_nodes - (required) is a type of number
      number_of_nodes = master_node.value["number_of_nodes"]
      # shape - (required) is a type of string
      shape = master_node.value["shape"]
      # subnet_id - (required) is a type of string
      subnet_id = master_node.value["subnet_id"]
    }
  }

  dynamic "network_config" {
    for_each = var.network_config
    content {
      # cidr_block - (optional) is a type of string
      cidr_block = network_config.value["cidr_block"]
      # is_nat_gateway_required - (optional) is a type of bool
      is_nat_gateway_required = network_config.value["is_nat_gateway_required"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "util_node" {
    for_each = var.util_node
    content {
      # block_volume_size_in_gbs - (required) is a type of string
      block_volume_size_in_gbs = util_node.value["block_volume_size_in_gbs"]
      # number_of_nodes - (required) is a type of number
      number_of_nodes = util_node.value["number_of_nodes"]
      # shape - (required) is a type of string
      shape = util_node.value["shape"]
      # subnet_id - (required) is a type of string
      subnet_id = util_node.value["subnet_id"]
    }
  }

  dynamic "worker_node" {
    for_each = var.worker_node
    content {
      # block_volume_size_in_gbs - (required) is a type of string
      block_volume_size_in_gbs = worker_node.value["block_volume_size_in_gbs"]
      # number_of_nodes - (required) is a type of number
      number_of_nodes = worker_node.value["number_of_nodes"]
      # shape - (required) is a type of string
      shape = worker_node.value["shape"]
      # subnet_id - (required) is a type of string
      subnet_id = worker_node.value["subnet_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_details" {
  description = "returns a list of object"
  value       = oci_bds_bds_instance.this.cluster_details
}

output "created_by" {
  description = "returns a string"
  value       = oci_bds_bds_instance.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_bds_bds_instance.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_bds_bds_instance.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_bds_bds_instance.this.id
}

output "is_cloud_sql_configured" {
  description = "returns a bool"
  value       = oci_bds_bds_instance.this.is_cloud_sql_configured
}

output "nodes" {
  description = "returns a list of object"
  value       = oci_bds_bds_instance.this.nodes
}

output "number_of_nodes" {
  description = "returns a number"
  value       = oci_bds_bds_instance.this.number_of_nodes
}

output "state" {
  description = "returns a string"
  value       = oci_bds_bds_instance.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_bds_bds_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_bds_bds_instance.this.time_updated
}

output "this" {
  value = oci_bds_bds_instance.this
}
```

[top](#index)