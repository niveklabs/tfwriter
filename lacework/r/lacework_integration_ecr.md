# lacework_integration_ecr

[back](../lacework.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    lacework = ">= 0.3.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_integration_ecr" {
  source = "./modules/lacework/r/lacework_integration_ecr"

  # enabled - (optional) is a type of bool
  enabled = null
  # limit_by_label - (optional) is a type of string
  limit_by_label = null
  # limit_by_repos - (optional) is a type of string
  limit_by_repos = null
  # limit_by_tag - (optional) is a type of string
  limit_by_tag = null
  # limit_num_imgs - (optional) is a type of number
  limit_num_imgs = null
  # name - (required) is a type of string
  name = null
  # registry_domain - (required) is a type of string
  registry_domain = null

  credentials = [{
    access_key_id     = null
    external_id       = null
    role_arn          = null
    secret_access_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - The state of the external integration"
  type        = bool
  default     = null
}

variable "limit_by_label" {
  description = "(optional) - An image label to limit the assessment of images with matching label"
  type        = string
  default     = null
}

variable "limit_by_repos" {
  description = "(optional) - A comma-separated list of repositories to assess"
  type        = string
  default     = null
}

variable "limit_by_tag" {
  description = "(optional) - An image tag to limit the assessment of images with matching tag"
  type        = string
  default     = null
}

variable "limit_num_imgs" {
  description = "(optional) - The maximum number of newest container images to assess per repository"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The ECR integration name"
  type        = string
}

variable "registry_domain" {
  description = "(required) - The Amazon Container Registry (ECR) domain"
  type        = string
}

variable "credentials" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      access_key_id     = string
      external_id       = string
      role_arn          = string
      secret_access_key = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "lacework_integration_ecr" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # limit_by_label - (optional) is a type of string
  limit_by_label = var.limit_by_label
  # limit_by_repos - (optional) is a type of string
  limit_by_repos = var.limit_by_repos
  # limit_by_tag - (optional) is a type of string
  limit_by_tag = var.limit_by_tag
  # limit_num_imgs - (optional) is a type of number
  limit_num_imgs = var.limit_num_imgs
  # name - (required) is a type of string
  name = var.name
  # registry_domain - (required) is a type of string
  registry_domain = var.registry_domain

  dynamic "credentials" {
    for_each = var.credentials
    content {
      # access_key_id - (optional) is a type of string
      access_key_id = credentials.value["access_key_id"]
      # external_id - (optional) is a type of string
      external_id = credentials.value["external_id"]
      # role_arn - (optional) is a type of string
      role_arn = credentials.value["role_arn"]
      # secret_access_key - (optional) is a type of string
      secret_access_key = credentials.value["secret_access_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "aws_auth_type" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.aws_auth_type
}

output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_integration_ecr.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.type_name
}

output "this" {
  value = lacework_integration_ecr.this
}
```

[top](#index)