# bigip_as3

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_as3" {
  source = "./modules/bigip/r/bigip_as3"

  # application_list - (optional) is a type of string
  application_list = null
  # as3_json - (required) is a type of string
  as3_json = null
  # tenant_filter - (optional) is a type of string
  tenant_filter = null
  # tenant_list - (optional) is a type of string
  tenant_list = null
  # tenant_name - (optional) is a type of string
  tenant_name = null
}
```

[top](#index)

### Variables

```terraform
variable "application_list" {
  description = "(optional) - Name of Application"
  type        = string
  default     = null
}

variable "as3_json" {
  description = "(required) - AS3 json"
  type        = string
}

variable "tenant_filter" {
  description = "(optional) - Name of Tenant"
  type        = string
  default     = null
}

variable "tenant_list" {
  description = "(optional) - Name of Tenant"
  type        = string
  default     = null
}

variable "tenant_name" {
  description = "(optional) - Name of Tenant"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_as3" "this" {
  application_list = var.application_list
  as3_json         = var.as3_json
  tenant_filter    = var.tenant_filter
  tenant_list      = var.tenant_list
  tenant_name      = var.tenant_name
}
```

[top](#index)

### Outputs

```terraform
output "application_list" {
  description = "returns a string"
  value       = bigip_as3.this.application_list
}

output "id" {
  description = "returns a string"
  value       = bigip_as3.this.id
}

output "tenant_list" {
  description = "returns a string"
  value       = bigip_as3.this.tenant_list
}

output "this" {
  value = bigip_as3.this
}
```

[top](#index)