# mso_site

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_site" {
  source = "./modules/mso/r/mso_site"

  # apic_site_id - (required) is a type of string
  apic_site_id = null
  # cloud_providers - (optional) is a type of list of string
  cloud_providers = []
  # labels - (optional) is a type of list of string
  labels = []
  # location - (optional) is a type of map of string
  location = {}
  # login_domain - (optional) is a type of string
  login_domain = null
  # maintenance_mode - (optional) is a type of bool
  maintenance_mode = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # platform - (optional) is a type of string
  platform = null
  # urls - (required) is a type of list of string
  urls = []
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "apic_site_id" {
  description = "(required)"
  type        = string
}

variable "cloud_providers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "location" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "login_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintenance_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "urls" {
  description = "(required)"
  type        = list(string)
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_site" "this" {
  apic_site_id     = var.apic_site_id
  cloud_providers  = var.cloud_providers
  labels           = var.labels
  location         = var.location
  login_domain     = var.login_domain
  maintenance_mode = var.maintenance_mode
  name             = var.name
  password         = var.password
  platform         = var.platform
  urls             = var.urls
  username         = var.username
}
```

[top](#index)

### Outputs

```terraform
output "cloud_providers" {
  description = "returns a list of string"
  value       = mso_site.this.cloud_providers
}

output "id" {
  description = "returns a string"
  value       = mso_site.this.id
}

output "labels" {
  description = "returns a list of string"
  value       = mso_site.this.labels
}

output "login_domain" {
  description = "returns a string"
  value       = mso_site.this.login_domain
}

output "platform" {
  description = "returns a string"
  value       = mso_site.this.platform
}

output "this" {
  value = mso_site.this
}
```

[top](#index)