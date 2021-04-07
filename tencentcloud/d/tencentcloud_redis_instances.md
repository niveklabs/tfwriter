# tencentcloud_redis_instances

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
module "tencentcloud_redis_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_redis_instances"

  # limit - (optional) is a type of number
  limit = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # search_key - (optional) is a type of string
  search_key = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "limit" {
  description = "(optional) - The number limitation of results for a query."
  type        = number
  default     = null
}

variable "project_id" {
  description = "(optional) - ID of the project to which redis instance belongs."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "search_key" {
  description = "(optional) - Key words used to match the results, and the key words can be: instance ID, instance name and IP address."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of redis instance."
  type        = map(string)
  default     = null
}

variable "zone" {
  description = "(optional) - ID of an available zone."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_redis_instances" "this" {
  # limit - (optional) is a type of number
  limit = var.limit
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # search_key - (optional) is a type of string
  search_key = var.search_key
  # tags - (optional) is a type of map of string
  tags = var.tags
  # zone - (optional) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_redis_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_redis_instances.this.instance_list
}

output "this" {
  value = tencentcloud_redis_instances.this
}
```

[top](#index)