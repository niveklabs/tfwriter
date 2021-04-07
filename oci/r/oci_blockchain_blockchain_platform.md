# oci_blockchain_blockchain_platform

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
module "oci_blockchain_blockchain_platform" {
  source = "./modules/oci/r/oci_blockchain_blockchain_platform"

  # ca_cert_archive_text - (optional) is a type of string
  ca_cert_archive_text = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # compute_shape - (required) is a type of string
  compute_shape = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # federated_user_id - (optional) is a type of string
  federated_user_id = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # idcs_access_token - (required) is a type of string
  idcs_access_token = null
  # is_byol - (optional) is a type of bool
  is_byol = null
  # load_balancer_shape - (optional) is a type of string
  load_balancer_shape = null
  # platform_role - (required) is a type of string
  platform_role = null
  # storage_size_in_tbs - (optional) is a type of number
  storage_size_in_tbs = null
  # total_ocpu_capacity - (optional) is a type of number
  total_ocpu_capacity = null

  replicas = [{
    ca_count      = null
    console_count = null
    proxy_count   = null
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
variable "ca_cert_archive_text" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "compute_shape" {
  description = "(required)"
  type        = string
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

variable "federated_user_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "idcs_access_token" {
  description = "(required)"
  type        = string
}

variable "is_byol" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "load_balancer_shape" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform_role" {
  description = "(required)"
  type        = string
}

variable "storage_size_in_tbs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "total_ocpu_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "replicas" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ca_count      = number
      console_count = number
      proxy_count   = number
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
resource "oci_blockchain_blockchain_platform" "this" {
  # ca_cert_archive_text - (optional) is a type of string
  ca_cert_archive_text = var.ca_cert_archive_text
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # compute_shape - (required) is a type of string
  compute_shape = var.compute_shape
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # federated_user_id - (optional) is a type of string
  federated_user_id = var.federated_user_id
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # idcs_access_token - (required) is a type of string
  idcs_access_token = var.idcs_access_token
  # is_byol - (optional) is a type of bool
  is_byol = var.is_byol
  # load_balancer_shape - (optional) is a type of string
  load_balancer_shape = var.load_balancer_shape
  # platform_role - (required) is a type of string
  platform_role = var.platform_role
  # storage_size_in_tbs - (optional) is a type of number
  storage_size_in_tbs = var.storage_size_in_tbs
  # total_ocpu_capacity - (optional) is a type of number
  total_ocpu_capacity = var.total_ocpu_capacity

  dynamic "replicas" {
    for_each = var.replicas
    content {
      # ca_count - (optional) is a type of number
      ca_count = replicas.value["ca_count"]
      # console_count - (optional) is a type of number
      console_count = replicas.value["console_count"]
      # proxy_count - (optional) is a type of number
      proxy_count = replicas.value["proxy_count"]
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

}
```

[top](#index)

### Outputs

```terraform
output "ca_cert_archive_text" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.ca_cert_archive_text
}

output "component_details" {
  description = "returns a list of object"
  value       = oci_blockchain_blockchain_platform.this.component_details
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_blockchain_blockchain_platform.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.description
}

output "federated_user_id" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.federated_user_id
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_blockchain_blockchain_platform.this.freeform_tags
}

output "host_ocpu_utilization_info" {
  description = "returns a list of object"
  value       = oci_blockchain_blockchain_platform.this.host_ocpu_utilization_info
}

output "id" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.id
}

output "is_byol" {
  description = "returns a bool"
  value       = oci_blockchain_blockchain_platform.this.is_byol
}

output "is_multi_ad" {
  description = "returns a bool"
  value       = oci_blockchain_blockchain_platform.this.is_multi_ad
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.lifecycle_details
}

output "load_balancer_shape" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.load_balancer_shape
}

output "platform_shape_type" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.platform_shape_type
}

output "service_endpoint" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.service_endpoint
}

output "service_version" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.service_version
}

output "state" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.state
}

output "storage_size_in_tbs" {
  description = "returns a number"
  value       = oci_blockchain_blockchain_platform.this.storage_size_in_tbs
}

output "storage_used_in_tbs" {
  description = "returns a number"
  value       = oci_blockchain_blockchain_platform.this.storage_used_in_tbs
}

output "time_created" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_blockchain_blockchain_platform.this.time_updated
}

output "total_ocpu_capacity" {
  description = "returns a number"
  value       = oci_blockchain_blockchain_platform.this.total_ocpu_capacity
}

output "this" {
  value = oci_blockchain_blockchain_platform.this
}
```

[top](#index)