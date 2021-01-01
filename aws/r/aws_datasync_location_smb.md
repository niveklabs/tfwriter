# aws_datasync_location_smb
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
module "aws_datasync_location_smb" {
  source = "./modules/aws/r/aws_datasync_location_smb"

  # agent_arns - (required) is a type of set of string
  agent_arns = []
  # domain - (optional) is a type of string
  domain = null
  # password - (required) is a type of string
  password = null
  # server_hostname - (required) is a type of string
  server_hostname = null
  # subdirectory - (required) is a type of string
  subdirectory = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user - (required) is a type of string
  user = null

  mount_options = [{
    version = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "agent_arns" {
  description = "(required)"
  type        = set(string)
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "server_hostname" {
  description = "(required)"
  type        = string
}

variable "subdirectory" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user" {
  description = "(required)"
  type        = string
}

variable "mount_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      version = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_datasync_location_smb" "this" {
  agent_arns      = var.agent_arns
  domain          = var.domain
  password        = var.password
  server_hostname = var.server_hostname
  subdirectory    = var.subdirectory
  tags            = var.tags
  user            = var.user

  dynamic "mount_options" {
    for_each = var.mount_options
    content {
      version = mount_options.value["version"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_datasync_location_smb.this.arn
}

output "domain" {
  description = "returns a string"
  value       = aws_datasync_location_smb.this.domain
}

output "id" {
  description = "returns a string"
  value       = aws_datasync_location_smb.this.id
}

output "uri" {
  description = "returns a string"
  value       = aws_datasync_location_smb.this.uri
}

output "this" {
  value = aws_datasync_location_smb.this
}
```
[top](#index)
