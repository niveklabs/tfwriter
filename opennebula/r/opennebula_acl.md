# opennebula_acl

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_acl" {
  source = "./modules/opennebula/r/opennebula_acl"

  # resource - (required) is a type of string
  resource = null
  # rights - (required) is a type of string
  rights = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "resource" {
  description = "(required) - Resource component of the new rule. ACL String Syntax is expected."
  type        = string
}

variable "rights" {
  description = "(required) - Rights component of the new rule. ACL String Syntax is expected."
  type        = string
}

variable "user" {
  description = "(required) - User component of the new rule. ACL String Syntax is expected."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opennebula_acl" "this" {
  resource = var.resource
  rights   = var.rights
  user     = var.user
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opennebula_acl.this.id
}

output "this" {
  value = opennebula_acl.this
}
```

[top](#index)