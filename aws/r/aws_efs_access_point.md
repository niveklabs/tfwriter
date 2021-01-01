# aws_efs_access_point

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_efs_access_point" {
  source = "./modules/aws/r/aws_efs_access_point"

  # file_system_id - (required) is a type of string
  file_system_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  posix_user = [{
    gid            = null
    secondary_gids = []
    uid            = null
  }]

  root_directory = [{
    creation_info = [{
      owner_gid   = null
      owner_uid   = null
      permissions = null
    }]
    path = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "file_system_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "posix_user" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      gid            = number
      secondary_gids = set(number)
      uid            = number
    }
  ))
  default = []
}

variable "root_directory" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      creation_info = list(object(
        {
          owner_gid   = number
          owner_uid   = number
          permissions = string
        }
      ))
      path = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_efs_access_point" "this" {
  file_system_id = var.file_system_id
  tags           = var.tags

  dynamic "posix_user" {
    for_each = var.posix_user
    content {
      gid            = posix_user.value["gid"]
      secondary_gids = posix_user.value["secondary_gids"]
      uid            = posix_user.value["uid"]
    }
  }

  dynamic "root_directory" {
    for_each = var.root_directory
    content {
      path = root_directory.value["path"]

      dynamic "creation_info" {
        for_each = root_directory.value.creation_info
        content {
          owner_gid   = creation_info.value["owner_gid"]
          owner_uid   = creation_info.value["owner_uid"]
          permissions = creation_info.value["permissions"]
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
  value       = aws_efs_access_point.this.arn
}

output "file_system_arn" {
  description = "returns a string"
  value       = aws_efs_access_point.this.file_system_arn
}

output "id" {
  description = "returns a string"
  value       = aws_efs_access_point.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_efs_access_point.this.owner_id
}

output "this" {
  value = aws_efs_access_point.this
}
```

[top](#index)