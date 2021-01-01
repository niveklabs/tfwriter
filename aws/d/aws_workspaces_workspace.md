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
  source = "./modules/aws/d/aws_workspaces_workspace"

  # directory_id - (optional) is a type of string
  directory_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_name - (optional) is a type of string
  user_name = null
  # workspace_id - (optional) is a type of string
  workspace_id = null
}
```
[top](#index)
### Variables
```hcl
variable "directory_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "workspace_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```
[top](#index)

### Datasource
```hcl
data "aws_workspaces_workspace" "this" {
  directory_id = var.directory_id
  tags         = var.tags
  user_name    = var.user_name
  workspace_id = var.workspace_id
}
```
[top](#index)
### Outputs
```hcl
output "bundle_id" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.bundle_id
}

output "computer_name" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.computer_name
}

output "directory_id" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.directory_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.ip_address
}

output "root_volume_encryption_enabled" {
  description = "returns a bool"
  value       = data.aws_workspaces_workspace.this.root_volume_encryption_enabled
}

output "state" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_workspaces_workspace.this.tags
}

output "user_name" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.user_name
}

output "user_volume_encryption_enabled" {
  description = "returns a bool"
  value       = data.aws_workspaces_workspace.this.user_volume_encryption_enabled
}

output "volume_encryption_key" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.volume_encryption_key
}

output "workspace_id" {
  description = "returns a string"
  value       = data.aws_workspaces_workspace.this.workspace_id
}

output "workspace_properties" {
  description = "returns a list of object"
  value       = data.aws_workspaces_workspace.this.workspace_properties
}

output "this" {
  value = aws_workspaces_workspace.this
}
```
[top](#index)
