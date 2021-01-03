# prismacloud_integration

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.0.8"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_integration" {
  source = "./modules/prismacloud/r/prismacloud_integration"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # integration_type - (required) is a type of string
  integration_type = null
  # name - (required) is a type of string
  name = null

  integration_config = [{
    auth_token = null
    base_url   = null
    headers = [{
      key       = null
      read_only = null
      secure    = null
      value     = null
    }]
    host_url        = null
    integration_key = null
    login           = null
    password        = null
    queue_url       = null
    tables          = {}
    url             = null
    version         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Enabled"
  type        = bool
  default     = null
}

variable "integration_type" {
  description = "(required) - Integration type"
  type        = string
}

variable "name" {
  description = "(required) - Name of the integration"
  type        = string
}

variable "integration_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      auth_token = string
      base_url   = string
      headers = list(object(
        {
          key       = string
          read_only = bool
          secure    = bool
          value     = string
        }
      ))
      host_url        = string
      integration_key = string
      login           = string
      password        = string
      queue_url       = string
      tables          = map(bool)
      url             = string
      version         = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_integration" "this" {
  description      = var.description
  enabled          = var.enabled
  integration_type = var.integration_type
  name             = var.name

  dynamic "integration_config" {
    for_each = var.integration_config
    content {
      auth_token      = integration_config.value["auth_token"]
      base_url        = integration_config.value["base_url"]
      host_url        = integration_config.value["host_url"]
      integration_key = integration_config.value["integration_key"]
      login           = integration_config.value["login"]
      password        = integration_config.value["password"]
      queue_url       = integration_config.value["queue_url"]
      tables          = integration_config.value["tables"]
      url             = integration_config.value["url"]
      version         = integration_config.value["version"]

      dynamic "headers" {
        for_each = integration_config.value.headers
        content {
          key       = headers.value["key"]
          read_only = headers.value["read_only"]
          secure    = headers.value["secure"]
          value     = headers.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = prismacloud_integration.this.created_by
}

output "created_ts" {
  description = "returns a number"
  value       = prismacloud_integration.this.created_ts
}

output "id" {
  description = "returns a string"
  value       = prismacloud_integration.this.id
}

output "integration_id" {
  description = "returns a string"
  value       = prismacloud_integration.this.integration_id
}

output "last_modified_by" {
  description = "returns a string"
  value       = prismacloud_integration.this.last_modified_by
}

output "last_modified_ts" {
  description = "returns a number"
  value       = prismacloud_integration.this.last_modified_ts
}

output "reason" {
  description = "returns a list of object"
  value       = prismacloud_integration.this.reason
}

output "status" {
  description = "returns a string"
  value       = prismacloud_integration.this.status
}

output "valid" {
  description = "returns a bool"
  value       = prismacloud_integration.this.valid
}

output "this" {
  value = prismacloud_integration.this
}
```

[top](#index)