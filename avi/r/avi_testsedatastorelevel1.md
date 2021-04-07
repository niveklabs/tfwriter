# avi_testsedatastorelevel1

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
module "avi_testsedatastorelevel1" {
  source = "./modules/avi/r/avi_testsedatastorelevel1"

  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # test_se_datastore_level_2_ref - (optional) is a type of string
  test_se_datastore_level_2_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "test_se_datastore_level_2_ref" {
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

### Resource

```terraform
resource "avi_testsedatastorelevel1" "this" {
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # test_se_datastore_level_2_ref - (optional) is a type of string
  test_se_datastore_level_2_ref = var.test_se_datastore_level_2_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_testsedatastorelevel1.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_testsedatastorelevel1.this.tenant_ref
}

output "test_se_datastore_level_2_ref" {
  description = "returns a string"
  value       = avi_testsedatastorelevel1.this.test_se_datastore_level_2_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_testsedatastorelevel1.this.uuid
}

output "this" {
  value = avi_testsedatastorelevel1.this
}
```

[top](#index)