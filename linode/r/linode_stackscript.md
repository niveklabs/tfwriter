# linode_stackscript

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_stackscript" {
  source = "./modules/linode/r/linode_stackscript"

  # description - (required) is a type of string
  description = null
  # images - (required) is a type of list of string
  images = []
  # is_public - (optional) is a type of bool
  is_public = null
  # label - (required) is a type of string
  label = null
  # rev_note - (optional) is a type of string
  rev_note = null
  # script - (required) is a type of string
  script = null
  # user_defined_fields - (optional) is a type of list of object
  user_defined_fields = [{
    default = null
    example = null
    label   = null
    many_of = null
    name    = null
    one_of  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required) - A description for the StackScript."
  type        = string
}

variable "images" {
  description = "(required) - An array of Image IDs representing the Images that this StackScript is compatible for deploying with."
  type        = list(string)
}

variable "is_public" {
  description = "(optional) - This determines whether other users can use your StackScript. Once a StackScript is made public, it cannot be made private."
  type        = bool
  default     = null
}

variable "label" {
  description = "(required) - The StackScript's label is for display purposes only."
  type        = string
}

variable "rev_note" {
  description = "(optional) - This field allows you to add notes for the set of revisions made to this StackScript."
  type        = string
  default     = null
}

variable "script" {
  description = "(required) - The script to execute when provisioning a new Linode with this StackScript."
  type        = string
}

variable "user_defined_fields" {
  description = "(optional) - This is a list of fields defined with a special syntax inside this StackScript that allow for supplying customized parameters during deployment."
  type = list(object(
    {
      default = string
      example = string
      label   = string
      many_of = string
      name    = string
      one_of  = string
    }
  ))
  default = null
}
```

[top](#index)

### Resource

```terraform
resource "linode_stackscript" "this" {
  description         = var.description
  images              = var.images
  is_public           = var.is_public
  label               = var.label
  rev_note            = var.rev_note
  script              = var.script
  user_defined_fields = var.user_defined_fields
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = linode_stackscript.this.created
}

output "deployments_active" {
  description = "returns a number"
  value       = linode_stackscript.this.deployments_active
}

output "deployments_total" {
  description = "returns a number"
  value       = linode_stackscript.this.deployments_total
}

output "id" {
  description = "returns a string"
  value       = linode_stackscript.this.id
}

output "updated" {
  description = "returns a string"
  value       = linode_stackscript.this.updated
}

output "user_defined_fields" {
  description = "returns a list of object"
  value       = linode_stackscript.this.user_defined_fields
}

output "user_gravatar_id" {
  description = "returns a string"
  value       = linode_stackscript.this.user_gravatar_id
}

output "username" {
  description = "returns a string"
  value       = linode_stackscript.this.username
}

output "this" {
  value = linode_stackscript.this
}
```

[top](#index)