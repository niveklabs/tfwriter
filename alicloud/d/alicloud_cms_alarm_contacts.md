# alicloud_cms_alarm_contacts

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cms_alarm_contacts" {
  source = "./modules/alicloud/d/alicloud_cms_alarm_contacts"

  # chanel_type - (optional) is a type of string
  chanel_type = null
  # chanel_value - (optional) is a type of string
  chanel_value = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "chanel_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "chanel_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cms_alarm_contacts" "this" {
  # chanel_type - (optional) is a type of string
  chanel_type = var.chanel_type
  # chanel_value - (optional) is a type of string
  chanel_value = var.chanel_value
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "contacts" {
  description = "returns a list of object"
  value       = data.alicloud_cms_alarm_contacts.this.contacts
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cms_alarm_contacts.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cms_alarm_contacts.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_cms_alarm_contacts.this.names
}

output "this" {
  value = alicloud_cms_alarm_contacts.this
}
```

[top](#index)