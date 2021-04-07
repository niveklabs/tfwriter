# okta_auth_server

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
module "okta_auth_server" {
  source = "./modules/okta/r/okta_auth_server"

  # audiences - (required) is a type of set of string
  audiences = []
  # credentials_rotation_mode - (optional) is a type of string
  credentials_rotation_mode = null
  # description - (optional) is a type of string
  description = null
  # issuer_mode - (optional) is a type of string
  issuer_mode = null
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
  description = "(required) - Currently Okta only supports a single value here"
  type        = set(string)
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

variable "issuer_mode" {
  description = "(optional) - *Early Access Property*. Indicates which value is specified in the issuer of the tokens that a Custom Authorization Server returns: the original Okta org domain URL or a custom domain URL"
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
resource "okta_auth_server" "this" {
  # audiences - (required) is a type of set of string
  audiences = var.audiences
  # credentials_rotation_mode - (optional) is a type of string
  credentials_rotation_mode = var.credentials_rotation_mode
  # description - (optional) is a type of string
  description = var.description
  # issuer_mode - (optional) is a type of string
  issuer_mode = var.issuer_mode
  # name - (required) is a type of string
  name = var.name
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "credentials_last_rotated" {
  description = "returns a string"
  value       = okta_auth_server.this.credentials_last_rotated
}

output "credentials_next_rotation" {
  description = "returns a string"
  value       = okta_auth_server.this.credentials_next_rotation
}

output "id" {
  description = "returns a string"
  value       = okta_auth_server.this.id
}

output "issuer" {
  description = "returns a string"
  value       = okta_auth_server.this.issuer
}

output "kid" {
  description = "returns a string"
  value       = okta_auth_server.this.kid
}

output "this" {
  value = okta_auth_server.this
}
```

[top](#index)