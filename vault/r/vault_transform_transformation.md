# vault_transform_transformation

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_transform_transformation" {
  source = "./modules/vault/r/vault_transform_transformation"

  # allowed_roles - (optional) is a type of list of string
  allowed_roles = []
  # masking_character - (optional) is a type of string
  masking_character = null
  # name - (required) is a type of string
  name = null
  # path - (required) is a type of string
  path = null
  # template - (optional) is a type of string
  template = null
  # templates - (optional) is a type of list of string
  templates = []
  # tweak_source - (optional) is a type of string
  tweak_source = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_roles" {
  description = "(optional) - The set of roles allowed to perform this transformation."
  type        = list(string)
  default     = null
}

variable "masking_character" {
  description = "(optional) - The character used to replace data when in masking mode"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the transformation."
  type        = string
}

variable "path" {
  description = "(required) - The mount path for a back-end, for example, the path given in \"$ vault auth enable -path=my-aws aws\"."
  type        = string
}

variable "template" {
  description = "(optional) - The name of the template to use."
  type        = string
  default     = null
}

variable "templates" {
  description = "(optional) - Templates configured for transformation."
  type        = list(string)
  default     = null
}

variable "tweak_source" {
  description = "(optional) - The source of where the tweak value comes from. Only valid when in FPE mode."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - The type of transformation to perform."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_transform_transformation" "this" {
  allowed_roles     = var.allowed_roles
  masking_character = var.masking_character
  name              = var.name
  path              = var.path
  template          = var.template
  templates         = var.templates
  tweak_source      = var.tweak_source
  type              = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_transform_transformation.this.id
}

output "templates" {
  description = "returns a list of string"
  value       = vault_transform_transformation.this.templates
}

output "this" {
  value = vault_transform_transformation.this
}
```

[top](#index)