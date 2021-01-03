# datadog_logs_archive

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_logs_archive" {
  source = "./modules/datadog/r/datadog_logs_archive"

  # azure - (optional) is a type of map of string
  azure = {}
  # gcs - (optional) is a type of map of string
  gcs = {}
  # include_tags - (optional) is a type of bool
  include_tags = null
  # name - (required) is a type of string
  name = null
  # query - (required) is a type of string
  query = null
  # rehydration_tags - (optional) is a type of list of string
  rehydration_tags = []
  # s3 - (optional) is a type of map of string
  s3 = {}
}
```

[top](#index)

### Variables

```terraform
variable "azure" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "gcs" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "include_tags" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "query" {
  description = "(required)"
  type        = string
}

variable "rehydration_tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "s3" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_archive" "this" {
  azure            = var.azure
  gcs              = var.gcs
  include_tags     = var.include_tags
  name             = var.name
  query            = var.query
  rehydration_tags = var.rehydration_tags
  s3               = var.s3
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_logs_archive.this.id
}

output "this" {
  value = datadog_logs_archive.this
}
```

[top](#index)