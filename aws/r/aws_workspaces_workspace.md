# aws_workspaces_workspace

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
module "aws_workspaces_workspace" {
  source = "./modules/aws/r/aws_workspaces_workspace"

  # bundle_id - (required) is a type of string
  bundle_id = null
  # directory_id - (required) is a type of string
  directory_id = null
  # root_volume_encryption_enabled - (optional) is a type of bool
  root_volume_encryption_enabled = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_name - (required) is a type of string
  user_name = null
  # user_volume_encryption_enabled - (optional) is a type of bool
  user_volume_encryption_enabled = null
  # volume_encryption_key - (optional) is a type of string
  volume_encryption_key = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  workspace_properties = [{
    compute_type_name                         = null
    root_volume_size_gib                      = null
    running_mode                              = null
    running_mode_auto_stop_timeout_in_minutes = null
    user_volume_size_gib                      = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "bundle_id" {
  description = "(required)"
  type        = string
}

variable "directory_id" {
  description = "(required)"
  type        = string
}

variable "root_volume_encryption_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_name" {
  description = "(required)"
  type        = string
}

variable "user_volume_encryption_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "volume_encryption_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}

variable "workspace_properties" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      compute_type_name                         = string
      root_volume_size_gib                      = number
      running_mode                              = string
      running_mode_auto_stop_timeout_in_minutes = number
      user_volume_size_gib                      = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_workspaces_workspace" "this" {
  bundle_id                      = var.bundle_id
  directory_id                   = var.directory_id
  root_volume_encryption_enabled = var.root_volume_encryption_enabled
  tags                           = var.tags
  user_name                      = var.user_name
  user_volume_encryption_enabled = var.user_volume_encryption_enabled
  volume_encryption_key          = var.volume_encryption_key

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "workspace_properties" {
    for_each = var.workspace_properties
    content {
      compute_type_name                         = workspace_properties.value["compute_type_name"]
      root_volume_size_gib                      = workspace_properties.value["root_volume_size_gib"]
      running_mode                              = workspace_properties.value["running_mode"]
      running_mode_auto_stop_timeout_in_minutes = workspace_properties.value["running_mode_auto_stop_timeout_in_minutes"]
      user_volume_size_gib                      = workspace_properties.value["user_volume_size_gib"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "computer_name" {
  description = "returns a string"
  value       = aws_workspaces_workspace.this.computer_name
}

output "id" {
  description = "returns a string"
  value       = aws_workspaces_workspace.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = aws_workspaces_workspace.this.ip_address
}

output "state" {
  description = "returns a string"
  value       = aws_workspaces_workspace.this.state
}

output "this" {
  value = aws_workspaces_workspace.this
}
```

[top](#index)