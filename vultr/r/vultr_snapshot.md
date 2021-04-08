# vultr_snapshot

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
module "vultr_snapshot" {
  source = "./modules/vultr/r/vultr_snapshot"

  # description - (optional) is a type of string
  description = null
  # instance_id - (required) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vultr_snapshot" "this" {
  # description - (optional) is a type of string
  description = var.description
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "app_id" {
  description = "returns a number"
  value       = vultr_snapshot.this.app_id
}

output "date_created" {
  description = "returns a string"
  value       = vultr_snapshot.this.date_created
}

output "id" {
  description = "returns a string"
  value       = vultr_snapshot.this.id
}

output "os_id" {
  description = "returns a number"
  value       = vultr_snapshot.this.os_id
}

output "size" {
  description = "returns a number"
  value       = vultr_snapshot.this.size
}

output "status" {
  description = "returns a string"
  value       = vultr_snapshot.this.status
}

output "this" {
  value = vultr_snapshot.this
}
```

[top](#index)