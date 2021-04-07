# avi_webhook

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
module "avi_webhook" {
  source = "./modules/avi/r/avi_webhook"

  # callback_url - (optional) is a type of string
  callback_url = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
  # verification_token - (optional) is a type of string
  verification_token = null
}
```

[top](#index)

### Variables

```terraform
variable "callback_url" {
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

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "verification_token" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_webhook" "this" {
  # callback_url - (optional) is a type of string
  callback_url = var.callback_url
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # verification_token - (optional) is a type of string
  verification_token = var.verification_token
}
```

[top](#index)

### Outputs

```terraform
output "callback_url" {
  description = "returns a string"
  value       = avi_webhook.this.callback_url
}

output "description" {
  description = "returns a string"
  value       = avi_webhook.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_webhook.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_webhook.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_webhook.this.uuid
}

output "verification_token" {
  description = "returns a string"
  value       = avi_webhook.this.verification_token
}

output "this" {
  value = avi_webhook.this
}
```

[top](#index)