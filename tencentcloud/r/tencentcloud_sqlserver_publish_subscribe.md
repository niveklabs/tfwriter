# tencentcloud_sqlserver_publish_subscribe

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
module "tencentcloud_sqlserver_publish_subscribe" {
  source = "./modules/tencentcloud/r/tencentcloud_sqlserver_publish_subscribe"

  # delete_subscribe_db - (optional) is a type of bool
  delete_subscribe_db = null
  # publish_instance_id - (required) is a type of string
  publish_instance_id = null
  # publish_subscribe_name - (optional) is a type of string
  publish_subscribe_name = null
  # subscribe_instance_id - (required) is a type of string
  subscribe_instance_id = null

  database_tuples = [{
    publish_database = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "delete_subscribe_db" {
  description = "(optional) - Whether to delete the subscriber database when deleting the Publish and Subscribe. `true` for deletes the subscribe database, `false` for does not delete the subscribe database. default is `false`."
  type        = bool
  default     = null
}

variable "publish_instance_id" {
  description = "(required) - ID of the SQL Server instance which publish."
  type        = string
}

variable "publish_subscribe_name" {
  description = "(optional) - The name of the Publish and Subscribe. Default is `default_name`."
  type        = string
  default     = null
}

variable "subscribe_instance_id" {
  description = "(required) - ID of the SQL Server instance which subscribe."
  type        = string
}

variable "database_tuples" {
  description = "nested block: NestingSet, min items: 1, max items: 80"
  type = set(object(
    {
      publish_database = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_sqlserver_publish_subscribe" "this" {
  # delete_subscribe_db - (optional) is a type of bool
  delete_subscribe_db = var.delete_subscribe_db
  # publish_instance_id - (required) is a type of string
  publish_instance_id = var.publish_instance_id
  # publish_subscribe_name - (optional) is a type of string
  publish_subscribe_name = var.publish_subscribe_name
  # subscribe_instance_id - (required) is a type of string
  subscribe_instance_id = var.subscribe_instance_id

  dynamic "database_tuples" {
    for_each = var.database_tuples
    content {
      # publish_database - (required) is a type of string
      publish_database = database_tuples.value["publish_database"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_publish_subscribe.this.id
}

output "this" {
  value = tencentcloud_sqlserver_publish_subscribe.this
}
```

[top](#index)