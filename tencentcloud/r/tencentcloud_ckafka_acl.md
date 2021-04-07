# tencentcloud_ckafka_acl

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_ckafka_acl" {
  source = "./modules/tencentcloud/r/tencentcloud_ckafka_acl"

  # host - (optional) is a type of string
  host = null
  # instance_id - (required) is a type of string
  instance_id = null
  # operation_type - (required) is a type of string
  operation_type = null
  # permission_type - (optional) is a type of string
  permission_type = null
  # principal - (optional) is a type of string
  principal = null
  # resource_name - (required) is a type of string
  resource_name = null
  # resource_type - (optional) is a type of string
  resource_type = null
}
```

[top](#index)

### Variables

```terraform
variable "host" {
  description = "(optional) - IP address allowed to access. The default value is `*`, which means that any host can access."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - ID of the ckafka instance."
  type        = string
}

variable "operation_type" {
  description = "(required) - ACL operation mode. Valid values: `UNKNOWN`, `ANY`, `ALL`, `READ`, `WRITE`, `CREATE`, `DELETE`, `ALTER`, `DESCRIBE`, `CLUSTER_ACTION`, `DESCRIBE_CONFIGS` and `ALTER_CONFIGS`."
  type        = string
}

variable "permission_type" {
  description = "(optional) - ACL permission type. Valid values: `UNKNOWN`, `ANY`, `DENY`, `ALLOW`. and `ALLOW` by default. Currently, CKafka supports `ALLOW` (equivalent to allow list), and other fields will be used for future ACLs compatible with open-source Kafka."
  type        = string
  default     = null
}

variable "principal" {
  description = "(optional) - User list. The default value is `*`, which means that any user can access. The current user can only be one included in the user list."
  type        = string
  default     = null
}

variable "resource_name" {
  description = "(required) - ACL resource name, which is related to `resource_type`. For example, if `resource_type` is `TOPIC`, this field indicates the topic name; if `resource_type` is `GROUP`, this field indicates the group name."
  type        = string
}

variable "resource_type" {
  description = "(optional) - ACL resource type. Valid values are `UNKNOWN`, `ANY`, `TOPIC`, `GROUP`, `CLUSTER`, `TRANSACTIONAL_ID`. and `TOPIC` by default. Currently, only `TOPIC` is available, and other fields will be used for future ACLs compatible with open-source Kafka."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ckafka_acl" "this" {
  # host - (optional) is a type of string
  host = var.host
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # operation_type - (required) is a type of string
  operation_type = var.operation_type
  # permission_type - (optional) is a type of string
  permission_type = var.permission_type
  # principal - (optional) is a type of string
  principal = var.principal
  # resource_name - (required) is a type of string
  resource_name = var.resource_name
  # resource_type - (optional) is a type of string
  resource_type = var.resource_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_ckafka_acl.this.id
}

output "this" {
  value = tencentcloud_ckafka_acl.this
}
```

[top](#index)