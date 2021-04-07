# oci_dns_steering_policy

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
module "oci_dns_steering_policy" {
  source = "./modules/oci/d/oci_dns_steering_policy"

  # steering_policy_id - (required) is a type of string
  steering_policy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "steering_policy_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_dns_steering_policy" "this" {
  # steering_policy_id - (required) is a type of string
  steering_policy_id = var.steering_policy_id
}
```

[top](#index)

### Outputs

```terraform
output "answers" {
  description = "returns a list of object"
  value       = data.oci_dns_steering_policy.this.answers
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_dns_steering_policy.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_dns_steering_policy.this.freeform_tags
}

output "health_check_monitor_id" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy.this.health_check_monitor_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy.this.id
}

output "rules" {
  description = "returns a list of object"
  value       = data.oci_dns_steering_policy.this.rules
}

output "self" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy.this.self
}

output "state" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy.this.state
}

output "template" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy.this.template
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_dns_steering_policy.this.time_created
}

output "ttl" {
  description = "returns a number"
  value       = data.oci_dns_steering_policy.this.ttl
}

output "this" {
  value = oci_dns_steering_policy.this
}
```

[top](#index)