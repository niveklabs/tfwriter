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
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_controller_config" {
  source = "./modules/aviatrix/r/aviatrix_controller_config"

  # aws_guard_duty_scanning_interval - (optional) is a type of number
  aws_guard_duty_scanning_interval = null
  # backup_account_name - (optional) is a type of string
  backup_account_name = null
  # backup_bucket_name - (optional) is a type of string
  backup_bucket_name = null
  # backup_cloud_type - (optional) is a type of number
  backup_cloud_type = null
  # backup_configuration - (optional) is a type of bool
  backup_configuration = null
  # backup_container_name - (optional) is a type of string
  backup_container_name = null
  # backup_region - (optional) is a type of string
  backup_region = null
  # backup_storage_name - (optional) is a type of string
  backup_storage_name = null
  # ca_certificate_file_path - (optional) is a type of string
  ca_certificate_file_path = null
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
  # server_private_key_file_path - (optional) is a type of string
  server_private_key_file_path = null
  # server_public_certificate_file_path - (optional) is a type of string
  server_public_certificate_file_path = null
  # sg_management_account_name - (optional) is a type of string
  sg_management_account_name = null
  # target_version - (optional) is a type of string
  target_version = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_guard_duty_scanning_interval" {
  description = "(optional) - Scanning Interval for AWS Guard Duty."
  type        = number
  default     = null
}

variable "backup_account_name" {
  description = "(optional) - This parameter represents the name of a Cloud-Account in Aviatrix controller."
  type        = string
  default     = null
}

variable "backup_bucket_name" {
  description = "(optional) - Bucket name. Required for AWS, AWSGOV, GCP and OCI."
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

variable "backup_container_name" {
  description = "(optional) - Container name. Required for Azure."
  type        = string
  default     = null
}

variable "backup_region" {
  description = "(optional) - Name of region. Required for Azure and OCI."
  type        = string
  default     = null
}

variable "backup_storage_name" {
  description = "(optional) - Storage name. Required for Azure."
  type        = string
  default     = null
}

variable "ca_certificate_file_path" {
  description = "(optional) - File path to the CA Certificate."
  type        = string
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

variable "server_private_key_file_path" {
  description = "(optional) - File path to server private key."
  type        = string
  default     = null
}

variable "server_public_certificate_file_path" {
  description = "(optional) - File path to the Server public certificate."
  type        = string
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
  # aws_guard_duty_scanning_interval - (optional) is a type of number
  aws_guard_duty_scanning_interval = var.aws_guard_duty_scanning_interval
  # backup_account_name - (optional) is a type of string
  backup_account_name = var.backup_account_name
  # backup_bucket_name - (optional) is a type of string
  backup_bucket_name = var.backup_bucket_name
  # backup_cloud_type - (optional) is a type of number
  backup_cloud_type = var.backup_cloud_type
  # backup_configuration - (optional) is a type of bool
  backup_configuration = var.backup_configuration
  # backup_container_name - (optional) is a type of string
  backup_container_name = var.backup_container_name
  # backup_region - (optional) is a type of string
  backup_region = var.backup_region
  # backup_storage_name - (optional) is a type of string
  backup_storage_name = var.backup_storage_name
  # ca_certificate_file_path - (optional) is a type of string
  ca_certificate_file_path = var.ca_certificate_file_path
  # enable_vpc_dns_server - (optional) is a type of bool
  enable_vpc_dns_server = var.enable_vpc_dns_server
  # fqdn_exception_rule - (optional) is a type of bool
  fqdn_exception_rule = var.fqdn_exception_rule
  # http_access - (optional) is a type of bool
  http_access = var.http_access
  # multiple_backups - (optional) is a type of bool
  multiple_backups = var.multiple_backups
  # security_group_management - (optional) is a type of bool
  security_group_management = var.security_group_management
  # server_private_key_file_path - (optional) is a type of string
  server_private_key_file_path = var.server_private_key_file_path
  # server_public_certificate_file_path - (optional) is a type of string
  server_public_certificate_file_path = var.server_public_certificate_file_path
  # sg_management_account_name - (optional) is a type of string
  sg_management_account_name = var.sg_management_account_name
  # target_version - (optional) is a type of string
  target_version = var.target_version
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