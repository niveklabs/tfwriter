# aws_sagemaker_model

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
module "aws_sagemaker_model" {
  source = "./modules/aws/r/aws_sagemaker_model"

  # enable_network_isolation - (optional) is a type of bool
  enable_network_isolation = null
  # execution_role_arn - (required) is a type of string
  execution_role_arn = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  container = [{
    container_hostname = null
    environment        = {}
    image              = null
    image_config = [{
      repository_access_mode = null
    }]
    mode           = null
    model_data_url = null
  }]

  primary_container = [{
    container_hostname = null
    environment        = {}
    image              = null
    image_config = [{
      repository_access_mode = null
    }]
    mode           = null
    model_data_url = null
  }]

  vpc_config = [{
    security_group_ids = []
    subnets            = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enable_network_isolation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "execution_role_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "container" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      container_hostname = string
      environment        = map(string)
      image              = string
      image_config = list(object(
        {
          repository_access_mode = string
        }
      ))
      mode           = string
      model_data_url = string
    }
  ))
  default = []
}

variable "primary_container" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      container_hostname = string
      environment        = map(string)
      image              = string
      image_config = list(object(
        {
          repository_access_mode = string
        }
      ))
      mode           = string
      model_data_url = string
    }
  ))
  default = []
}

variable "vpc_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      security_group_ids = set(string)
      subnets            = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_sagemaker_model" "this" {
  enable_network_isolation = var.enable_network_isolation
  execution_role_arn       = var.execution_role_arn
  name                     = var.name
  tags                     = var.tags

  dynamic "container" {
    for_each = var.container
    content {
      container_hostname = container.value["container_hostname"]
      environment        = container.value["environment"]
      image              = container.value["image"]
      mode               = container.value["mode"]
      model_data_url     = container.value["model_data_url"]

      dynamic "image_config" {
        for_each = container.value.image_config
        content {
          repository_access_mode = image_config.value["repository_access_mode"]
        }
      }

    }
  }

  dynamic "primary_container" {
    for_each = var.primary_container
    content {
      container_hostname = primary_container.value["container_hostname"]
      environment        = primary_container.value["environment"]
      image              = primary_container.value["image"]
      mode               = primary_container.value["mode"]
      model_data_url     = primary_container.value["model_data_url"]

      dynamic "image_config" {
        for_each = primary_container.value.image_config
        content {
          repository_access_mode = image_config.value["repository_access_mode"]
        }
      }

    }
  }

  dynamic "vpc_config" {
    for_each = var.vpc_config
    content {
      security_group_ids = vpc_config.value["security_group_ids"]
      subnets            = vpc_config.value["subnets"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_model.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_model.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_sagemaker_model.this.name
}

output "this" {
  value = aws_sagemaker_model.this
}
```

[top](#index)