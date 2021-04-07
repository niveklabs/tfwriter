# avi_alertemailconfig

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_alertemailconfig" {
  source = "./modules/avi/r/avi_alertemailconfig"

  # cc_emails - (optional) is a type of string
  cc_emails = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # to_emails - (required) is a type of string
  to_emails = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "cc_emails" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "to_emails" {
  description = "(required)"
  type        = string
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_alertemailconfig" "this" {
  # cc_emails - (optional) is a type of string
  cc_emails = var.cc_emails
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # to_emails - (required) is a type of string
  to_emails = var.to_emails
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "cc_emails" {
  description = "returns a string"
  value       = avi_alertemailconfig.this.cc_emails
}

output "description" {
  description = "returns a string"
  value       = avi_alertemailconfig.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_alertemailconfig.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_alertemailconfig.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_alertemailconfig.this.uuid
}

output "this" {
  value = avi_alertemailconfig.this
}
```

[top](#index)