# oci_log_analytics_namespace

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
module "oci_log_analytics_namespace" {
  source = "./modules/oci/r/oci_log_analytics_namespace"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # is_onboarded - (required) is a type of bool
  is_onboarded = null
  # namespace - (required) is a type of string
  namespace = null

  timeouts = [{
    create = null
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

variable "is_onboarded" {
  description = "(required)"
  type        = bool
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_log_analytics_namespace" "this" {
  compartment_id = var.compartment_id
  is_onboarded   = var.is_onboarded
  namespace      = var.namespace

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
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
  value       = oci_log_analytics_namespace.this.id
}

output "this" {
  value = oci_log_analytics_namespace.this
}
```

[top](#index)