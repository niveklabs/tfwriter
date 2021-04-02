# oci_resourcemanager_stack_tf_state

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_resourcemanager_stack_tf_state" {
  source = "./modules/oci/d/oci_resourcemanager_stack_tf_state"

  # local_path - (required) is a type of string
  local_path = null
  # stack_id - (required) is a type of string
  stack_id = null
}
```

[top](#index)

### Variables

```terraform
variable "local_path" {
  description = "(required)"
  type        = string
}

variable "stack_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_resourcemanager_stack_tf_state" "this" {
  local_path = var.local_path
  stack_id   = var.stack_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_resourcemanager_stack_tf_state.this.id
}

output "this" {
  value = oci_resourcemanager_stack_tf_state.this
}
```

[top](#index)