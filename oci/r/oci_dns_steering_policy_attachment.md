# oci_dns_steering_policy_attachment

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
module "oci_dns_steering_policy_attachment" {
  source = "./modules/oci/r/oci_dns_steering_policy_attachment"

  # display_name - (optional) is a type of string
  display_name = null
  # domain_name - (required) is a type of string
  domain_name = null
  # steering_policy_id - (required) is a type of string
  steering_policy_id = null
  # zone_id - (required) is a type of string
  zone_id = null

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
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "steering_policy_id" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
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
resource "oci_dns_steering_policy_attachment" "this" {
  display_name       = var.display_name
  domain_name        = var.domain_name
  steering_policy_id = var.steering_policy_id
  zone_id            = var.zone_id

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
output "compartment_id" {
  description = "returns a string"
  value       = oci_dns_steering_policy_attachment.this.compartment_id
}

output "display_name" {
  description = "returns a string"
  value       = oci_dns_steering_policy_attachment.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_dns_steering_policy_attachment.this.id
}

output "rtypes" {
  description = "returns a list of string"
  value       = oci_dns_steering_policy_attachment.this.rtypes
}

output "self" {
  description = "returns a string"
  value       = oci_dns_steering_policy_attachment.this.self
}

output "state" {
  description = "returns a string"
  value       = oci_dns_steering_policy_attachment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dns_steering_policy_attachment.this.time_created
}

output "this" {
  value = oci_dns_steering_policy_attachment.this
}
```

[top](#index)