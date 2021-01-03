# mso_schema_template_deploy

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_deploy" {
  source = "./modules/mso/r/mso_schema_template_deploy"

  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (optional) is a type of string
  site_id = null
  # template_name - (required) is a type of string
  template_name = null
  # undeploy - (optional) is a type of bool
  undeploy = null
}
```

[top](#index)

### Variables

```terraform
variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "site_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "undeploy" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_deploy" "this" {
  schema_id     = var.schema_id
  site_id       = var.site_id
  template_name = var.template_name
  undeploy      = var.undeploy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_schema_template_deploy.this.id
}

output "site_id" {
  description = "returns a string"
  value       = mso_schema_template_deploy.this.site_id
}

output "undeploy" {
  description = "returns a bool"
  value       = mso_schema_template_deploy.this.undeploy
}

output "this" {
  value = mso_schema_template_deploy.this
}
```

[top](#index)