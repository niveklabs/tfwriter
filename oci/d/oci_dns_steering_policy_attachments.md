# oci_dns_steering_policy_attachments

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
module "oci_dns_steering_policy_attachments" {
  source = "./modules/oci/d/oci_dns_steering_policy_attachments"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # domain - (optional) is a type of string
  domain = null
  # domain_contains - (optional) is a type of string
  domain_contains = null
  # state - (optional) is a type of string
  state = null
  # steering_policy_id - (optional) is a type of string
  steering_policy_id = null
  # time_created_greater_than_or_equal_to - (optional) is a type of string
  time_created_greater_than_or_equal_to = null
  # time_created_less_than - (optional) is a type of string
  time_created_less_than = null
  # zone_id - (optional) is a type of string
  zone_id = null

  filter = [{
    name   = null
    regex  = null
    values = []
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

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "steering_policy_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created_greater_than_or_equal_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created_less_than" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_dns_steering_policy_attachments" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # domain - (optional) is a type of string
  domain = var.domain
  # domain_contains - (optional) is a type of string
  domain_contains = var.domain_contains
  # state - (optional) is a type of string
  state = var.state
  # steering_policy_id - (optional) is a type of string
  steering_policy_id = var.steering_policy_id
  # time_created_greater_than_or_equal_to - (optional) is a type of string
  time_created_greater_than_or_equal_to = var.time_created_greater_than_or_equal_to
  # time_created_less_than - (optional) is a type of string
  time_created_less_than = var.time_created_less_than
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy_attachments.this.id
}

output "steering_policy_attachments" {
  description = "returns a list of object"
  value       = data.oci_dns_steering_policy_attachments.this.steering_policy_attachments
}

output "this" {
  value = oci_dns_steering_policy_attachments.this
}
```

[top](#index)