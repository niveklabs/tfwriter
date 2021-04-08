# auth0_prompt

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_prompt" {
  source = "./modules/auth0/r/auth0_prompt"

  # universal_login_experience - (optional) is a type of string
  universal_login_experience = null
}
```

[top](#index)

### Variables

```terraform
variable "universal_login_experience" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "auth0_prompt" "this" {
  # universal_login_experience - (optional) is a type of string
  universal_login_experience = var.universal_login_experience
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_prompt.this.id
}

output "this" {
  value = auth0_prompt.this
}
```

[top](#index)