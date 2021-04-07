# tencentcloud_ckafka_topics

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
module "tencentcloud_ckafka_topics" {
  source = "./modules/tencentcloud/d/tencentcloud_ckafka_topics"

  # instance_id - (required) is a type of string
  instance_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # topic_name - (optional) is a type of string
  topic_name = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - Ckafka instance ID."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}

variable "topic_name" {
  description = "(optional) - Name of the CKafka topic. It must start with a letter, the rest can contain letters, numbers and dashes(-). The length range is from 1 to 64."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_ckafka_topics" "this" {
  instance_id        = var.instance_id
  result_output_file = var.result_output_file
  topic_name         = var.topic_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_ckafka_topics.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_ckafka_topics.this.instance_list
}

output "this" {
  value = tencentcloud_ckafka_topics.this
}
```

[top](#index)