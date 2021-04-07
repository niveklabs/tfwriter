# oci_containerengine_node_pool

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
module "oci_containerengine_node_pool" {
  source = "./modules/oci/r/oci_containerengine_node_pool"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # kubernetes_version - (required) is a type of string
  kubernetes_version = null
  # name - (required) is a type of string
  name = null
  # node_image_id - (optional) is a type of string
  node_image_id = null
  # node_image_name - (optional) is a type of string
  node_image_name = null
  # node_metadata - (optional) is a type of map of string
  node_metadata = {}
  # node_shape - (required) is a type of string
  node_shape = null
  # quantity_per_subnet - (optional) is a type of number
  quantity_per_subnet = null
  # ssh_public_key - (optional) is a type of string
  ssh_public_key = null
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = []

  initial_node_labels = [{
    key   = null
    value = null
  }]

  node_config_details = [{
    placement_configs = [{
      availability_domain = null
      subnet_id           = null
    }]
    size = null
  }]

  node_shape_config = [{
    memory_in_gbs = null
    ocpus         = null
  }]

  node_source_details = [{
    boot_volume_size_in_gbs = null
    image_id                = null
    source_type             = null
  }]

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
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "kubernetes_version" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_image_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "node_shape" {
  description = "(required)"
  type        = string
}

variable "quantity_per_subnet" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssh_public_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "initial_node_labels" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "node_config_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      placement_configs = set(object(
        {
          availability_domain = string
          subnet_id           = string
        }
      ))
      size = number
    }
  ))
  default = []
}

variable "node_shape_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      memory_in_gbs = number
      ocpus         = number
    }
  ))
  default = []
}

variable "node_source_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      boot_volume_size_in_gbs = string
      image_id                = string
      source_type             = string
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
```

[top](#index)

### Resource

```terraform
resource "oci_containerengine_node_pool" "this" {
  cluster_id          = var.cluster_id
  compartment_id      = var.compartment_id
  kubernetes_version  = var.kubernetes_version
  name                = var.name
  node_image_id       = var.node_image_id
  node_image_name     = var.node_image_name
  node_metadata       = var.node_metadata
  node_shape          = var.node_shape
  quantity_per_subnet = var.quantity_per_subnet
  ssh_public_key      = var.ssh_public_key
  subnet_ids          = var.subnet_ids

  dynamic "initial_node_labels" {
    for_each = var.initial_node_labels
    content {
      key   = initial_node_labels.value["key"]
      value = initial_node_labels.value["value"]
    }
  }

  dynamic "node_config_details" {
    for_each = var.node_config_details
    content {
      size = node_config_details.value["size"]

      dynamic "placement_configs" {
        for_each = node_config_details.value.placement_configs
        content {
          availability_domain = placement_configs.value["availability_domain"]
          subnet_id           = placement_configs.value["subnet_id"]
        }
      }

    }
  }

  dynamic "node_shape_config" {
    for_each = var.node_shape_config
    content {
      memory_in_gbs = node_shape_config.value["memory_in_gbs"]
      ocpus         = node_shape_config.value["ocpus"]
    }
  }

  dynamic "node_source_details" {
    for_each = var.node_source_details
    content {
      boot_volume_size_in_gbs = node_source_details.value["boot_volume_size_in_gbs"]
      image_id                = node_source_details.value["image_id"]
      source_type             = node_source_details.value["source_type"]
    }
  }

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
output "id" {
  description = "returns a string"
  value       = oci_containerengine_node_pool.this.id
}

output "node_image_id" {
  description = "returns a string"
  value       = oci_containerengine_node_pool.this.node_image_id
}

output "node_image_name" {
  description = "returns a string"
  value       = oci_containerengine_node_pool.this.node_image_name
}

output "node_metadata" {
  description = "returns a map of string"
  value       = oci_containerengine_node_pool.this.node_metadata
}

output "node_source" {
  description = "returns a list of object"
  value       = oci_containerengine_node_pool.this.node_source
}

output "nodes" {
  description = "returns a list of object"
  value       = oci_containerengine_node_pool.this.nodes
}

output "quantity_per_subnet" {
  description = "returns a number"
  value       = oci_containerengine_node_pool.this.quantity_per_subnet
}

output "ssh_public_key" {
  description = "returns a string"
  value       = oci_containerengine_node_pool.this.ssh_public_key
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = oci_containerengine_node_pool.this.subnet_ids
}

output "this" {
  value = oci_containerengine_node_pool.this
}
```

[top](#index)