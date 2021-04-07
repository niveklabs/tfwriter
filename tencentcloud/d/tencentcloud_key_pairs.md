# tencentcloud_key_pairs

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_key_pairs" {
  source = "./modules/tencentcloud/d/tencentcloud_key_pairs"

  # key_id - (optional) is a type of string
  key_id = null
  # key_name - (optional) is a type of string
  key_name = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "key_id" {
  description = "(optional) - ID of the key pair to be queried."
  type        = string
  default     = null
}

variable "key_name" {
  description = "(optional) - Name of the key pair to be queried. Support regular expression search, only `^` and `$` are supported."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID of the key pair to be queried."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_key_pairs" "this" {
  key_id             = var.key_id
  key_name           = var.key_name
  project_id         = var.project_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_key_pairs.this.id
}

output "key_pair_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_key_pairs.this.key_pair_list
}

output "this" {
  value = tencentcloud_key_pairs.this
}
```

[top](#index)