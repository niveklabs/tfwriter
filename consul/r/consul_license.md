# consul_license

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_license" {
  source = "./modules/consul/r/consul_license"

  # datacenter - (optional) is a type of string
  datacenter = null
  # license - (required) is a type of string
  license = null
}
```

[top](#index)

### Variables

```terraform
variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "consul_license" "this" {
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # license - (required) is a type of string
  license = var.license
}
```

[top](#index)

### Outputs

```terraform
output "customer_id" {
  description = "returns a string"
  value       = consul_license.this.customer_id
}

output "expiration_time" {
  description = "returns a string"
  value       = consul_license.this.expiration_time
}

output "features" {
  description = "returns a list of string"
  value       = consul_license.this.features
}

output "id" {
  description = "returns a string"
  value       = consul_license.this.id
}

output "installation_id" {
  description = "returns a string"
  value       = consul_license.this.installation_id
}

output "issue_time" {
  description = "returns a string"
  value       = consul_license.this.issue_time
}

output "license_id" {
  description = "returns a string"
  value       = consul_license.this.license_id
}

output "product" {
  description = "returns a string"
  value       = consul_license.this.product
}

output "start_time" {
  description = "returns a string"
  value       = consul_license.this.start_time
}

output "valid" {
  description = "returns a bool"
  value       = consul_license.this.valid
}

output "warnings" {
  description = "returns a list of string"
  value       = consul_license.this.warnings
}

output "this" {
  value = consul_license.this
}
```

[top](#index)