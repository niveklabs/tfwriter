# aws_mq_broker

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/aws/d/aws_mq_broker"

  # broker_id - (optional) is a type of string
  broker_id = null
  # broker_name - (optional) is a type of string
  broker_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  logs = [{
    audit   = null
    general = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "broker_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "broker_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
```

[top](#index)

### Datasource

```terraform
data "aws_mq_broker" "this" {
  # broker_id - (optional) is a type of string
  broker_id = var.broker_id
  # broker_name - (optional) is a type of string
  broker_name = var.broker_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "logs" {
    for_each = var.logs
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.arn
}

output "authentication_strategy" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.authentication_strategy
}

output "auto_minor_version_upgrade" {
  description = "returns a bool"
  value       = data.aws_mq_broker.this.auto_minor_version_upgrade
}

output "broker_id" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.broker_id
}

output "broker_name" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.broker_name
}

output "configuration" {
  description = "returns a list of object"
  value       = data.aws_mq_broker.this.configuration
}

output "deployment_mode" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.deployment_mode
}

output "encryption_options" {
  description = "returns a list of object"
  value       = data.aws_mq_broker.this.encryption_options
}

output "engine_type" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.engine_type
}

output "engine_version" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.engine_version
}

output "host_instance_type" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.host_instance_type
}

output "id" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.id
}

output "instances" {
  description = "returns a list of object"
  value       = data.aws_mq_broker.this.instances
}

output "ldap_server_metadata" {
  description = "returns a list of object"
  value       = data.aws_mq_broker.this.ldap_server_metadata
}

output "maintenance_window_start_time" {
  description = "returns a list of object"
  value       = data.aws_mq_broker.this.maintenance_window_start_time
}

output "publicly_accessible" {
  description = "returns a bool"
  value       = data.aws_mq_broker.this.publicly_accessible
}

output "security_groups" {
  description = "returns a set of string"
  value       = data.aws_mq_broker.this.security_groups
}

output "storage_type" {
  description = "returns a string"
  value       = data.aws_mq_broker.this.storage_type
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = data.aws_mq_broker.this.subnet_ids
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_mq_broker.this.tags
}

output "user" {
  description = "returns a set of object"
  value       = data.aws_mq_broker.this.user
}

output "this" {
  value = aws_mq_broker.this
}
```

[top](#index)