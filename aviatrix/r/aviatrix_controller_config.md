# aviatrix_controller_config

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_controller_config" {
  source = "./modules/aviatrix/r/aviatrix_controller_config"

  # backup_account_name - (optional) is a type of string
  backup_account_name = null
  # backup_bucket_name - (optional) is a type of string
  backup_bucket_name = null
  # backup_cloud_type - (optional) is a type of number
  backup_cloud_type = null
  # backup_configuration - (optional) is a type of bool
  backup_configuration = null
  # enable_vpc_dns_server - (optional) is a type of bool
  enable_vpc_dns_server = null
  # fqdn_exception_rule - (optional) is a type of bool
  fqdn_exception_rule = null
  # http_access - (optional) is a type of bool
  http_access = null
  # multiple_backups - (optional) is a type of bool
  multiple_backups = null
  # security_group_management - (optional) is a type of bool
  security_group_management = null
  # sg_management_account_name - (optional) is a type of string
  sg_management_account_name = null
  # target_version - (optional) is a type of string
  target_version = null
}
```

[top](#index)

### Variables

```terraform
variable "backup_account_name" {
  description = "(optional) - This parameter represents the name of a Cloud-Account in Aviatrix controller."
  type        = string
  default     = null
}

variable "backup_bucket_name" {
  description = "(optional) - S3 Bucket Name for AWS."
  type        = string
  default     = null
}

variable "backup_cloud_type" {
  description = "(optional) - Type of cloud service provider, requires an integer value. Use 1 for AWS."
  type        = number
  default     = null
}

variable "backup_configuration" {
  description = "(optional) - Switch to enable/disable controller cloudn backup config."
  type        = bool
  default     = null
}

variable "enable_vpc_dns_server" {
  description = "(optional) - Enable VPC/VNET DNS Server."
  type        = bool
  default     = null
}

variable "fqdn_exception_rule" {
  description = "(optional) - A system-wide mode. Default: true."
  type        = bool
  default     = null
}

variable "http_access" {
  description = "(optional) - Switch for http access. Default: false."
  type        = bool
  default     = null
}

variable "multiple_backups" {
  description = "(optional) - Switch to enable the controller to backup up to a maximum of 3 rotating backups."
  type        = bool
  default     = null
}

variable "security_group_management" {
  description = "(optional) - Used to manage the Controller instance’s inbound rules from gateways."
  type        = bool
  default     = null
}

variable "sg_management_account_name" {
  description = "(optional) - Cloud account name of user."
  type        = string
  default     = null
}

variable "target_version" {
  description = "(optional) - The release version number to which the controller will be upgraded to."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_controller_config" "this" {
  backup_account_name        = var.backup_account_name
  backup_bucket_name         = var.backup_bucket_name
  backup_cloud_type          = var.backup_cloud_type
  backup_configuration       = var.backup_configuration
  enable_vpc_dns_server      = var.enable_vpc_dns_server
  fqdn_exception_rule        = var.fqdn_exception_rule
  http_access                = var.http_access
  multiple_backups           = var.multiple_backups
  security_group_management  = var.security_group_management
  sg_management_account_name = var.sg_management_account_name
  target_version             = var.target_version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_controller_config.this.id
}

output "version" {
  description = "returns a string"
  value       = aviatrix_controller_config.this.version
}

output "this" {
  value = aviatrix_controller_config.this
}
```

[top](#index)