# aws_sagemaker_code_repository

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
module "aws_sagemaker_code_repository" {
  source = "./modules/aws/r/aws_sagemaker_code_repository"

  # code_repository_name - (required) is a type of string
  code_repository_name = null

  git_config = [{
    branch         = null
    repository_url = null
    secret_arn     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "code_repository_name" {
  description = "(required)"
  type        = string
}

variable "git_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      branch         = string
      repository_url = string
      secret_arn     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_sagemaker_code_repository" "this" {
  code_repository_name = var.code_repository_name

  dynamic "git_config" {
    for_each = var.git_config
    content {
      branch         = git_config.value["branch"]
      repository_url = git_config.value["repository_url"]
      secret_arn     = git_config.value["secret_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_code_repository.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_code_repository.this.id
}

output "this" {
  value = aws_sagemaker_code_repository.this
}
```

[top](#index)