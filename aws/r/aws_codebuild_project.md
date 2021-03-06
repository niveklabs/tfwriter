# aws_codebuild_project

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
module "aws_codebuild_project" {
  source = [{
    auth = [{
      resource = null
      type     = null
    }]
    buildspec       = null
    git_clone_depth = null
    git_submodules_config = [{
      fetch_submodules = null
    }]
    insecure_ssl        = null
    location            = null
    report_build_status = null
    type                = null
  }]

  # badge_enabled - (optional) is a type of bool
  badge_enabled = null
  # build_timeout - (optional) is a type of number
  build_timeout = null
  # description - (optional) is a type of string
  description = null
  # encryption_key - (optional) is a type of string
  encryption_key = null
  # name - (required) is a type of string
  name = null
  # queued_timeout - (optional) is a type of number
  queued_timeout = null
  # service_role - (required) is a type of string
  service_role = null
  # source_version - (optional) is a type of string
  source_version = null
  # tags - (optional) is a type of map of string
  tags = {}

  artifacts = [{
    artifact_identifier    = null
    encryption_disabled    = null
    location               = null
    name                   = null
    namespace_type         = null
    override_artifact_name = null
    packaging              = null
    path                   = null
    type                   = null
  }]

  cache = [{
    location = null
    modes    = []
    type     = null
  }]

  environment = [{
    certificate  = null
    compute_type = null
    environment_variable = [{
      name  = null
      type  = null
      value = null
    }]
    image                       = null
    image_pull_credentials_type = null
    privileged_mode             = null
    registry_credential = [{
      credential          = null
      credential_provider = null
    }]
    type = null
  }]

  logs_config = [{
    cloudwatch_logs = [{
      group_name  = null
      status      = null
      stream_name = null
    }]
    s3_logs = [{
      encryption_disabled = null
      location            = null
      status              = null
    }]
  }]

  secondary_artifacts = [{
    artifact_identifier    = null
    encryption_disabled    = null
    location               = null
    name                   = null
    namespace_type         = null
    override_artifact_name = null
    packaging              = null
    path                   = null
    type                   = null
  }]

  secondary_sources = [{
    auth = [{
      resource = null
      type     = null
    }]
    buildspec       = null
    git_clone_depth = null
    git_submodules_config = [{
      fetch_submodules = null
    }]
    insecure_ssl        = null
    location            = null
    report_build_status = null
    source_identifier   = null
    type                = null
  }]


  vpc_config = [{
    security_group_ids = []
    subnets            = []
    vpc_id             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "badge_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "build_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryption_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "queued_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_role" {
  description = "(required)"
  type        = string
}

variable "source_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "artifacts" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      artifact_identifier    = string
      encryption_disabled    = bool
      location               = string
      name                   = string
      namespace_type         = string
      override_artifact_name = bool
      packaging              = string
      path                   = string
      type                   = string
    }
  ))
}

variable "cache" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      location = string
      modes    = list(string)
      type     = string
    }
  ))
  default = []
}

variable "environment" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      certificate  = string
      compute_type = string
      environment_variable = list(object(
        {
          name  = string
          type  = string
          value = string
        }
      ))
      image                       = string
      image_pull_credentials_type = string
      privileged_mode             = bool
      registry_credential = list(object(
        {
          credential          = string
          credential_provider = string
        }
      ))
      type = string
    }
  ))
}

variable "logs_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloudwatch_logs = list(object(
        {
          group_name  = string
          status      = string
          stream_name = string
        }
      ))
      s3_logs = list(object(
        {
          encryption_disabled = bool
          location            = string
          status              = string
        }
      ))
    }
  ))
  default = []
}

variable "secondary_artifacts" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      artifact_identifier    = string
      encryption_disabled    = bool
      location               = string
      name                   = string
      namespace_type         = string
      override_artifact_name = bool
      packaging              = string
      path                   = string
      type                   = string
    }
  ))
  default = []
}

variable "secondary_sources" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auth = list(object(
        {
          resource = string
          type     = string
        }
      ))
      buildspec       = string
      git_clone_depth = number
      git_submodules_config = list(object(
        {
          fetch_submodules = bool
        }
      ))
      insecure_ssl        = bool
      location            = string
      report_build_status = bool
      source_identifier   = string
      type                = string
    }
  ))
  default = []
}

variable "source" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      auth = list(object(
        {
          resource = string
          type     = string
        }
      ))
      buildspec       = string
      git_clone_depth = number
      git_submodules_config = list(object(
        {
          fetch_submodules = bool
        }
      ))
      insecure_ssl        = bool
      location            = string
      report_build_status = bool
      type                = string
    }
  ))
}

variable "vpc_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      security_group_ids = set(string)
      subnets            = set(string)
      vpc_id             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_codebuild_project" "this" {
  # badge_enabled - (optional) is a type of bool
  badge_enabled = var.badge_enabled
  # build_timeout - (optional) is a type of number
  build_timeout = var.build_timeout
  # description - (optional) is a type of string
  description = var.description
  # encryption_key - (optional) is a type of string
  encryption_key = var.encryption_key
  # name - (required) is a type of string
  name = var.name
  # queued_timeout - (optional) is a type of number
  queued_timeout = var.queued_timeout
  # service_role - (required) is a type of string
  service_role = var.service_role
  # source_version - (optional) is a type of string
  source_version = var.source_version
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "artifacts" {
    for_each = var.artifacts
    content {
      # artifact_identifier - (optional) is a type of string
      artifact_identifier = artifacts.value["artifact_identifier"]
      # encryption_disabled - (optional) is a type of bool
      encryption_disabled = artifacts.value["encryption_disabled"]
      # location - (optional) is a type of string
      location = artifacts.value["location"]
      # name - (optional) is a type of string
      name = artifacts.value["name"]
      # namespace_type - (optional) is a type of string
      namespace_type = artifacts.value["namespace_type"]
      # override_artifact_name - (optional) is a type of bool
      override_artifact_name = artifacts.value["override_artifact_name"]
      # packaging - (optional) is a type of string
      packaging = artifacts.value["packaging"]
      # path - (optional) is a type of string
      path = artifacts.value["path"]
      # type - (required) is a type of string
      type = artifacts.value["type"]
    }
  }

  dynamic "cache" {
    for_each = var.cache
    content {
      # location - (optional) is a type of string
      location = cache.value["location"]
      # modes - (optional) is a type of list of string
      modes = cache.value["modes"]
      # type - (optional) is a type of string
      type = cache.value["type"]
    }
  }

  dynamic "environment" {
    for_each = var.environment
    content {
      # certificate - (optional) is a type of string
      certificate = environment.value["certificate"]
      # compute_type - (required) is a type of string
      compute_type = environment.value["compute_type"]
      # image - (required) is a type of string
      image = environment.value["image"]
      # image_pull_credentials_type - (optional) is a type of string
      image_pull_credentials_type = environment.value["image_pull_credentials_type"]
      # privileged_mode - (optional) is a type of bool
      privileged_mode = environment.value["privileged_mode"]
      # type - (required) is a type of string
      type = environment.value["type"]

      dynamic "environment_variable" {
        for_each = environment.value.environment_variable
        content {
          # name - (required) is a type of string
          name = environment_variable.value["name"]
          # type - (optional) is a type of string
          type = environment_variable.value["type"]
          # value - (required) is a type of string
          value = environment_variable.value["value"]
        }
      }

      dynamic "registry_credential" {
        for_each = environment.value.registry_credential
        content {
          # credential - (required) is a type of string
          credential = registry_credential.value["credential"]
          # credential_provider - (required) is a type of string
          credential_provider = registry_credential.value["credential_provider"]
        }
      }

    }
  }

  dynamic "logs_config" {
    for_each = var.logs_config
    content {

      dynamic "cloudwatch_logs" {
        for_each = logs_config.value.cloudwatch_logs
        content {
          # group_name - (optional) is a type of string
          group_name = cloudwatch_logs.value["group_name"]
          # status - (optional) is a type of string
          status = cloudwatch_logs.value["status"]
          # stream_name - (optional) is a type of string
          stream_name = cloudwatch_logs.value["stream_name"]
        }
      }

      dynamic "s3_logs" {
        for_each = logs_config.value.s3_logs
        content {
          # encryption_disabled - (optional) is a type of bool
          encryption_disabled = s3_logs.value["encryption_disabled"]
          # location - (optional) is a type of string
          location = s3_logs.value["location"]
          # status - (optional) is a type of string
          status = s3_logs.value["status"]
        }
      }

    }
  }

  dynamic "secondary_artifacts" {
    for_each = var.secondary_artifacts
    content {
      # artifact_identifier - (required) is a type of string
      artifact_identifier = secondary_artifacts.value["artifact_identifier"]
      # encryption_disabled - (optional) is a type of bool
      encryption_disabled = secondary_artifacts.value["encryption_disabled"]
      # location - (optional) is a type of string
      location = secondary_artifacts.value["location"]
      # name - (optional) is a type of string
      name = secondary_artifacts.value["name"]
      # namespace_type - (optional) is a type of string
      namespace_type = secondary_artifacts.value["namespace_type"]
      # override_artifact_name - (optional) is a type of bool
      override_artifact_name = secondary_artifacts.value["override_artifact_name"]
      # packaging - (optional) is a type of string
      packaging = secondary_artifacts.value["packaging"]
      # path - (optional) is a type of string
      path = secondary_artifacts.value["path"]
      # type - (required) is a type of string
      type = secondary_artifacts.value["type"]
    }
  }

  dynamic "secondary_sources" {
    for_each = var.secondary_sources
    content {
      # buildspec - (optional) is a type of string
      buildspec = secondary_sources.value["buildspec"]
      # git_clone_depth - (optional) is a type of number
      git_clone_depth = secondary_sources.value["git_clone_depth"]
      # insecure_ssl - (optional) is a type of bool
      insecure_ssl = secondary_sources.value["insecure_ssl"]
      # location - (optional) is a type of string
      location = secondary_sources.value["location"]
      # report_build_status - (optional) is a type of bool
      report_build_status = secondary_sources.value["report_build_status"]
      # source_identifier - (required) is a type of string
      source_identifier = secondary_sources.value["source_identifier"]
      # type - (required) is a type of string
      type = secondary_sources.value["type"]

      dynamic "auth" {
        for_each = secondary_sources.value.auth
        content {
          # resource - (optional) is a type of string
          resource = auth.value["resource"]
          # type - (required) is a type of string
          type = auth.value["type"]
        }
      }

      dynamic "git_submodules_config" {
        for_each = secondary_sources.value.git_submodules_config
        content {
          # fetch_submodules - (required) is a type of bool
          fetch_submodules = git_submodules_config.value["fetch_submodules"]
        }
      }

    }
  }

  dynamic "source" {
    for_each = var.source
    content {
      # buildspec - (optional) is a type of string
      buildspec = source.value["buildspec"]
      # git_clone_depth - (optional) is a type of number
      git_clone_depth = source.value["git_clone_depth"]
      # insecure_ssl - (optional) is a type of bool
      insecure_ssl = source.value["insecure_ssl"]
      # location - (optional) is a type of string
      location = source.value["location"]
      # report_build_status - (optional) is a type of bool
      report_build_status = source.value["report_build_status"]
      # type - (required) is a type of string
      type = source.value["type"]

      dynamic "auth" {
        for_each = source.value.auth
        content {
          # resource - (optional) is a type of string
          resource = auth.value["resource"]
          # type - (required) is a type of string
          type = auth.value["type"]
        }
      }

      dynamic "git_submodules_config" {
        for_each = source.value.git_submodules_config
        content {
          # fetch_submodules - (required) is a type of bool
          fetch_submodules = git_submodules_config.value["fetch_submodules"]
        }
      }

    }
  }

  dynamic "vpc_config" {
    for_each = var.vpc_config
    content {
      # security_group_ids - (required) is a type of set of string
      security_group_ids = vpc_config.value["security_group_ids"]
      # subnets - (required) is a type of set of string
      subnets = vpc_config.value["subnets"]
      # vpc_id - (required) is a type of string
      vpc_id = vpc_config.value["vpc_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_codebuild_project.this.arn
}

output "badge_url" {
  description = "returns a string"
  value       = aws_codebuild_project.this.badge_url
}

output "description" {
  description = "returns a string"
  value       = aws_codebuild_project.this.description
}

output "encryption_key" {
  description = "returns a string"
  value       = aws_codebuild_project.this.encryption_key
}

output "id" {
  description = "returns a string"
  value       = aws_codebuild_project.this.id
}

output "this" {
  value = aws_codebuild_project.this
}
```

[top](#index)