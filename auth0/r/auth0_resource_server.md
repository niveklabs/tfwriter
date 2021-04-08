# auth0_resource_server

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
module "auth0_resource_server" {
  source = "./modules/auth0/r/auth0_resource_server"

  # allow_offline_access - (optional) is a type of bool
  allow_offline_access = null
  # enforce_policies - (optional) is a type of bool
  enforce_policies = null
  # identifier - (optional) is a type of string
  identifier = null
  # name - (optional) is a type of string
  name = null
  # options - (optional) is a type of map of string
  options = {}
  # signing_alg - (optional) is a type of string
  signing_alg = null
  # signing_secret - (optional) is a type of string
  signing_secret = null
  # skip_consent_for_verifiable_first_party_clients - (optional) is a type of bool
  skip_consent_for_verifiable_first_party_clients = null
  # token_dialect - (optional) is a type of string
  token_dialect = null
  # token_lifetime - (optional) is a type of number
  token_lifetime = null
  # token_lifetime_for_web - (optional) is a type of number
  token_lifetime_for_web = null
  # verification_location - (optional) is a type of string
  verification_location = null

  scopes = [{
    description = null
    value       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_offline_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enforce_policies" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "signing_alg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signing_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "skip_consent_for_verifiable_first_party_clients" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "token_dialect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "token_lifetime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "token_lifetime_for_web" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "verification_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scopes" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      value       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "auth0_resource_server" "this" {
  # allow_offline_access - (optional) is a type of bool
  allow_offline_access = var.allow_offline_access
  # enforce_policies - (optional) is a type of bool
  enforce_policies = var.enforce_policies
  # identifier - (optional) is a type of string
  identifier = var.identifier
  # name - (optional) is a type of string
  name = var.name
  # options - (optional) is a type of map of string
  options = var.options
  # signing_alg - (optional) is a type of string
  signing_alg = var.signing_alg
  # signing_secret - (optional) is a type of string
  signing_secret = var.signing_secret
  # skip_consent_for_verifiable_first_party_clients - (optional) is a type of bool
  skip_consent_for_verifiable_first_party_clients = var.skip_consent_for_verifiable_first_party_clients
  # token_dialect - (optional) is a type of string
  token_dialect = var.token_dialect
  # token_lifetime - (optional) is a type of number
  token_lifetime = var.token_lifetime
  # token_lifetime_for_web - (optional) is a type of number
  token_lifetime_for_web = var.token_lifetime_for_web
  # verification_location - (optional) is a type of string
  verification_location = var.verification_location

  dynamic "scopes" {
    for_each = var.scopes
    content {
      # description - (optional) is a type of string
      description = scopes.value["description"]
      # value - (required) is a type of string
      value = scopes.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_resource_server.this.id
}

output "signing_alg" {
  description = "returns a string"
  value       = auth0_resource_server.this.signing_alg
}

output "signing_secret" {
  description = "returns a string"
  value       = auth0_resource_server.this.signing_secret
}

output "token_lifetime" {
  description = "returns a number"
  value       = auth0_resource_server.this.token_lifetime
}

output "token_lifetime_for_web" {
  description = "returns a number"
  value       = auth0_resource_server.this.token_lifetime_for_web
}

output "this" {
  value = auth0_resource_server.this
}
```

[top](#index)