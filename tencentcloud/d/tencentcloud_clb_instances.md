# tencentcloud_clb_instances

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
module "tencentcloud_clb_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_clb_instances"

  # clb_id - (optional) is a type of string
  clb_id = null
  # clb_name - (optional) is a type of string
  clb_name = null
  # network_type - (optional) is a type of string
  network_type = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "clb_id" {
  description = "(optional) - ID of the CLB to be queried."
  type        = string
  default     = null
}

variable "clb_name" {
  description = "(optional) - Name of the CLB to be queried."
  type        = string
  default     = null
}

variable "network_type" {
  description = "(optional) - Type of CLB instance, and available values include `OPEN` and `INTERNAL`."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID of the CLB."
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
data "tencentcloud_clb_instances" "this" {
  clb_id             = var.clb_id
  clb_name           = var.clb_name
  network_type       = var.network_type
  project_id         = var.project_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "clb_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_clb_instances.this.clb_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_clb_instances.this.id
}

output "this" {
  value = tencentcloud_clb_instances.this
}
```

[top](#index)