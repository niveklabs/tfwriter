# avi_alertemailconfig

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/avi/d/avi_alertemailconfig"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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
```

[top](#index)

### Datasource

```terraform
data "avi_alertemailconfig" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "cc_emails" {
  description = "returns a string"
  value       = data.avi_alertemailconfig.this.cc_emails
}

output "description" {
  description = "returns a string"
  value       = data.avi_alertemailconfig.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_alertemailconfig.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_alertemailconfig.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_alertemailconfig.this.tenant_ref
}

output "to_emails" {
  description = "returns a string"
  value       = data.avi_alertemailconfig.this.to_emails
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_alertemailconfig.this.uuid
}

output "this" {
  value = avi_alertemailconfig.this
}
```

[top](#index)