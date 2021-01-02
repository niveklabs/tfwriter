# kubernetes_priority_class

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_priority_class" {
  source = "./modules/kubernetes/r/kubernetes_priority_class"

  # description - (optional) is a type of string
  description = null
  # global_default - (optional) is a type of bool
  global_default = null
  # value - (required) is a type of number
  value = null

  metadata = [{
    annotations      = {}
    generate_name    = null
    generation       = null
    labels           = {}
    name             = null
    resource_version = null
    self_link        = null
    uid              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - An arbitrary string that usually provides guidelines on when this priority class should be used."
  type        = string
  default     = null
}

variable "global_default" {
  description = "(optional) - Specifies whether this PriorityClass should be considered as the default priority for pods that do not have any priority class. Only one PriorityClass can be marked as `globalDefault`. However, if more than one PriorityClasses exists with their `globalDefault` field set to true, the smallest value of such global default PriorityClasses will be used as the default priority."
  type        = bool
  default     = null
}

variable "value" {
  description = "(required) - The value of this priority class. This is the actual priority that pods receive when they have the name of this class in their pod spec."
  type        = number
}

variable "metadata" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generate_name    = string
      generation       = number
      labels           = map(string)
      name             = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_priority_class" "this" {
  description    = var.description
  global_default = var.global_default
  value          = var.value

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_priority_class.this.id
}

output "this" {
  value = kubernetes_priority_class.this
}
```

[top](#index)