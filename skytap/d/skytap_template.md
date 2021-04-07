# skytap_template

[back](../skytap.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    skytap = ">= 0.14.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "skytap_template" {
  source = "./modules/skytap/d/skytap_template"

  # most_recent - (optional) is a type of bool
  most_recent = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "most_recent" {
  description = "(optional) - used when multiple items will be returned"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - regex expression to name of the template"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "skytap_template" "this" {
  # most_recent - (optional) is a type of bool
  most_recent = var.most_recent
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.skytap_template.this.id
}

output "this" {
  value = skytap_template.this
}
```

[top](#index)