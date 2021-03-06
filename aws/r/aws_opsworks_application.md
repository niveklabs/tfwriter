# aws_opsworks_application

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
module "aws_opsworks_application" {
  source = "./modules/aws/r/aws_opsworks_application"

  # auto_bundle_on_deploy - (optional) is a type of string
  auto_bundle_on_deploy = null
  # aws_flow_ruby_settings - (optional) is a type of string
  aws_flow_ruby_settings = null
  # data_source_arn - (optional) is a type of string
  data_source_arn = null
  # data_source_database_name - (optional) is a type of string
  data_source_database_name = null
  # data_source_type - (optional) is a type of string
  data_source_type = null
  # description - (optional) is a type of string
  description = null
  # document_root - (optional) is a type of string
  document_root = null
  # domains - (optional) is a type of list of string
  domains = []
  # enable_ssl - (optional) is a type of bool
  enable_ssl = null
  # name - (required) is a type of string
  name = null
  # rails_env - (optional) is a type of string
  rails_env = null
  # short_name - (optional) is a type of string
  short_name = null
  # stack_id - (required) is a type of string
  stack_id = null
  # type - (required) is a type of string
  type = null

  app_source = [{
    password = null
    revision = null
    ssh_key  = null
    type     = null
    url      = null
    username = null
  }]

  environment = [{
    key    = null
    secure = null
    value  = null
  }]

  ssl_configuration = [{
    certificate = null
    chain       = null
    private_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_bundle_on_deploy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_flow_ruby_settings" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_source_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_source_database_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_source_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "document_root" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domains" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "enable_ssl" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rails_env" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "short_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack_id" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "app_source" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      password = string
      revision = string
      ssh_key  = string
      type     = string
      url      = string
      username = string
    }
  ))
  default = []
}

variable "environment" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key    = string
      secure = bool
      value  = string
    }
  ))
  default = []
}

variable "ssl_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate = string
      chain       = string
      private_key = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_opsworks_application" "this" {
  # auto_bundle_on_deploy - (optional) is a type of string
  auto_bundle_on_deploy = var.auto_bundle_on_deploy
  # aws_flow_ruby_settings - (optional) is a type of string
  aws_flow_ruby_settings = var.aws_flow_ruby_settings
  # data_source_arn - (optional) is a type of string
  data_source_arn = var.data_source_arn
  # data_source_database_name - (optional) is a type of string
  data_source_database_name = var.data_source_database_name
  # data_source_type - (optional) is a type of string
  data_source_type = var.data_source_type
  # description - (optional) is a type of string
  description = var.description
  # document_root - (optional) is a type of string
  document_root = var.document_root
  # domains - (optional) is a type of list of string
  domains = var.domains
  # enable_ssl - (optional) is a type of bool
  enable_ssl = var.enable_ssl
  # name - (required) is a type of string
  name = var.name
  # rails_env - (optional) is a type of string
  rails_env = var.rails_env
  # short_name - (optional) is a type of string
  short_name = var.short_name
  # stack_id - (required) is a type of string
  stack_id = var.stack_id
  # type - (required) is a type of string
  type = var.type

  dynamic "app_source" {
    for_each = var.app_source
    content {
      # password - (optional) is a type of string
      password = app_source.value["password"]
      # revision - (optional) is a type of string
      revision = app_source.value["revision"]
      # ssh_key - (optional) is a type of string
      ssh_key = app_source.value["ssh_key"]
      # type - (required) is a type of string
      type = app_source.value["type"]
      # url - (optional) is a type of string
      url = app_source.value["url"]
      # username - (optional) is a type of string
      username = app_source.value["username"]
    }
  }

  dynamic "environment" {
    for_each = var.environment
    content {
      # key - (required) is a type of string
      key = environment.value["key"]
      # secure - (optional) is a type of bool
      secure = environment.value["secure"]
      # value - (required) is a type of string
      value = environment.value["value"]
    }
  }

  dynamic "ssl_configuration" {
    for_each = var.ssl_configuration
    content {
      # certificate - (required) is a type of string
      certificate = ssl_configuration.value["certificate"]
      # chain - (optional) is a type of string
      chain = ssl_configuration.value["chain"]
      # private_key - (required) is a type of string
      private_key = ssl_configuration.value["private_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_opsworks_application.this.id
}

output "short_name" {
  description = "returns a string"
  value       = aws_opsworks_application.this.short_name
}

output "this" {
  value = aws_opsworks_application.this
}
```

[top](#index)