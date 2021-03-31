# mso_schema_template_vrf

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_vrf" {
  source = "./modules/mso/d/mso_schema_template_vrf"

  # display_name - (optional) is a type of string
  display_name = null
  # layer3_multicast - (optional) is a type of bool
  layer3_multicast = null
  # name - (required) is a type of string
  name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template - (required) is a type of string
  template = null
  # vzany - (optional) is a type of bool
  vzany = null
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

variable "layer3_multicast" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "vzany" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_vrf" "this" {
  display_name     = var.display_name
  layer3_multicast = var.layer3_multicast
  name             = var.name
  schema_id        = var.schema_id
  template         = var.template
  vzany            = var.vzany
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_vrf.this.id
}

output "this" {
  value = mso_schema_template_vrf.this
}
```

[top](#index)