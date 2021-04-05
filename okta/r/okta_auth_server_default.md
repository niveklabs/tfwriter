# okta_auth_server_default

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
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_auth_server_default" {
  source = "./modules/okta/r/okta_auth_server_default"

  # audiences - (optional) is a type of set of string
  audiences = []
  # credentials_rotation_mode - (optional) is a type of string
  credentials_rotation_mode = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "audiences" {
  description = "(optional) - Currently Okta only supports a single value here"
  type        = set(string)
  default     = null
}

variable "credentials_rotation_mode" {
  description = "(optional) - Credential rotation mode, in many cases you cannot set this to MANUAL, the API will ignore the value and you will get a perpetual diff. This should rarely be used."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_auth_server_default" "this" {
  audiences                 = var.audiences
  credentials_rotation_mode = var.credentials_rotation_mode
  description               = var.description
  name                      = var.name
  status                    = var.status
}
```

[top](#index)

### Outputs

```terraform
output "credentials_last_rotated" {
  description = "returns a string"
  value       = okta_auth_server_default.this.credentials_last_rotated
}

output "credentials_next_rotation" {
  description = "returns a string"
  value       = okta_auth_server_default.this.credentials_next_rotation
}

output "id" {
  description = "returns a string"
  value       = okta_auth_server_default.this.id
}

output "issuer" {
  description = "returns a string"
  value       = okta_auth_server_default.this.issuer
}

output "kid" {
  description = "returns a string"
  value       = okta_auth_server_default.this.kid
}

output "this" {
  value = okta_auth_server_default.this
}
```

[top](#index)