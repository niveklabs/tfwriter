# oci_artifacts_container_configuration

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_artifacts_container_configuration" {
  source = "./modules/oci/r/oci_artifacts_container_configuration"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # is_repository_created_on_first_push - (required) is a type of bool
  is_repository_created_on_first_push = null

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

variable "is_repository_created_on_first_push" {
  description = "(required)"
  type        = bool
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
resource "oci_artifacts_container_configuration" "this" {
  compartment_id                      = var.compartment_id
  is_repository_created_on_first_push = var.is_repository_created_on_first_push

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
  value       = oci_artifacts_container_configuration.this.id
}

output "namespace" {
  description = "returns a string"
  value       = oci_artifacts_container_configuration.this.namespace
}

output "this" {
  value = oci_artifacts_container_configuration.this
}
```

[top](#index)