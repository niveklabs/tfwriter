# null_resource

[back](../null.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    null = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "null_resource" {
  source = "./modules/null/r/null_resource"

  # triggers - (optional) is a type of map of string
  triggers = {}
}
```

[top](#index)

### Variables

```terraform
variable "triggers" {
  description = "(optional) - A map of arbitrary strings that, when changed, will force the null resource to be replaced, re-running any associated provisioners."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "null_resource" "this" {
  triggers = var.triggers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = null_resource.this.id
}

output "this" {
  value = null_resource.this
}
```

[top](#index)