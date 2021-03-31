# aws_appsync_graphql_api

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
module "aws_appsync_graphql_api" {
  source = "./modules/aws/r/aws_appsync_graphql_api"

  # authentication_type - (required) is a type of string
  authentication_type = null
  # name - (required) is a type of string
  name = null
  # schema - (optional) is a type of string
  schema = null
  # tags - (optional) is a type of map of string
  tags = {}
  # xray_enabled - (optional) is a type of bool
  xray_enabled = null

  additional_authentication_provider = [{
    authentication_type = null
    openid_connect_config = [{
      auth_ttl  = null
      client_id = null
      iat_ttl   = null
      issuer    = null
    }]
    user_pool_config = [{
      app_id_client_regex = null
      aws_region          = null
      user_pool_id        = null
    }]
  }]

  log_config = [{
    cloudwatch_logs_role_arn = null
    exclude_verbose_content  = null
    field_log_level          = null
  }]

  openid_connect_config = [{
    auth_ttl  = null
    client_id = null
    iat_ttl   = null
    issuer    = null
  }]

  user_pool_config = [{
    app_id_client_regex = null
    aws_region          = null
    default_action      = null
    user_pool_id        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authentication_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "schema" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "xray_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "additional_authentication_provider" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      authentication_type = string
      openid_connect_config = list(object(
        {
          auth_ttl  = number
          client_id = string
          iat_ttl   = number
          issuer    = string
        }
      ))
      user_pool_config = list(object(
        {
          app_id_client_regex = string
          aws_region          = string
          user_pool_id        = string
        }
      ))
    }
  ))
  default = []
}

variable "log_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloudwatch_logs_role_arn = string
      exclude_verbose_content  = bool
      field_log_level          = string
    }
  ))
  default = []
}

variable "openid_connect_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_ttl  = number
      client_id = string
      iat_ttl   = number
      issuer    = string
    }
  ))
  default = []
}

variable "user_pool_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      app_id_client_regex = string
      aws_region          = string
      default_action      = string
      user_pool_id        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_appsync_graphql_api" "this" {
  authentication_type = var.authentication_type
  name                = var.name
  schema              = var.schema
  tags                = var.tags
  xray_enabled        = var.xray_enabled

  dynamic "additional_authentication_provider" {
    for_each = var.additional_authentication_provider
    content {
      authentication_type = additional_authentication_provider.value["authentication_type"]

      dynamic "openid_connect_config" {
        for_each = additional_authentication_provider.value.openid_connect_config
        content {
          auth_ttl  = openid_connect_config.value["auth_ttl"]
          client_id = openid_connect_config.value["client_id"]
          iat_ttl   = openid_connect_config.value["iat_ttl"]
          issuer    = openid_connect_config.value["issuer"]
        }
      }

      dynamic "user_pool_config" {
        for_each = additional_authentication_provider.value.user_pool_config
        content {
          app_id_client_regex = user_pool_config.value["app_id_client_regex"]
          aws_region          = user_pool_config.value["aws_region"]
          user_pool_id        = user_pool_config.value["user_pool_id"]
        }
      }

    }
  }

  dynamic "log_config" {
    for_each = var.log_config
    content {
      cloudwatch_logs_role_arn = log_config.value["cloudwatch_logs_role_arn"]
      exclude_verbose_content  = log_config.value["exclude_verbose_content"]
      field_log_level          = log_config.value["field_log_level"]
    }
  }

  dynamic "openid_connect_config" {
    for_each = var.openid_connect_config
    content {
      auth_ttl  = openid_connect_config.value["auth_ttl"]
      client_id = openid_connect_config.value["client_id"]
      iat_ttl   = openid_connect_config.value["iat_ttl"]
      issuer    = openid_connect_config.value["issuer"]
    }
  }

  dynamic "user_pool_config" {
    for_each = var.user_pool_config
    content {
      app_id_client_regex = user_pool_config.value["app_id_client_regex"]
      aws_region          = user_pool_config.value["aws_region"]
      default_action      = user_pool_config.value["default_action"]
      user_pool_id        = user_pool_config.value["user_pool_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_appsync_graphql_api.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_appsync_graphql_api.this.id
}

output "uris" {
  description = "returns a map of string"
  value       = aws_appsync_graphql_api.this.uris
}

output "this" {
  value = aws_appsync_graphql_api.this
}
```

[top](#index)