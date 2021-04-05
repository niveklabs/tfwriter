# alicloud_kms_secret_versions

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_kms_secret_versions" {
  source = "./modules/alicloud/d/alicloud_kms_secret_versions"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # include_deprecated - (optional) is a type of string
  include_deprecated = null
  # output_file - (optional) is a type of string
  output_file = null
  # secret_name - (required) is a type of string
  secret_name = null
  # version_stage - (optional) is a type of string
  version_stage = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "include_deprecated" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_name" {
  description = "(required)"
  type        = string
}

variable "version_stage" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_kms_secret_versions" "this" {
  enable_details     = var.enable_details
  ids                = var.ids
  include_deprecated = var.include_deprecated
  output_file        = var.output_file
  secret_name        = var.secret_name
  version_stage      = var.version_stage
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_kms_secret_versions.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_kms_secret_versions.this.ids
}

output "versions" {
  description = "returns a list of object"
  value       = data.alicloud_kms_secret_versions.this.versions
}

output "this" {
  value = alicloud_kms_secret_versions.this
}
```

[top](#index)