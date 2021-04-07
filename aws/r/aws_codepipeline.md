# aws_codepipeline

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
module "aws_codepipeline" {
  source = "./modules/aws/r/aws_codepipeline"

  # name - (required) is a type of string
  name = null
  # role_arn - (required) is a type of string
  role_arn = null
  # tags - (optional) is a type of map of string
  tags = {}

  artifact_store = [{
    encryption_key = [{
      id   = null
      type = null
    }]
    location = null
    region   = null
    type     = null
  }]

  stage = [{
    action = [{
      category         = null
      configuration    = {}
      input_artifacts  = []
      name             = null
      namespace        = null
      output_artifacts = []
      owner            = null
      provider         = null
      region           = null
      role_arn         = null
      run_order        = null
      version          = null
    }]
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "artifact_store" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      encryption_key = list(object(
        {
          id   = string
          type = string
        }
      ))
      location = string
      region   = string
      type     = string
    }
  ))
}

variable "stage" {
  description = "nested block: NestingList, min items: 2, max items: 0"
  type = set(object(
    {
      action = list(object(
        {
          category         = string
          configuration    = map(string)
          input_artifacts  = list(string)
          name             = string
          namespace        = string
          output_artifacts = list(string)
          owner            = string
          provider         = string
          region           = string
          role_arn         = string
          run_order        = number
          version          = string
        }
      ))
      name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_codepipeline" "this" {
  # name - (required) is a type of string
  name = var.name
  # role_arn - (required) is a type of string
  role_arn = var.role_arn
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "artifact_store" {
    for_each = var.artifact_store
    content {
      # location - (required) is a type of string
      location = artifact_store.value["location"]
      # region - (optional) is a type of string
      region = artifact_store.value["region"]
      # type - (required) is a type of string
      type = artifact_store.value["type"]

      dynamic "encryption_key" {
        for_each = artifact_store.value.encryption_key
        content {
          # id - (required) is a type of string
          id = encryption_key.value["id"]
          # type - (required) is a type of string
          type = encryption_key.value["type"]
        }
      }

    }
  }

  dynamic "stage" {
    for_each = var.stage
    content {
      # name - (required) is a type of string
      name = stage.value["name"]

      dynamic "action" {
        for_each = stage.value.action
        content {
          # category - (required) is a type of string
          category = action.value["category"]
          # configuration - (optional) is a type of map of string
          configuration = action.value["configuration"]
          # input_artifacts - (optional) is a type of list of string
          input_artifacts = action.value["input_artifacts"]
          # name - (required) is a type of string
          name = action.value["name"]
          # namespace - (optional) is a type of string
          namespace = action.value["namespace"]
          # output_artifacts - (optional) is a type of list of string
          output_artifacts = action.value["output_artifacts"]
          # owner - (required) is a type of string
          owner = action.value["owner"]
          # provider - (required) is a type of string
          provider = action.value["provider"]
          # region - (optional) is a type of string
          region = action.value["region"]
          # role_arn - (optional) is a type of string
          role_arn = action.value["role_arn"]
          # run_order - (optional) is a type of number
          run_order = action.value["run_order"]
          # version - (required) is a type of string
          version = action.value["version"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_codepipeline.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_codepipeline.this.id
}

output "this" {
  value = aws_codepipeline.this
}
```

[top](#index)