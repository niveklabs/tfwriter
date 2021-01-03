# oci_containerengine_cluster

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_containerengine_cluster" {
  source = "./modules/oci/r/oci_containerengine_cluster"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # kubernetes_version - (required) is a type of string
  kubernetes_version = null
  # name - (required) is a type of string
  name = null
  # vcn_id - (required) is a type of string
  vcn_id = null

  options = [{
    add_ons = [{
      is_kubernetes_dashboard_enabled = null
      is_tiller_enabled               = null
    }]
    admission_controller_options = [{
      is_pod_security_policy_enabled = null
    }]
    kubernetes_network_config = [{
      pods_cidr     = null
      services_cidr = null
    }]
    service_lb_subnet_ids = []
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kubernetes_version" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "vcn_id" {
  description = "(required)"
  type        = string
}

variable "options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      add_ons = list(object(
        {
          is_kubernetes_dashboard_enabled = bool
          is_tiller_enabled               = bool
        }
      ))
      admission_controller_options = list(object(
        {
          is_pod_security_policy_enabled = bool
        }
      ))
      kubernetes_network_config = list(object(
        {
          pods_cidr     = string
          services_cidr = string
        }
      ))
      service_lb_subnet_ids = list(string)
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
resource "oci_containerengine_cluster" "this" {
  compartment_id     = var.compartment_id
  kms_key_id         = var.kms_key_id
  kubernetes_version = var.kubernetes_version
  name               = var.name
  vcn_id             = var.vcn_id

  dynamic "options" {
    for_each = var.options
    content {
      service_lb_subnet_ids = options.value["service_lb_subnet_ids"]

      dynamic "add_ons" {
        for_each = options.value.add_ons
        content {
          is_kubernetes_dashboard_enabled = add_ons.value["is_kubernetes_dashboard_enabled"]
          is_tiller_enabled               = add_ons.value["is_tiller_enabled"]
        }
      }

      dynamic "admission_controller_options" {
        for_each = options.value.admission_controller_options
        content {
          is_pod_security_policy_enabled = admission_controller_options.value["is_pod_security_policy_enabled"]
        }
      }

      dynamic "kubernetes_network_config" {
        for_each = options.value.kubernetes_network_config
        content {
          pods_cidr     = kubernetes_network_config.value["pods_cidr"]
          services_cidr = kubernetes_network_config.value["services_cidr"]
        }
      }

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
output "available_kubernetes_upgrades" {
  description = "returns a list of string"
  value       = oci_containerengine_cluster.this.available_kubernetes_upgrades
}

output "endpoints" {
  description = "returns a list of object"
  value       = oci_containerengine_cluster.this.endpoints
}

output "id" {
  description = "returns a string"
  value       = oci_containerengine_cluster.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_containerengine_cluster.this.kms_key_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_containerengine_cluster.this.lifecycle_details
}

output "metadata" {
  description = "returns a list of object"
  value       = oci_containerengine_cluster.this.metadata
}

output "state" {
  description = "returns a string"
  value       = oci_containerengine_cluster.this.state
}

output "this" {
  value = oci_containerengine_cluster.this
}
```

[top](#index)