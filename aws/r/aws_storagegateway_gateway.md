# aws_storagegateway_gateway
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
module "aws_storagegateway_gateway" {
  source = "./modules/aws/r/aws_storagegateway_gateway"

  # activation_key - (optional) is a type of string
  activation_key = null
  # average_download_rate_limit_in_bits_per_sec - (optional) is a type of number
  average_download_rate_limit_in_bits_per_sec = null
  # average_upload_rate_limit_in_bits_per_sec - (optional) is a type of number
  average_upload_rate_limit_in_bits_per_sec = null
  # cloudwatch_log_group_arn - (optional) is a type of string
  cloudwatch_log_group_arn = null
  # gateway_ip_address - (optional) is a type of string
  gateway_ip_address = null
  # gateway_name - (required) is a type of string
  gateway_name = null
  # gateway_timezone - (required) is a type of string
  gateway_timezone = null
  # gateway_type - (optional) is a type of string
  gateway_type = null
  # gateway_vpc_endpoint - (optional) is a type of string
  gateway_vpc_endpoint = null
  # medium_changer_type - (optional) is a type of string
  medium_changer_type = null
  # smb_guest_password - (optional) is a type of string
  smb_guest_password = null
  # smb_security_strategy - (optional) is a type of string
  smb_security_strategy = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tape_drive_type - (optional) is a type of string
  tape_drive_type = null

  smb_active_directory_settings = [{
    active_directory_status = null
    domain_controllers      = []
    domain_name             = null
    organizational_unit     = null
    password                = null
    timeout_in_seconds      = null
    username                = null
  }]

  timeouts = [{
    create = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "activation_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "average_download_rate_limit_in_bits_per_sec" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "average_upload_rate_limit_in_bits_per_sec" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cloudwatch_log_group_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_name" {
  description = "(required)"
  type        = string
}

variable "gateway_timezone" {
  description = "(required)"
  type        = string
}

variable "gateway_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_vpc_endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "medium_changer_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smb_guest_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smb_security_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tape_drive_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smb_active_directory_settings" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      active_directory_status = string
      domain_controllers      = set(string)
      domain_name             = string
      organizational_unit     = string
      password                = string
      timeout_in_seconds      = number
      username                = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_storagegateway_gateway" "this" {
  activation_key                              = var.activation_key
  average_download_rate_limit_in_bits_per_sec = var.average_download_rate_limit_in_bits_per_sec
  average_upload_rate_limit_in_bits_per_sec   = var.average_upload_rate_limit_in_bits_per_sec
  cloudwatch_log_group_arn                    = var.cloudwatch_log_group_arn
  gateway_ip_address                          = var.gateway_ip_address
  gateway_name                                = var.gateway_name
  gateway_timezone                            = var.gateway_timezone
  gateway_type                                = var.gateway_type
  gateway_vpc_endpoint                        = var.gateway_vpc_endpoint
  medium_changer_type                         = var.medium_changer_type
  smb_guest_password                          = var.smb_guest_password
  smb_security_strategy                       = var.smb_security_strategy
  tags                                        = var.tags
  tape_drive_type                             = var.tape_drive_type

  dynamic "smb_active_directory_settings" {
    for_each = var.smb_active_directory_settings
    content {
      domain_controllers  = smb_active_directory_settings.value["domain_controllers"]
      domain_name         = smb_active_directory_settings.value["domain_name"]
      organizational_unit = smb_active_directory_settings.value["organizational_unit"]
      password            = smb_active_directory_settings.value["password"]
      timeout_in_seconds  = smb_active_directory_settings.value["timeout_in_seconds"]
      username            = smb_active_directory_settings.value["username"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "activation_key" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.activation_key
}

output "arn" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.arn
}

output "ec2_instance_id" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.ec2_instance_id
}

output "endpoint_type" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.endpoint_type
}

output "gateway_id" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.gateway_id
}

output "gateway_ip_address" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.gateway_ip_address
}

output "gateway_network_interface" {
  description = "returns a list of object"
  value       = aws_storagegateway_gateway.this.gateway_network_interface
}

output "host_environment" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.host_environment
}

output "id" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.id
}

output "smb_security_strategy" {
  description = "returns a string"
  value       = aws_storagegateway_gateway.this.smb_security_strategy
}

output "this" {
  value = aws_storagegateway_gateway.this
}
```
[top](#index)
