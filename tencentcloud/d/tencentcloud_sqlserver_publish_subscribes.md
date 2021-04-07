# tencentcloud_sqlserver_publish_subscribes

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
module "tencentcloud_sqlserver_publish_subscribes" {
  source = "./modules/tencentcloud/d/tencentcloud_sqlserver_publish_subscribes"

  # instance_id - (required) is a type of string
  instance_id = null
  # pub_or_sub_instance_id - (optional) is a type of string
  pub_or_sub_instance_id = null
  # pub_or_sub_instance_ip - (optional) is a type of string
  pub_or_sub_instance_ip = null
  # publish_database - (optional) is a type of string
  publish_database = null
  # publish_subscribe_id - (optional) is a type of number
  publish_subscribe_id = null
  # publish_subscribe_name - (optional) is a type of string
  publish_subscribe_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # subscribe_database - (optional) is a type of string
  subscribe_database = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - ID of the SQL Server instance."
  type        = string
}

variable "pub_or_sub_instance_id" {
  description = "(optional) - The subscribe/publish instance ID. It is related to whether the `instance_id` is a publish instance or a subscribe instance. when `instance_id` is a publish instance, this field is filtered according to the subscribe instance ID; when `instance_id` is a subscribe instance, this field is filtering according to the publish instance ID."
  type        = string
  default     = null
}

variable "pub_or_sub_instance_ip" {
  description = "(optional) - The intranet IP of the subscribe/publish instance. It is related to whether the `instance_id` is a publish instance or a subscribe instance. when `instance_id` is a publish instance, this field is filtered according to the intranet IP of the subscribe instance; when `instance_id` is a subscribe instance, this field is based on the publish instance intranet IP filter."
  type        = string
  default     = null
}

variable "publish_database" {
  description = "(optional) - Name of publish database."
  type        = string
  default     = null
}

variable "publish_subscribe_id" {
  description = "(optional) - The id of the Publish and Subscribe."
  type        = number
  default     = null
}

variable "publish_subscribe_name" {
  description = "(optional) - The name of the Publish and Subscribe."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}

variable "subscribe_database" {
  description = "(optional) - Name of subscribe database."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_sqlserver_publish_subscribes" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # pub_or_sub_instance_id - (optional) is a type of string
  pub_or_sub_instance_id = var.pub_or_sub_instance_id
  # pub_or_sub_instance_ip - (optional) is a type of string
  pub_or_sub_instance_ip = var.pub_or_sub_instance_ip
  # publish_database - (optional) is a type of string
  publish_database = var.publish_database
  # publish_subscribe_id - (optional) is a type of number
  publish_subscribe_id = var.publish_subscribe_id
  # publish_subscribe_name - (optional) is a type of string
  publish_subscribe_name = var.publish_subscribe_name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # subscribe_database - (optional) is a type of string
  subscribe_database = var.subscribe_database
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_sqlserver_publish_subscribes.this.id
}

output "publish_subscribe_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_sqlserver_publish_subscribes.this.publish_subscribe_list
}

output "this" {
  value = tencentcloud_sqlserver_publish_subscribes.this
}
```

[top](#index)