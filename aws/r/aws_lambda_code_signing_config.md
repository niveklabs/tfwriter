# aws_lambda_code_signing_config

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lambda_code_signing_config" {
  source = "./modules/aws/r/aws_lambda_code_signing_config"

  # description - (optional) is a type of string
  description = null

  allowed_publishers = [{
    signing_profile_version_arns = []
  }]

  policies = [{
    untrusted_artifact_on_deployment = null
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

variable "allowed_publishers" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      signing_profile_version_arns = set(string)
    }
  ))
}

variable "policies" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      untrusted_artifact_on_deployment = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_lambda_code_signing_config" "this" {
  description = var.description

  dynamic "allowed_publishers" {
    for_each = var.allowed_publishers
    content {
      signing_profile_version_arns = allowed_publishers.value["signing_profile_version_arns"]
    }
  }

  dynamic "policies" {
    for_each = var.policies
    content {
      untrusted_artifact_on_deployment = policies.value["untrusted_artifact_on_deployment"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lambda_code_signing_config.this.arn
}

output "config_id" {
  description = "returns a string"
  value       = aws_lambda_code_signing_config.this.config_id
}

output "id" {
  description = "returns a string"
  value       = aws_lambda_code_signing_config.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = aws_lambda_code_signing_config.this.last_modified
}

output "this" {
  value = aws_lambda_code_signing_config.this
}
```

[top](#index)