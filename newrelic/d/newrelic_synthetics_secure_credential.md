# newrelic_synthetics_secure_credential

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_synthetics_secure_credential" {
  source = "./modules/newrelic/d/newrelic_synthetics_secure_credential"

  # key - (required) is a type of string
  key = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required) - The secure credential's key name. Regardless of the case used in the configuration, the provider will provide an upcased key to the underlying API."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_synthetics_secure_credential" "this" {
  # key - (required) is a type of string
  key = var.key
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.newrelic_synthetics_secure_credential.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.newrelic_synthetics_secure_credential.this.description
}

output "id" {
  description = "returns a string"
  value       = data.newrelic_synthetics_secure_credential.this.id
}

output "last_updated" {
  description = "returns a string"
  value       = data.newrelic_synthetics_secure_credential.this.last_updated
}

output "this" {
  value = newrelic_synthetics_secure_credential.this
}
```

[top](#index)