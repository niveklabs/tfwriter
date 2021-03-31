# dme_domain

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_domain" {
  source = "./modules/dme/d/dme_domain"

  # created - (optional) is a type of string
  created = null
  # folder_id - (optional) is a type of string
  folder_id = null
  # gtd_enabled - (optional) is a type of string
  gtd_enabled = null
  # name - (required) is a type of string
  name = null
  # soa_id - (optional) is a type of string
  soa_id = null
  # template_id - (optional) is a type of string
  template_id = null
  # transfer_acl_id - (optional) is a type of string
  transfer_acl_id = null
  # updated - (optional) is a type of string
  updated = null
  # vanity_id - (optional) is a type of string
  vanity_id = null
}
```

[top](#index)

### Variables

```terraform
variable "created" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "folder_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gtd_enabled" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "soa_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "transfer_acl_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "updated" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vanity_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "dme_domain" "this" {
  created         = var.created
  folder_id       = var.folder_id
  gtd_enabled     = var.gtd_enabled
  name            = var.name
  soa_id          = var.soa_id
  template_id     = var.template_id
  transfer_acl_id = var.transfer_acl_id
  updated         = var.updated
  vanity_id       = var.vanity_id
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.dme_domain.this.created
}

output "folder_id" {
  description = "returns a string"
  value       = data.dme_domain.this.folder_id
}

output "gtd_enabled" {
  description = "returns a string"
  value       = data.dme_domain.this.gtd_enabled
}

output "id" {
  description = "returns a string"
  value       = data.dme_domain.this.id
}

output "soa_id" {
  description = "returns a string"
  value       = data.dme_domain.this.soa_id
}

output "template_id" {
  description = "returns a string"
  value       = data.dme_domain.this.template_id
}

output "transfer_acl_id" {
  description = "returns a string"
  value       = data.dme_domain.this.transfer_acl_id
}

output "updated" {
  description = "returns a string"
  value       = data.dme_domain.this.updated
}

output "vanity_id" {
  description = "returns a string"
  value       = data.dme_domain.this.vanity_id
}

output "this" {
  value = dme_domain.this
}
```

[top](#index)