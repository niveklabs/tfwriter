# mso_site

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_site" {
  source = "./modules/mso/d/mso_site"

  # apic_site_id - (optional) is a type of string
  apic_site_id = null
  # cloud_providers - (optional) is a type of list of string
  cloud_providers = []
  # labels - (optional) is a type of list of string
  labels = []
  # location - (optional) is a type of map of string
  location = {}
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # urls - (optional) is a type of list of string
  urls = []
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "apic_site_id" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "urls" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_site" "this" {
  apic_site_id    = var.apic_site_id
  cloud_providers = var.cloud_providers
  labels          = var.labels
  location        = var.location
  name            = var.name
  password        = var.password
  urls            = var.urls
  username        = var.username
}
```

[top](#index)

### Outputs

```terraform
output "cloud_providers" {
  description = "returns a list of string"
  value       = data.mso_site.this.cloud_providers
}

output "id" {
  description = "returns a string"
  value       = data.mso_site.this.id
}

output "labels" {
  description = "returns a list of string"
  value       = data.mso_site.this.labels
}

output "urls" {
  description = "returns a list of string"
  value       = data.mso_site.this.urls
}

output "this" {
  value = mso_site.this
}
```

[top](#index)