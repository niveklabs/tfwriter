# tencentcloud_scf_namespace

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_scf_namespace" {
  source = "./modules/tencentcloud/r/tencentcloud_scf_namespace"

  # description - (optional) is a type of string
  description = null
  # namespace - (required) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the SCF namespace."
  type        = string
  default     = null
}

variable "namespace" {
  description = "(required) - Name of the SCF namespace."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_scf_namespace" "this" {
  # description - (optional) is a type of string
  description = var.description
  # namespace - (required) is a type of string
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_scf_namespace.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_scf_namespace.this.id
}

output "modify_time" {
  description = "returns a string"
  value       = tencentcloud_scf_namespace.this.modify_time
}

output "type" {
  description = "returns a string"
  value       = tencentcloud_scf_namespace.this.type
}

output "this" {
  value = tencentcloud_scf_namespace.this
}
```

[top](#index)