# tencentcloud_ckafka_acls

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
module "tencentcloud_ckafka_acls" {
  source = "./modules/tencentcloud/d/tencentcloud_ckafka_acls"

  # host - (optional) is a type of string
  host = null
  # instance_id - (required) is a type of string
  instance_id = null
  # resource_name - (required) is a type of string
  resource_name = null
  # resource_type - (required) is a type of string
  resource_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "host" {
  description = "(optional) - Host substr used for querying."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - Id of the ckafka instance."
  type        = string
}

variable "resource_name" {
  description = "(required) - ACL resource name, which is related to `resource_type`. For example, if `resource_type` is `TOPIC`, this field indicates the topic name; if `resource_type` is `GROUP`, this field indicates the group name."
  type        = string
}

variable "resource_type" {
  description = "(required) - ACL resource type. Valid values are `UNKNOWN`, `ANY`, `TOPIC`, `GROUP`, `CLUSTER`, `TRANSACTIONAL_ID`. Currently, only `TOPIC` is available, and other fields will be used for future ACLs compatible with open-source Kafka."
  type        = string
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
data "tencentcloud_ckafka_acls" "this" {
  # host - (optional) is a type of string
  host = var.host
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # resource_name - (required) is a type of string
  resource_name = var.resource_name
  # resource_type - (required) is a type of string
  resource_type = var.resource_type
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "acl_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_ckafka_acls.this.acl_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_ckafka_acls.this.id
}

output "this" {
  value = tencentcloud_ckafka_acls.this
}
```

[top](#index)