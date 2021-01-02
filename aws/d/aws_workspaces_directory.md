# aws_workspaces_directory

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_workspaces_directory" {
  source = "./modules/aws/d/aws_workspaces_directory"

  # directory_id - (required) is a type of string
  directory_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  workspace_creation_properties = [{
    custom_security_group_id            = null
    default_ou                          = null
    enable_internet_access              = null
    enable_maintenance_mode             = null
    user_enabled_as_local_administrator = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "directory_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "workspace_creation_properties" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      custom_security_group_id            = string
      default_ou                          = string
      enable_internet_access              = bool
      enable_maintenance_mode             = bool
      user_enabled_as_local_administrator = bool
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_workspaces_directory" "this" {
  directory_id = var.directory_id
  tags         = var.tags

  dynamic "workspace_creation_properties" {
    for_each = var.workspace_creation_properties
    content {
      custom_security_group_id            = workspace_creation_properties.value["custom_security_group_id"]
      default_ou                          = workspace_creation_properties.value["default_ou"]
      enable_internet_access              = workspace_creation_properties.value["enable_internet_access"]
      enable_maintenance_mode             = workspace_creation_properties.value["enable_maintenance_mode"]
      user_enabled_as_local_administrator = workspace_creation_properties.value["user_enabled_as_local_administrator"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "alias" {
  description = "returns a string"
  value       = data.aws_workspaces_directory.this.alias
}

output "customer_user_name" {
  description = "returns a string"
  value       = data.aws_workspaces_directory.this.customer_user_name
}

output "directory_name" {
  description = "returns a string"
  value       = data.aws_workspaces_directory.this.directory_name
}

output "directory_type" {
  description = "returns a string"
  value       = data.aws_workspaces_directory.this.directory_type
}

output "dns_ip_addresses" {
  description = "returns a set of string"
  value       = data.aws_workspaces_directory.this.dns_ip_addresses
}

output "iam_role_id" {
  description = "returns a string"
  value       = data.aws_workspaces_directory.this.iam_role_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_workspaces_directory.this.id
}

output "ip_group_ids" {
  description = "returns a set of string"
  value       = data.aws_workspaces_directory.this.ip_group_ids
}

output "registration_code" {
  description = "returns a string"
  value       = data.aws_workspaces_directory.this.registration_code
}

output "self_service_permissions" {
  description = "returns a list of object"
  value       = data.aws_workspaces_directory.this.self_service_permissions
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = data.aws_workspaces_directory.this.subnet_ids
}

output "workspace_security_group_id" {
  description = "returns a string"
  value       = data.aws_workspaces_directory.this.workspace_security_group_id
}

output "this" {
  value = aws_workspaces_directory.this
}
```

[top](#index)