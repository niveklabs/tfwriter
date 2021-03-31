# alicloud_ram_saml_provider

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_saml_provider" {
  source = "./modules/alicloud/r/alicloud_ram_saml_provider"

  # description - (optional) is a type of string
  description = null
  # encodedsaml_metadata_document - (optional) is a type of string
  encodedsaml_metadata_document = null
  # saml_provider_name - (required) is a type of string
  saml_provider_name = null
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

variable "encodedsaml_metadata_document" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "saml_provider_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_saml_provider" "this" {
  description                   = var.description
  encodedsaml_metadata_document = var.encodedsaml_metadata_document
  saml_provider_name            = var.saml_provider_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = alicloud_ram_saml_provider.this.arn
}

output "id" {
  description = "returns a string"
  value       = alicloud_ram_saml_provider.this.id
}

output "update_date" {
  description = "returns a string"
  value       = alicloud_ram_saml_provider.this.update_date
}

output "this" {
  value = alicloud_ram_saml_provider.this
}
```

[top](#index)