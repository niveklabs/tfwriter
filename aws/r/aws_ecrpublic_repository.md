# aws_ecrpublic_repository

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
module "aws_ecrpublic_repository" {
  source = "./modules/aws/r/aws_ecrpublic_repository"

  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # repository_name - (required) is a type of string
  repository_name = null

  catalog_data = [{
    about_text        = null
    architectures     = []
    description       = null
    logo_image_blob   = null
    operating_systems = []
    usage_text        = null
  }]

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "repository_name" {
  description = "(required)"
  type        = string
}

variable "catalog_data" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      about_text        = string
      architectures     = set(string)
      description       = string
      logo_image_blob   = string
      operating_systems = set(string)
      usage_text        = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ecrpublic_repository" "this" {
  force_destroy   = var.force_destroy
  repository_name = var.repository_name

  dynamic "catalog_data" {
    for_each = var.catalog_data
    content {
      about_text        = catalog_data.value["about_text"]
      architectures     = catalog_data.value["architectures"]
      description       = catalog_data.value["description"]
      logo_image_blob   = catalog_data.value["logo_image_blob"]
      operating_systems = catalog_data.value["operating_systems"]
      usage_text        = catalog_data.value["usage_text"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ecrpublic_repository.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ecrpublic_repository.this.id
}

output "registry_id" {
  description = "returns a string"
  value       = aws_ecrpublic_repository.this.registry_id
}

output "repository_uri" {
  description = "returns a string"
  value       = aws_ecrpublic_repository.this.repository_uri
}

output "this" {
  value = aws_ecrpublic_repository.this
}
```

[top](#index)