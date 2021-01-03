# alicloud_alidns_domains

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_alidns_domains" {
  source = "./modules/alicloud/d/alicloud_alidns_domains"

  # ali_domain - (optional) is a type of bool
  ali_domain = null
  # domain_name_regex - (optional) is a type of string
  domain_name_regex = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # group_id - (optional) is a type of string
  group_id = null
  # group_name_regex - (optional) is a type of string
  group_name_regex = null
  # ids - (optional) is a type of list of string
  ids = []
  # instance_id - (optional) is a type of string
  instance_id = null
  # key_word - (optional) is a type of string
  key_word = null
  # lang - (optional) is a type of string
  lang = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # search_mode - (optional) is a type of string
  search_mode = null
  # starmark - (optional) is a type of bool
  starmark = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version_code - (optional) is a type of string
  version_code = null
}
```

[top](#index)

### Variables

```terraform
variable "ali_domain" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "domain_name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_word" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "search_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "starmark" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version_code" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_alidns_domains" "this" {
  ali_domain        = var.ali_domain
  domain_name_regex = var.domain_name_regex
  enable_details    = var.enable_details
  group_id          = var.group_id
  group_name_regex  = var.group_name_regex
  ids               = var.ids
  instance_id       = var.instance_id
  key_word          = var.key_word
  lang              = var.lang
  output_file       = var.output_file
  resource_group_id = var.resource_group_id
  search_mode       = var.search_mode
  starmark          = var.starmark
  tags              = var.tags
  version_code      = var.version_code
}
```

[top](#index)

### Outputs

```terraform
output "domains" {
  description = "returns a list of object"
  value       = data.alicloud_alidns_domains.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_alidns_domains.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_alidns_domains.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_alidns_domains.this.names
}

output "this" {
  value = alicloud_alidns_domains.this
}
```

[top](#index)