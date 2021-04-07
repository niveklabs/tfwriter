# aws_mq_broker

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_mq_broker" {
  source = "./modules/aws/r/aws_mq_broker"

  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # authentication_strategy - (optional) is a type of string
  authentication_strategy = null
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = null
  # broker_name - (required) is a type of string
  broker_name = null
  # deployment_mode - (optional) is a type of string
  deployment_mode = null
  # engine_type - (required) is a type of string
  engine_type = null
  # engine_version - (required) is a type of string
  engine_version = null
  # host_instance_type - (required) is a type of string
  host_instance_type = null
  # publicly_accessible - (optional) is a type of bool
  publicly_accessible = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # storage_type - (optional) is a type of string
  storage_type = null
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}

  configuration = [{
    id       = null
    revision = null
  }]

  encryption_options = [{
    kms_key_id        = null
    use_aws_owned_key = null
  }]

  ldap_server_metadata = [{
    hosts                    = []
    role_base                = null
    role_name                = null
    role_search_matching     = null
    role_search_subtree      = null
    service_account_password = null
    service_account_username = null
    user_base                = null
    user_role_name           = null
    user_search_matching     = null
    user_search_subtree      = null
  }]

  logs = [{
    audit   = null
    general = null
  }]

  maintenance_window_start_time = [{
    day_of_week = null
    time_of_day = null
    time_zone   = null
  }]

  user = [{
    console_access = null
    groups         = []
    password       = null
    username       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "apply_immediately" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "authentication_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_minor_version_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "broker_name" {
  description = "(required)"
  type        = string
}

variable "deployment_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_type" {
  description = "(required)"
  type        = string
}

variable "engine_version" {
  description = "(required)"
  type        = string
}

variable "host_instance_type" {
  description = "(required)"
  type        = string
}

variable "publicly_accessible" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id       = string
      revision = number
    }
  ))
  default = []
}

variable "encryption_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kms_key_id        = string
      use_aws_owned_key = bool
    }
  ))
  default = []
}

variable "ldap_server_metadata" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      hosts                    = list(string)
      role_base                = string
      role_name                = string
      role_search_matching     = string
      role_search_subtree      = bool
      service_account_password = string
      service_account_username = string
      user_base                = string
      user_role_name           = string
      user_search_matching     = string
      user_search_subtree      = bool
    }
  ))
  default = []
}

variable "logs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      audit   = bool
      general = bool
    }
  ))
  default = []
}

variable "maintenance_window_start_time" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      day_of_week = string
      time_of_day = string
      time_zone   = string
    }
  ))
  default = []
}

variable "user" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      console_access = bool
      groups         = set(string)
      password       = string
      username       = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_mq_broker" "this" {
  # apply_immediately - (optional) is a type of bool
  apply_immediately = var.apply_immediately
  # authentication_strategy - (optional) is a type of string
  authentication_strategy = var.authentication_strategy
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = var.auto_minor_version_upgrade
  # broker_name - (required) is a type of string
  broker_name = var.broker_name
  # deployment_mode - (optional) is a type of string
  deployment_mode = var.deployment_mode
  # engine_type - (required) is a type of string
  engine_type = var.engine_type
  # engine_version - (required) is a type of string
  engine_version = var.engine_version
  # host_instance_type - (required) is a type of string
  host_instance_type = var.host_instance_type
  # publicly_accessible - (optional) is a type of bool
  publicly_accessible = var.publicly_accessible
  # security_groups - (optional) is a type of set of string
  security_groups = var.security_groups
  # storage_type - (optional) is a type of string
  storage_type = var.storage_type
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = var.subnet_ids
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "configuration" {
    for_each = var.configuration
    content {
      # id - (optional) is a type of string
      id = configuration.value["id"]
      # revision - (optional) is a type of number
      revision = configuration.value["revision"]
    }
  }

  dynamic "encryption_options" {
    for_each = var.encryption_options
    content {
      # kms_key_id - (optional) is a type of string
      kms_key_id = encryption_options.value["kms_key_id"]
      # use_aws_owned_key - (optional) is a type of bool
      use_aws_owned_key = encryption_options.value["use_aws_owned_key"]
    }
  }

  dynamic "ldap_server_metadata" {
    for_each = var.ldap_server_metadata
    content {
      # hosts - (optional) is a type of list of string
      hosts = ldap_server_metadata.value["hosts"]
      # role_base - (optional) is a type of string
      role_base = ldap_server_metadata.value["role_base"]
      # role_name - (optional) is a type of string
      role_name = ldap_server_metadata.value["role_name"]
      # role_search_matching - (optional) is a type of string
      role_search_matching = ldap_server_metadata.value["role_search_matching"]
      # role_search_subtree - (optional) is a type of bool
      role_search_subtree = ldap_server_metadata.value["role_search_subtree"]
      # service_account_password - (optional) is a type of string
      service_account_password = ldap_server_metadata.value["service_account_password"]
      # service_account_username - (optional) is a type of string
      service_account_username = ldap_server_metadata.value["service_account_username"]
      # user_base - (optional) is a type of string
      user_base = ldap_server_metadata.value["user_base"]
      # user_role_name - (optional) is a type of string
      user_role_name = ldap_server_metadata.value["user_role_name"]
      # user_search_matching - (optional) is a type of string
      user_search_matching = ldap_server_metadata.value["user_search_matching"]
      # user_search_subtree - (optional) is a type of bool
      user_search_subtree = ldap_server_metadata.value["user_search_subtree"]
    }
  }

  dynamic "logs" {
    for_each = var.logs
    content {
      # audit - (optional) is a type of bool
      audit = logs.value["audit"]
      # general - (optional) is a type of bool
      general = logs.value["general"]
    }
  }

  dynamic "maintenance_window_start_time" {
    for_each = var.maintenance_window_start_time
    content {
      # day_of_week - (required) is a type of string
      day_of_week = maintenance_window_start_time.value["day_of_week"]
      # time_of_day - (required) is a type of string
      time_of_day = maintenance_window_start_time.value["time_of_day"]
      # time_zone - (required) is a type of string
      time_zone = maintenance_window_start_time.value["time_zone"]
    }
  }

  dynamic "user" {
    for_each = var.user
    content {
      # console_access - (optional) is a type of bool
      console_access = user.value["console_access"]
      # groups - (optional) is a type of set of string
      groups = user.value["groups"]
      # password - (required) is a type of string
      password = user.value["password"]
      # username - (required) is a type of string
      username = user.value["username"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_mq_broker.this.arn
}

output "authentication_strategy" {
  description = "returns a string"
  value       = aws_mq_broker.this.authentication_strategy
}

output "id" {
  description = "returns a string"
  value       = aws_mq_broker.this.id
}

output "instances" {
  description = "returns a list of object"
  value       = aws_mq_broker.this.instances
}

output "storage_type" {
  description = "returns a string"
  value       = aws_mq_broker.this.storage_type
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = aws_mq_broker.this.subnet_ids
}

output "this" {
  value = aws_mq_broker.this
}
```

[top](#index)