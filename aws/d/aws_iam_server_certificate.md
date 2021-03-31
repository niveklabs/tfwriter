# aws_iam_server_certificate

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_iam_server_certificate" {
  source = "./modules/aws/d/aws_iam_server_certificate"

  # latest - (optional) is a type of bool
  latest = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # path_prefix - (optional) is a type of string
  path_prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "latest" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_iam_server_certificate" "this" {
  latest      = var.latest
  name        = var.name
  name_prefix = var.name_prefix
  path_prefix = var.path_prefix
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_iam_server_certificate.this.arn
}

output "certificate_body" {
  description = "returns a string"
  value       = data.aws_iam_server_certificate.this.certificate_body
}

output "certificate_chain" {
  description = "returns a string"
  value       = data.aws_iam_server_certificate.this.certificate_chain
}

output "expiration_date" {
  description = "returns a string"
  value       = data.aws_iam_server_certificate.this.expiration_date
}

output "id" {
  description = "returns a string"
  value       = data.aws_iam_server_certificate.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_iam_server_certificate.this.name
}

output "path" {
  description = "returns a string"
  value       = data.aws_iam_server_certificate.this.path
}

output "upload_date" {
  description = "returns a string"
  value       = data.aws_iam_server_certificate.this.upload_date
}

output "this" {
  value = aws_iam_server_certificate.this
}
```

[top](#index)