# vultr_snapshot_from_url

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_snapshot_from_url" {
  source = "./modules/vultr/r/vultr_snapshot_from_url"

  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vultr_snapshot_from_url" "this" {
  # url - (required) is a type of string
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "app_id" {
  description = "returns a number"
  value       = vultr_snapshot_from_url.this.app_id
}

output "date_created" {
  description = "returns a string"
  value       = vultr_snapshot_from_url.this.date_created
}

output "description" {
  description = "returns a string"
  value       = vultr_snapshot_from_url.this.description
}

output "id" {
  description = "returns a string"
  value       = vultr_snapshot_from_url.this.id
}

output "os_id" {
  description = "returns a number"
  value       = vultr_snapshot_from_url.this.os_id
}

output "size" {
  description = "returns a number"
  value       = vultr_snapshot_from_url.this.size
}

output "status" {
  description = "returns a string"
  value       = vultr_snapshot_from_url.this.status
}

output "this" {
  value = vultr_snapshot_from_url.this
}
```

[top](#index)