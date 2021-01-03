# alicloud_dms_enterprise_instance

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_dms_enterprise_instance" {
  source = "./modules/alicloud/r/alicloud_dms_enterprise_instance"

  # data_link_name - (optional) is a type of string
  data_link_name = null
  # database_password - (required) is a type of string
  database_password = null
  # database_user - (required) is a type of string
  database_user = null
  # dba_id - (optional) is a type of string
  dba_id = null
  # dba_uid - (required) is a type of number
  dba_uid = null
  # ddl_online - (optional) is a type of number
  ddl_online = null
  # ecs_instance_id - (optional) is a type of string
  ecs_instance_id = null
  # ecs_region - (optional) is a type of string
  ecs_region = null
  # env_type - (required) is a type of string
  env_type = null
  # export_timeout - (required) is a type of number
  export_timeout = null
  # host - (required) is a type of string
  host = null
  # instance_alias - (optional) is a type of string
  instance_alias = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_source - (required) is a type of string
  instance_source = null
  # instance_type - (required) is a type of string
  instance_type = null
  # network_type - (required) is a type of string
  network_type = null
  # port - (required) is a type of number
  port = null
  # query_timeout - (required) is a type of number
  query_timeout = null
  # safe_rule - (required) is a type of string
  safe_rule = null
  # safe_rule_id - (optional) is a type of string
  safe_rule_id = null
  # sid - (optional) is a type of string
  sid = null
  # skip_test - (optional) is a type of bool
  skip_test = null
  # tid - (optional) is a type of number
  tid = null
  # use_dsql - (optional) is a type of number
  use_dsql = null
  # vpc_id - (optional) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "data_link_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_password" {
  description = "(required)"
  type        = string
}

variable "database_user" {
  description = "(required)"
  type        = string
}

variable "dba_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dba_uid" {
  description = "(required)"
  type        = number
}

variable "ddl_online" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ecs_instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ecs_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "env_type" {
  description = "(required)"
  type        = string
}

variable "export_timeout" {
  description = "(required)"
  type        = number
}

variable "host" {
  description = "(required)"
  type        = string
}

variable "instance_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_source" {
  description = "(required)"
  type        = string
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "network_type" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "query_timeout" {
  description = "(required)"
  type        = number
}

variable "safe_rule" {
  description = "(required)"
  type        = string
}

variable "safe_rule_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "skip_test" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_dsql" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_dms_enterprise_instance" "this" {
  data_link_name    = var.data_link_name
  database_password = var.database_password
  database_user     = var.database_user
  dba_id            = var.dba_id
  dba_uid           = var.dba_uid
  ddl_online        = var.ddl_online
  ecs_instance_id   = var.ecs_instance_id
  ecs_region        = var.ecs_region
  env_type          = var.env_type
  export_timeout    = var.export_timeout
  host              = var.host
  instance_alias    = var.instance_alias
  instance_id       = var.instance_id
  instance_name     = var.instance_name
  instance_source   = var.instance_source
  instance_type     = var.instance_type
  network_type      = var.network_type
  port              = var.port
  query_timeout     = var.query_timeout
  safe_rule         = var.safe_rule
  safe_rule_id      = var.safe_rule_id
  sid               = var.sid
  skip_test         = var.skip_test
  tid               = var.tid
  use_dsql          = var.use_dsql
  vpc_id            = var.vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dba_id" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.dba_id
}

output "dba_nick_name" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.dba_nick_name
}

output "ecs_instance_id" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.ecs_instance_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.id
}

output "instance_alias" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.instance_alias
}

output "instance_id" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.instance_id
}

output "instance_name" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.instance_name
}

output "safe_rule_id" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.safe_rule_id
}

output "state" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.state
}

output "status" {
  description = "returns a string"
  value       = alicloud_dms_enterprise_instance.this.status
}

output "this" {
  value = alicloud_dms_enterprise_instance.this
}
```

[top](#index)