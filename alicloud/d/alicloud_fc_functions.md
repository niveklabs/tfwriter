# alicloud_fc_functions

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
module "alicloud_fc_functions" {
  source = "./modules/alicloud/d/alicloud_fc_functions"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
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

variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_fc_functions" "this" {
  ids          = var.ids
  name_regex   = var.name_regex
  output_file  = var.output_file
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "functions" {
  description = "returns a list of object"
  value       = data.alicloud_fc_functions.this.functions
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_fc_functions.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_fc_functions.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_fc_functions.this.names
}

output "this" {
  value = alicloud_fc_functions.this
}
```

[top](#index)