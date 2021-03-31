# aws_service_discovery_service

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_service_discovery_service" {
  source = "./modules/aws/r/aws_service_discovery_service"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  dns_config = [{
    dns_records = [{
      ttl  = null
      type = null
    }]
    namespace_id   = null
    routing_policy = null
  }]

  health_check_config = [{
    failure_threshold = null
    resource_path     = null
    type              = null
  }]

  health_check_custom_config = [{
    failure_threshold = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "dns_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dns_records = list(object(
        {
          ttl  = number
          type = string
        }
      ))
      namespace_id   = string
      routing_policy = string
    }
  ))
  default = []
}

variable "health_check_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      failure_threshold = number
      resource_path     = string
      type              = string
    }
  ))
  default = []
}

variable "health_check_custom_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      failure_threshold = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_service_discovery_service" "this" {
  description  = var.description
  name         = var.name
  namespace_id = var.namespace_id
  tags         = var.tags

  dynamic "dns_config" {
    for_each = var.dns_config
    content {
      namespace_id   = dns_config.value["namespace_id"]
      routing_policy = dns_config.value["routing_policy"]

      dynamic "dns_records" {
        for_each = dns_config.value.dns_records
        content {
          ttl  = dns_records.value["ttl"]
          type = dns_records.value["type"]
        }
      }

    }
  }

  dynamic "health_check_config" {
    for_each = var.health_check_config
    content {
      failure_threshold = health_check_config.value["failure_threshold"]
      resource_path     = health_check_config.value["resource_path"]
      type              = health_check_config.value["type"]
    }
  }

  dynamic "health_check_custom_config" {
    for_each = var.health_check_custom_config
    content {
      failure_threshold = health_check_custom_config.value["failure_threshold"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_service_discovery_service.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_service_discovery_service.this.id
}

output "namespace_id" {
  description = "returns a string"
  value       = aws_service_discovery_service.this.namespace_id
}

output "this" {
  value = aws_service_discovery_service.this
}
```

[top](#index)