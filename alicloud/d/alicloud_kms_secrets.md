# alicloud_kms_secrets

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_kms_secrets" {
  source = "./modules/alicloud/d/alicloud_kms_secrets"

  # fetch_tags - (optional) is a type of bool
  fetch_tags = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "fetch_tags" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_kms_secrets" "this" {
  fetch_tags  = var.fetch_tags
  ids         = var.ids
  name_regex  = var.name_regex
  output_file = var.output_file
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_kms_secrets.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_kms_secrets.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_kms_secrets.this.names
}

output "secrets" {
  description = "returns a list of object"
  value       = data.alicloud_kms_secrets.this.secrets
}

output "this" {
  value = alicloud_kms_secrets.this
}
```

[top](#index)