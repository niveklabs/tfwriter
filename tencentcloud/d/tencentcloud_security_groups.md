# tencentcloud_security_groups

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
module "tencentcloud_security_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_security_groups"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the security group to be queried. Conflict with `security_group_id`."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID of the security group to be queried. Conflict with `security_group_id`."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional) - ID of the security group to be queried. Conflict with `name` and `project_id`."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the security group to be queried. Conflict with `security_group_id`."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_security_groups" "this" {
  name               = var.name
  project_id         = var.project_id
  result_output_file = var.result_output_file
  security_group_id  = var.security_group_id
  tags               = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_security_groups.this.id
}

output "security_groups" {
  description = "returns a list of object"
  value       = data.tencentcloud_security_groups.this.security_groups
}

output "this" {
  value = tencentcloud_security_groups.this
}
```

[top](#index)