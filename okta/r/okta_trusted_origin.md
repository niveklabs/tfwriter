# okta_trusted_origin

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_trusted_origin" {
  source = "./modules/okta/r/okta_trusted_origin"

  # active - (optional) is a type of bool
  active = null
  # name - (required) is a type of string
  name = null
  # origin - (required) is a type of string
  origin = null
  # scopes - (required) is a type of list of string
  scopes = []
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional) - Whether the Trusted Origin is active or not - can only be issued post-creation"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Unique name for this trusted origin"
  type        = string
}

variable "origin" {
  description = "(required) - Unique origin URL for this trusted origin"
  type        = string
}

variable "scopes" {
  description = "(required) - Scopes of the Trusted Origin - can either be CORS or REDIRECT only"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "okta_trusted_origin" "this" {
  active = var.active
  name   = var.name
  origin = var.origin
  scopes = var.scopes
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_trusted_origin.this.id
}

output "this" {
  value = okta_trusted_origin.this
}
```

[top](#index)