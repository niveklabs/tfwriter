# packet_organization

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_organization" {
  source = "./modules/packet/r/packet_organization"

  # description - (optional) is a type of string
  description = null
  # logo - (optional) is a type of string
  logo = null
  # name - (required) is a type of string
  name = null
  # twitter - (optional) is a type of string
  twitter = null
  # website - (optional) is a type of string
  website = null
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

variable "logo" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "twitter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "website" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "packet_organization" "this" {
  # description - (optional) is a type of string
  description = var.description
  # logo - (optional) is a type of string
  logo = var.logo
  # name - (required) is a type of string
  name = var.name
  # twitter - (optional) is a type of string
  twitter = var.twitter
  # website - (optional) is a type of string
  website = var.website
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = packet_organization.this.created
}

output "id" {
  description = "returns a string"
  value       = packet_organization.this.id
}

output "updated" {
  description = "returns a string"
  value       = packet_organization.this.updated
}

output "this" {
  value = packet_organization.this
}
```

[top](#index)