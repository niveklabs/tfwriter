# aci_firmware_download_task

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_firmware_download_task" {
  source = "./modules/aci/r/aci_firmware_download_task"

  # annotation - (optional) is a type of string
  annotation = null
  # auth_pass - (optional) is a type of string
  auth_pass = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # description - (optional) is a type of string
  description = null
  # dnld_task_flip - (optional) is a type of string
  dnld_task_flip = null
  # identity_private_key_contents - (optional) is a type of string
  identity_private_key_contents = null
  # identity_private_key_passphrase - (optional) is a type of string
  identity_private_key_passphrase = null
  # identity_public_key_contents - (optional) is a type of string
  identity_public_key_contents = null
  # load_catalog_if_exists_and_newer - (optional) is a type of string
  load_catalog_if_exists_and_newer = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # password - (optional) is a type of string
  password = null
  # polling_interval - (optional) is a type of string
  polling_interval = null
  # proto - (optional) is a type of string
  proto = null
  # url - (optional) is a type of string
  url = null
  # user - (optional) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_pass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dnld_task_flip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_private_key_contents" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_private_key_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_public_key_contents" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_catalog_if_exists_and_newer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "polling_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_firmware_download_task" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # auth_pass - (optional) is a type of string
  auth_pass = var.auth_pass
  # auth_type - (optional) is a type of string
  auth_type = var.auth_type
  # description - (optional) is a type of string
  description = var.description
  # dnld_task_flip - (optional) is a type of string
  dnld_task_flip = var.dnld_task_flip
  # identity_private_key_contents - (optional) is a type of string
  identity_private_key_contents = var.identity_private_key_contents
  # identity_private_key_passphrase - (optional) is a type of string
  identity_private_key_passphrase = var.identity_private_key_passphrase
  # identity_public_key_contents - (optional) is a type of string
  identity_public_key_contents = var.identity_public_key_contents
  # load_catalog_if_exists_and_newer - (optional) is a type of string
  load_catalog_if_exists_and_newer = var.load_catalog_if_exists_and_newer
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # password - (optional) is a type of string
  password = var.password
  # polling_interval - (optional) is a type of string
  polling_interval = var.polling_interval
  # proto - (optional) is a type of string
  proto = var.proto
  # url - (optional) is a type of string
  url = var.url
  # user - (optional) is a type of string
  user = var.user
}
```

[top](#index)

### Outputs

```terraform
output "auth_pass" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.auth_pass
}

output "auth_type" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.auth_type
}

output "description" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.description
}

output "dnld_task_flip" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.dnld_task_flip
}

output "id" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.id
}

output "identity_private_key_contents" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.identity_private_key_contents
}

output "identity_private_key_passphrase" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.identity_private_key_passphrase
}

output "identity_public_key_contents" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.identity_public_key_contents
}

output "load_catalog_if_exists_and_newer" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.load_catalog_if_exists_and_newer
}

output "name_alias" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.name_alias
}

output "password" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.password
}

output "polling_interval" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.polling_interval
}

output "proto" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.proto
}

output "url" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.url
}

output "user" {
  description = "returns a string"
  value       = aci_firmware_download_task.this.user
}

output "this" {
  value = aci_firmware_download_task.this
}
```

[top](#index)