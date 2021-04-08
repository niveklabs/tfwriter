# vultr_iso_private

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
module "vultr_iso_private" {
  source = "./modules/vultr/r/vultr_iso_private"

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
resource "vultr_iso_private" "this" {
  # url - (required) is a type of string
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = vultr_iso_private.this.date_created
}

output "filename" {
  description = "returns a string"
  value       = vultr_iso_private.this.filename
}

output "id" {
  description = "returns a string"
  value       = vultr_iso_private.this.id
}

output "md5sum" {
  description = "returns a string"
  value       = vultr_iso_private.this.md5sum
}

output "sha512sum" {
  description = "returns a string"
  value       = vultr_iso_private.this.sha512sum
}

output "size" {
  description = "returns a number"
  value       = vultr_iso_private.this.size
}

output "status" {
  description = "returns a string"
  value       = vultr_iso_private.this.status
}

output "this" {
  value = vultr_iso_private.this
}
```

[top](#index)