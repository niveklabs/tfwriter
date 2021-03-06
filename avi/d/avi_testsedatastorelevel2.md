# avi_testsedatastorelevel2

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
module "avi_testsedatastorelevel2" {
  source = "./modules/avi/d/avi_testsedatastorelevel2"

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
data "avi_testsedatastorelevel2" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.avi_testsedatastorelevel2.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_testsedatastorelevel2.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_testsedatastorelevel2.this.tenant_ref
}

output "test_se_datastore_level_3_refs" {
  description = "returns a list of string"
  value       = data.avi_testsedatastorelevel2.this.test_se_datastore_level_3_refs
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_testsedatastorelevel2.this.uuid
}

output "this" {
  value = avi_testsedatastorelevel2.this
}
```

[top](#index)