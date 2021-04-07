# alicloud_slb_server_certificate

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_slb_server_certificate" {
  source = "./modules/alicloud/r/alicloud_slb_server_certificate"

  # alicloud_certifacte_id - (optional) is a type of string
  alicloud_certifacte_id = null
  # alicloud_certifacte_name - (optional) is a type of string
  alicloud_certifacte_name = null
  # alicloud_certificate_id - (optional) is a type of string
  alicloud_certificate_id = null
  # alicloud_certificate_name - (optional) is a type of string
  alicloud_certificate_name = null
  # alicloud_certificate_region_id - (optional) is a type of string
  alicloud_certificate_region_id = null
  # name - (optional) is a type of string
  name = null
  # private_key - (optional) is a type of string
  private_key = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # server_certificate - (optional) is a type of string
  server_certificate = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "alicloud_certifacte_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_certifacte_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_certificate_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_certificate_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_certificate_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_server_certificate" "this" {
  # alicloud_certifacte_id - (optional) is a type of string
  alicloud_certifacte_id = var.alicloud_certifacte_id
  # alicloud_certifacte_name - (optional) is a type of string
  alicloud_certifacte_name = var.alicloud_certifacte_name
  # alicloud_certificate_id - (optional) is a type of string
  alicloud_certificate_id = var.alicloud_certificate_id
  # alicloud_certificate_name - (optional) is a type of string
  alicloud_certificate_name = var.alicloud_certificate_name
  # alicloud_certificate_region_id - (optional) is a type of string
  alicloud_certificate_region_id = var.alicloud_certificate_region_id
  # name - (optional) is a type of string
  name = var.name
  # private_key - (optional) is a type of string
  private_key = var.private_key
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # server_certificate - (optional) is a type of string
  server_certificate = var.server_certificate
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_slb_server_certificate.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_slb_server_certificate.this.resource_group_id
}

output "this" {
  value = alicloud_slb_server_certificate.this
}
```

[top](#index)