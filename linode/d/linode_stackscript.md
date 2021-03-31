# linode_stackscript

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/linode/d/linode_stackscript"

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

### Datasource

```terraform
data "linode_stackscript" "this" {
  user_defined_fields = var.user_defined_fields
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.linode_stackscript.this.created
}

output "deployments_active" {
  description = "returns a number"
  value       = data.linode_stackscript.this.deployments_active
}

output "deployments_total" {
  description = "returns a number"
  value       = data.linode_stackscript.this.deployments_total
}

output "description" {
  description = "returns a string"
  value       = data.linode_stackscript.this.description
}

output "id" {
  description = "returns a number"
  value       = data.linode_stackscript.this.id
}

output "images" {
  description = "returns a list of string"
  value       = data.linode_stackscript.this.images
}

output "is_public" {
  description = "returns a bool"
  value       = data.linode_stackscript.this.is_public
}

output "label" {
  description = "returns a string"
  value       = data.linode_stackscript.this.label
}

output "rev_note" {
  description = "returns a string"
  value       = data.linode_stackscript.this.rev_note
}

output "script" {
  description = "returns a string"
  value       = data.linode_stackscript.this.script
}

output "updated" {
  description = "returns a string"
  value       = data.linode_stackscript.this.updated
}

output "user_defined_fields" {
  description = "returns a list of object"
  value       = data.linode_stackscript.this.user_defined_fields
}

output "user_gravatar_id" {
  description = "returns a string"
  value       = data.linode_stackscript.this.user_gravatar_id
}

output "username" {
  description = "returns a string"
  value       = data.linode_stackscript.this.username
}

output "this" {
  value = linode_stackscript.this
}
```

[top](#index)