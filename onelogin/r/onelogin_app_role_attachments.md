# onelogin_app_role_attachments

[back](../onelogin.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    onelogin = ">= 0.1.12"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "onelogin_app_role_attachments" {
  source = "./modules/onelogin/r/onelogin_app_role_attachments"

  # app_id - (required) is a type of number
  app_id = null
  # role_id - (required) is a type of number
  role_id = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = number
}

variable "role_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "onelogin_app_role_attachments" "this" {
  # app_id - (required) is a type of number
  app_id = var.app_id
  # role_id - (required) is a type of number
  role_id = var.role_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = onelogin_app_role_attachments.this.id
}

output "this" {
  value = onelogin_app_role_attachments.this
}
```

[top](#index)