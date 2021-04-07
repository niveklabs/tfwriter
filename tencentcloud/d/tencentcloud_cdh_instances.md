# tencentcloud_cdh_instances

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
module "tencentcloud_cdh_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_cdh_instances"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # host_id - (optional) is a type of string
  host_id = null
  # host_name - (optional) is a type of string
  host_name = null
  # host_state - (optional) is a type of string
  host_state = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional) - The available zone that the CDH instance locates at."
  type        = string
  default     = null
}

variable "host_id" {
  description = "(optional) - ID of the CDH instances to be queried."
  type        = string
  default     = null
}

variable "host_name" {
  description = "(optional) - Name of the CDH instances to be queried."
  type        = string
  default     = null
}

variable "host_state" {
  description = "(optional) - State of the CDH instances to be queried. Valid values: `PENDING`, `LAUNCH_FAILURE`, `RUNNING`, `EXPIRED`."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project CDH belongs to."
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
data "tencentcloud_cdh_instances" "this" {
  availability_zone  = var.availability_zone
  host_id            = var.host_id
  host_name          = var.host_name
  host_state         = var.host_state
  project_id         = var.project_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "cdh_instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cdh_instances.this.cdh_instance_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cdh_instances.this.id
}

output "this" {
  value = tencentcloud_cdh_instances.this
}
```

[top](#index)