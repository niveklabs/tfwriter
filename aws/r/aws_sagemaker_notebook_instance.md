# aws_sagemaker_notebook_instance

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
module "aws_sagemaker_notebook_instance" {
  source = "./modules/aws/r/aws_sagemaker_notebook_instance"

  # additional_code_repositories - (optional) is a type of set of string
  additional_code_repositories = []
  # default_code_repository - (optional) is a type of string
  default_code_repository = null
  # direct_internet_access - (optional) is a type of string
  direct_internet_access = null
  # instance_type - (required) is a type of string
  instance_type = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # lifecycle_config_name - (optional) is a type of string
  lifecycle_config_name = null
  # name - (required) is a type of string
  name = null
  # role_arn - (required) is a type of string
  role_arn = null
  # root_access - (optional) is a type of string
  root_access = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # volume_size - (optional) is a type of number
  volume_size = null
}
```

[top](#index)

### Variables

```hcl
variable "additional_code_repositories" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "default_code_repository" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "direct_internet_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lifecycle_config_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "root_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "volume_size" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_sagemaker_notebook_instance" "this" {
  additional_code_repositories = var.additional_code_repositories
  default_code_repository      = var.default_code_repository
  direct_internet_access       = var.direct_internet_access
  instance_type                = var.instance_type
  kms_key_id                   = var.kms_key_id
  lifecycle_config_name        = var.lifecycle_config_name
  name                         = var.name
  role_arn                     = var.role_arn
  root_access                  = var.root_access
  security_groups              = var.security_groups
  subnet_id                    = var.subnet_id
  tags                         = var.tags
  volume_size                  = var.volume_size
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_notebook_instance.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_notebook_instance.this.id
}

output "network_interface_id" {
  description = "returns a string"
  value       = aws_sagemaker_notebook_instance.this.network_interface_id
}

output "security_groups" {
  description = "returns a set of string"
  value       = aws_sagemaker_notebook_instance.this.security_groups
}

output "url" {
  description = "returns a string"
  value       = aws_sagemaker_notebook_instance.this.url
}

output "this" {
  value = aws_sagemaker_notebook_instance.this
}
```

[top](#index)