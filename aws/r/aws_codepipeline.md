# aws_codepipeline

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
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

```hcl
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
  description = "nested mode: NestingSet, min items: 1, max items: 0"
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
  description = "nested mode: NestingList, min items: 2, max items: 0"
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

```hcl
resource "aws_codepipeline" "this" {
  name     = var.name
  role_arn = var.role_arn
  tags     = var.tags

  dynamic "artifact_store" {
    for_each = var.artifact_store
    content {
      location = artifact_store.value["location"]
      region   = artifact_store.value["region"]
      type     = artifact_store.value["type"]

      dynamic "encryption_key" {
        for_each = artifact_store.value.encryption_key
        content {
          id   = encryption_key.value["id"]
          type = encryption_key.value["type"]
        }
      }

    }
  }

  dynamic "stage" {
    for_each = var.stage
    content {
      name = stage.value["name"]

      dynamic "action" {
        for_each = stage.value.action
        content {
          category         = action.value["category"]
          configuration    = action.value["configuration"]
          input_artifacts  = action.value["input_artifacts"]
          name             = action.value["name"]
          namespace        = action.value["namespace"]
          output_artifacts = action.value["output_artifacts"]
          owner            = action.value["owner"]
          provider         = action.value["provider"]
          region           = action.value["region"]
          role_arn         = action.value["role_arn"]
          run_order        = action.value["run_order"]
          version          = action.value["version"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
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