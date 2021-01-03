# newrelic_synthetics_secure_credential

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_synthetics_secure_credential" {
  source = "./modules/newrelic/r/newrelic_synthetics_secure_credential"

  # created_at - (optional) is a type of string
  created_at = null
  # description - (optional) is a type of string
  description = null
  # key - (required) is a type of string
  key = null
  # last_updated - (optional) is a type of string
  last_updated = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "created_at" {
  description = "(optional) - The time the secure credential was created."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - The secure credential's description."
  type        = string
  default     = null
}

variable "key" {
  description = "(required) - The secure credential's key name. Regardless of the case used in the configuration, the provider will provide an upcased key to the underlying API."
  type        = string
}

variable "last_updated" {
  description = "(optional) - The time the secure credential was last updated."
  type        = string
  default     = null
}

variable "value" {
  description = "(required) - The secure credential's value."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_synthetics_secure_credential" "this" {
  created_at   = var.created_at
  description  = var.description
  key          = var.key
  last_updated = var.last_updated
  value        = var.value
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = newrelic_synthetics_secure_credential.this.created_at
}

output "id" {
  description = "returns a string"
  value       = newrelic_synthetics_secure_credential.this.id
}

output "last_updated" {
  description = "returns a string"
  value       = newrelic_synthetics_secure_credential.this.last_updated
}

output "this" {
  value = newrelic_synthetics_secure_credential.this
}
```

[top](#index)