# aws_iam_openid_connect_provider

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
module "aws_iam_openid_connect_provider" {
  source = "./modules/aws/r/aws_iam_openid_connect_provider"

  # client_id_list - (required) is a type of list of string
  client_id_list = []
  # tags - (optional) is a type of map of string
  tags = {}
  # thumbprint_list - (required) is a type of list of string
  thumbprint_list = []
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "client_id_list" {
  description = "(required)"
  type        = list(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "thumbprint_list" {
  description = "(required)"
  type        = list(string)
}

variable "url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_openid_connect_provider" "this" {
  # client_id_list - (required) is a type of list of string
  client_id_list = var.client_id_list
  # tags - (optional) is a type of map of string
  tags = var.tags
  # thumbprint_list - (required) is a type of list of string
  thumbprint_list = var.thumbprint_list
  # url - (required) is a type of string
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iam_openid_connect_provider.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iam_openid_connect_provider.this.id
}

output "this" {
  value = aws_iam_openid_connect_provider.this
}
```

[top](#index)