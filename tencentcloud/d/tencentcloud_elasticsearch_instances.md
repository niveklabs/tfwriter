# tencentcloud_elasticsearch_instances

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
module "tencentcloud_elasticsearch_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_elasticsearch_instances"

  # instance_id - (optional) is a type of string
  instance_id = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(optional) - ID of the instance to be queried."
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional) - Name of the instance to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tag of the instance to be queried."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_elasticsearch_instances" "this" {
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # instance_name - (optional) is a type of string
  instance_name = var.instance_name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_elasticsearch_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_elasticsearch_instances.this.instance_list
}

output "this" {
  value = tencentcloud_elasticsearch_instances.this
}
```

[top](#index)