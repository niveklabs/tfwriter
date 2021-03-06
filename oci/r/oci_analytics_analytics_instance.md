# oci_analytics_analytics_instance

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
module "oci_analytics_analytics_instance" {
  source = "./modules/oci/r/oci_analytics_analytics_instance"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # email_notification - (optional) is a type of string
  email_notification = null
  # feature_set - (required) is a type of string
  feature_set = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # idcs_access_token - (required) is a type of string
  idcs_access_token = null
  # license_type - (required) is a type of string
  license_type = null
  # name - (required) is a type of string
  name = null
  # state - (optional) is a type of string
  state = null

  capacity = [{
    capacity_type  = null
    capacity_value = null
  }]

  network_endpoint_details = [{
    network_endpoint_type = null
    subnet_id             = null
    vcn_id                = null
    whitelisted_ips       = []
    whitelisted_vcns = [{
      id              = null
      whitelisted_ips = []
    }]
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

variable "email_notification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "feature_set" {
  description = "(required)"
  type        = string
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

variable "license_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capacity" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity_type  = string
      capacity_value = number
    }
  ))
}

variable "network_endpoint_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      network_endpoint_type = string
      subnet_id             = string
      vcn_id                = string
      whitelisted_ips       = list(string)
      whitelisted_vcns = list(object(
        {
          id              = string
          whitelisted_ips = list(string)
        }
      ))
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
resource "oci_analytics_analytics_instance" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (optional) is a type of string
  description = var.description
  # email_notification - (optional) is a type of string
  email_notification = var.email_notification
  # feature_set - (required) is a type of string
  feature_set = var.feature_set
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # idcs_access_token - (required) is a type of string
  idcs_access_token = var.idcs_access_token
  # license_type - (required) is a type of string
  license_type = var.license_type
  # name - (required) is a type of string
  name = var.name
  # state - (optional) is a type of string
  state = var.state

  dynamic "capacity" {
    for_each = var.capacity
    content {
      # capacity_type - (required) is a type of string
      capacity_type = capacity.value["capacity_type"]
      # capacity_value - (required) is a type of number
      capacity_value = capacity.value["capacity_value"]
    }
  }

  dynamic "network_endpoint_details" {
    for_each = var.network_endpoint_details
    content {
      # network_endpoint_type - (required) is a type of string
      network_endpoint_type = network_endpoint_details.value["network_endpoint_type"]
      # subnet_id - (optional) is a type of string
      subnet_id = network_endpoint_details.value["subnet_id"]
      # vcn_id - (optional) is a type of string
      vcn_id = network_endpoint_details.value["vcn_id"]
      # whitelisted_ips - (optional) is a type of list of string
      whitelisted_ips = network_endpoint_details.value["whitelisted_ips"]

      dynamic "whitelisted_vcns" {
        for_each = network_endpoint_details.value.whitelisted_vcns
        content {
          # id - (optional) is a type of string
          id = whitelisted_vcns.value["id"]
          # whitelisted_ips - (optional) is a type of list of string
          whitelisted_ips = whitelisted_vcns.value["whitelisted_ips"]
        }
      }

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_analytics_analytics_instance.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance.this.description
}

output "email_notification" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance.this.email_notification
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_analytics_analytics_instance.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance.this.id
}

output "private_access_channels" {
  description = "returns a map of string"
  value       = oci_analytics_analytics_instance.this.private_access_channels
}

output "service_url" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance.this.service_url
}

output "state" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance.this.time_updated
}

output "vanity_url_details" {
  description = "returns a map of string"
  value       = oci_analytics_analytics_instance.this.vanity_url_details
}

output "this" {
  value = oci_analytics_analytics_instance.this
}
```

[top](#index)