# aci_configuration_import_policy

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_configuration_import_policy" {
  source = "./modules/aci/d/aci_configuration_import_policy"

  # admin_st - (optional) is a type of string
  admin_st = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # fail_on_decrypt_errors - (optional) is a type of string
  fail_on_decrypt_errors = null
  # file_name - (optional) is a type of string
  file_name = null
  # import_mode - (optional) is a type of string
  import_mode = null
  # import_type - (optional) is a type of string
  import_type = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # snapshot - (optional) is a type of string
  snapshot = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_st" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fail_on_decrypt_errors" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "import_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "import_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_configuration_import_policy" "this" {
  admin_st               = var.admin_st
  annotation             = var.annotation
  description            = var.description
  fail_on_decrypt_errors = var.fail_on_decrypt_errors
  file_name              = var.file_name
  import_mode            = var.import_mode
  import_type            = var.import_type
  name                   = var.name
  name_alias             = var.name_alias
  snapshot               = var.snapshot
}
```

[top](#index)

### Outputs

```terraform
output "admin_st" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.admin_st
}

output "description" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.description
}

output "fail_on_decrypt_errors" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.fail_on_decrypt_errors
}

output "file_name" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.file_name
}

output "id" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.id
}

output "import_mode" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.import_mode
}

output "import_type" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.import_type
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.name_alias
}

output "snapshot" {
  description = "returns a string"
  value       = data.aci_configuration_import_policy.this.snapshot
}

output "this" {
  value = aci_configuration_import_policy.this
}
```

[top](#index)