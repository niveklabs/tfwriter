# aws_workspaces_directory

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
module "aws_workspaces_directory" {
  source = "./modules/aws/r/aws_workspaces_directory"

  # directory_id - (required) is a type of string
  directory_id = null
  # ip_group_ids - (optional) is a type of set of string
  ip_group_ids = []
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}

  self_service_permissions = [{
    change_compute_type  = null
    increase_volume_size = null
    rebuild_workspace    = null
    restart_workspace    = null
    switch_running_mode  = null
  }]

  workspace_access_properties = [{
    device_type_android    = null
    device_type_chromeos   = null
    device_type_ios        = null
    device_type_osx        = null
    device_type_web        = null
    device_type_windows    = null
    device_type_zeroclient = null
  }]

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

variable "ip_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnet_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "self_service_permissions" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      change_compute_type  = bool
      increase_volume_size = bool
      rebuild_workspace    = bool
      restart_workspace    = bool
      switch_running_mode  = bool
    }
  ))
  default = []
}

variable "workspace_access_properties" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      device_type_android    = string
      device_type_chromeos   = string
      device_type_ios        = string
      device_type_osx        = string
      device_type_web        = string
      device_type_windows    = string
      device_type_zeroclient = string
    }
  ))
  default = []
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

### Resource

```terraform
resource "aws_workspaces_directory" "this" {
  # directory_id - (required) is a type of string
  directory_id = var.directory_id
  # ip_group_ids - (optional) is a type of set of string
  ip_group_ids = var.ip_group_ids
  # subnet_ids - (optional) is a type of set of string
  subnet_ids = var.subnet_ids
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "self_service_permissions" {
    for_each = var.self_service_permissions
    content {
      # change_compute_type - (optional) is a type of bool
      change_compute_type = self_service_permissions.value["change_compute_type"]
      # increase_volume_size - (optional) is a type of bool
      increase_volume_size = self_service_permissions.value["increase_volume_size"]
      # rebuild_workspace - (optional) is a type of bool
      rebuild_workspace = self_service_permissions.value["rebuild_workspace"]
      # restart_workspace - (optional) is a type of bool
      restart_workspace = self_service_permissions.value["restart_workspace"]
      # switch_running_mode - (optional) is a type of bool
      switch_running_mode = self_service_permissions.value["switch_running_mode"]
    }
  }

  dynamic "workspace_access_properties" {
    for_each = var.workspace_access_properties
    content {
      # device_type_android - (optional) is a type of string
      device_type_android = workspace_access_properties.value["device_type_android"]
      # device_type_chromeos - (optional) is a type of string
      device_type_chromeos = workspace_access_properties.value["device_type_chromeos"]
      # device_type_ios - (optional) is a type of string
      device_type_ios = workspace_access_properties.value["device_type_ios"]
      # device_type_osx - (optional) is a type of string
      device_type_osx = workspace_access_properties.value["device_type_osx"]
      # device_type_web - (optional) is a type of string
      device_type_web = workspace_access_properties.value["device_type_web"]
      # device_type_windows - (optional) is a type of string
      device_type_windows = workspace_access_properties.value["device_type_windows"]
      # device_type_zeroclient - (optional) is a type of string
      device_type_zeroclient = workspace_access_properties.value["device_type_zeroclient"]
    }
  }

  dynamic "workspace_creation_properties" {
    for_each = var.workspace_creation_properties
    content {
      # custom_security_group_id - (optional) is a type of string
      custom_security_group_id = workspace_creation_properties.value["custom_security_group_id"]
      # default_ou - (optional) is a type of string
      default_ou = workspace_creation_properties.value["default_ou"]
      # enable_internet_access - (optional) is a type of bool
      enable_internet_access = workspace_creation_properties.value["enable_internet_access"]
      # enable_maintenance_mode - (optional) is a type of bool
      enable_maintenance_mode = workspace_creation_properties.value["enable_maintenance_mode"]
      # user_enabled_as_local_administrator - (optional) is a type of bool
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
  value       = aws_workspaces_directory.this.alias
}

output "customer_user_name" {
  description = "returns a string"
  value       = aws_workspaces_directory.this.customer_user_name
}

output "directory_name" {
  description = "returns a string"
  value       = aws_workspaces_directory.this.directory_name
}

output "directory_type" {
  description = "returns a string"
  value       = aws_workspaces_directory.this.directory_type
}

output "dns_ip_addresses" {
  description = "returns a set of string"
  value       = aws_workspaces_directory.this.dns_ip_addresses
}

output "iam_role_id" {
  description = "returns a string"
  value       = aws_workspaces_directory.this.iam_role_id
}

output "id" {
  description = "returns a string"
  value       = aws_workspaces_directory.this.id
}

output "ip_group_ids" {
  description = "returns a set of string"
  value       = aws_workspaces_directory.this.ip_group_ids
}

output "registration_code" {
  description = "returns a string"
  value       = aws_workspaces_directory.this.registration_code
}

output "subnet_ids" {
  description = "returns a set of string"
  value       = aws_workspaces_directory.this.subnet_ids
}

output "workspace_security_group_id" {
  description = "returns a string"
  value       = aws_workspaces_directory.this.workspace_security_group_id
}

output "this" {
  value = aws_workspaces_directory.this
}
```

[top](#index)