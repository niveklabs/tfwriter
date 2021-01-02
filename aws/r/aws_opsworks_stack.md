# aws_opsworks_stack

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_opsworks_stack" {
  source = "./modules/aws/r/aws_opsworks_stack"

  # agent_version - (optional) is a type of string
  agent_version = null
  # berkshelf_version - (optional) is a type of string
  berkshelf_version = null
  # color - (optional) is a type of string
  color = null
  # configuration_manager_name - (optional) is a type of string
  configuration_manager_name = null
  # configuration_manager_version - (optional) is a type of string
  configuration_manager_version = null
  # custom_json - (optional) is a type of string
  custom_json = null
  # default_availability_zone - (optional) is a type of string
  default_availability_zone = null
  # default_instance_profile_arn - (required) is a type of string
  default_instance_profile_arn = null
  # default_os - (optional) is a type of string
  default_os = null
  # default_root_device_type - (optional) is a type of string
  default_root_device_type = null
  # default_ssh_key_name - (optional) is a type of string
  default_ssh_key_name = null
  # default_subnet_id - (optional) is a type of string
  default_subnet_id = null
  # hostname_theme - (optional) is a type of string
  hostname_theme = null
  # manage_berkshelf - (optional) is a type of bool
  manage_berkshelf = null
  # name - (required) is a type of string
  name = null
  # region - (required) is a type of string
  region = null
  # service_role_arn - (required) is a type of string
  service_role_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
  # use_custom_cookbooks - (optional) is a type of bool
  use_custom_cookbooks = null
  # use_opsworks_security_groups - (optional) is a type of bool
  use_opsworks_security_groups = null
  # vpc_id - (optional) is a type of string
  vpc_id = null

  custom_cookbooks_source = [{
    password = null
    revision = null
    ssh_key  = null
    type     = null
    url      = null
    username = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "agent_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "berkshelf_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configuration_manager_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configuration_manager_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_instance_profile_arn" {
  description = "(required)"
  type        = string
}

variable "default_os" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_root_device_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_ssh_key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname_theme" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "manage_berkshelf" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "service_role_arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "use_custom_cookbooks" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "use_opsworks_security_groups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_cookbooks_source" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      password = string
      revision = string
      ssh_key  = string
      type     = string
      url      = string
      username = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_opsworks_stack" "this" {
  agent_version                 = var.agent_version
  berkshelf_version             = var.berkshelf_version
  color                         = var.color
  configuration_manager_name    = var.configuration_manager_name
  configuration_manager_version = var.configuration_manager_version
  custom_json                   = var.custom_json
  default_availability_zone     = var.default_availability_zone
  default_instance_profile_arn  = var.default_instance_profile_arn
  default_os                    = var.default_os
  default_root_device_type      = var.default_root_device_type
  default_ssh_key_name          = var.default_ssh_key_name
  default_subnet_id             = var.default_subnet_id
  hostname_theme                = var.hostname_theme
  manage_berkshelf              = var.manage_berkshelf
  name                          = var.name
  region                        = var.region
  service_role_arn              = var.service_role_arn
  tags                          = var.tags
  use_custom_cookbooks          = var.use_custom_cookbooks
  use_opsworks_security_groups  = var.use_opsworks_security_groups
  vpc_id                        = var.vpc_id

  dynamic "custom_cookbooks_source" {
    for_each = var.custom_cookbooks_source
    content {
      password = custom_cookbooks_source.value["password"]
      revision = custom_cookbooks_source.value["revision"]
      ssh_key  = custom_cookbooks_source.value["ssh_key"]
      type     = custom_cookbooks_source.value["type"]
      url      = custom_cookbooks_source.value["url"]
      username = custom_cookbooks_source.value["username"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "agent_version" {
  description = "returns a string"
  value       = aws_opsworks_stack.this.agent_version
}

output "arn" {
  description = "returns a string"
  value       = aws_opsworks_stack.this.arn
}

output "default_availability_zone" {
  description = "returns a string"
  value       = aws_opsworks_stack.this.default_availability_zone
}

output "default_subnet_id" {
  description = "returns a string"
  value       = aws_opsworks_stack.this.default_subnet_id
}

output "id" {
  description = "returns a string"
  value       = aws_opsworks_stack.this.id
}

output "stack_endpoint" {
  description = "returns a string"
  value       = aws_opsworks_stack.this.stack_endpoint
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_opsworks_stack.this.vpc_id
}

output "this" {
  value = aws_opsworks_stack.this
}
```

[top](#index)