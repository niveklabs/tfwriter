# ovh_domain_zone_redirection

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_domain_zone_redirection" {
  source = "./modules/ovh/r/ovh_domain_zone_redirection"

  # description - (optional) is a type of string
  description = null
  # keywords - (optional) is a type of string
  keywords = null
  # subdomain - (optional) is a type of string
  subdomain = null
  # target - (required) is a type of string
  target = null
  # title - (optional) is a type of string
  title = null
  # type - (required) is a type of string
  type = null
  # zone - (required) is a type of string
  zone = null
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

variable "keywords" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subdomain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target" {
  description = "(required)"
  type        = string
}

variable "title" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_domain_zone_redirection" "this" {
  # description - (optional) is a type of string
  description = var.description
  # keywords - (optional) is a type of string
  keywords = var.keywords
  # subdomain - (optional) is a type of string
  subdomain = var.subdomain
  # target - (required) is a type of string
  target = var.target
  # title - (optional) is a type of string
  title = var.title
  # type - (required) is a type of string
  type = var.type
  # zone - (required) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_domain_zone_redirection.this.id
}

output "this" {
  value = ovh_domain_zone_redirection.this
}
```

[top](#index)