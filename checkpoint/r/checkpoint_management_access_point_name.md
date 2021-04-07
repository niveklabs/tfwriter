# checkpoint_management_access_point_name

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_access_point_name" {
  source = "./modules/checkpoint/r/checkpoint_management_access_point_name"

  # apn - (optional) is a type of string
  apn = null
  # block_traffic_other_end_user_domains - (optional) is a type of bool
  block_traffic_other_end_user_domains = null
  # block_traffic_this_end_user_domain - (optional) is a type of bool
  block_traffic_this_end_user_domain = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # end_user_domain - (optional) is a type of string
  end_user_domain = null
  # enforce_end_user_domain - (optional) is a type of bool
  enforce_end_user_domain = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "apn" {
  description = "(optional) - APN name."
  type        = string
  default     = null
}

variable "block_traffic_other_end_user_domains" {
  description = "(optional) - Block MS to MS traffic between this and other APN end user domains."
  type        = bool
  default     = null
}

variable "block_traffic_this_end_user_domain" {
  description = "(optional) - Block MS to MS traffic within this end user domain."
  type        = bool
  default     = null
}

variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "end_user_domain" {
  description = "(optional) - End user domain name or UID."
  type        = string
  default     = null
}

variable "enforce_end_user_domain" {
  description = "(optional) - Enable enforce end user domain."
  type        = bool
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_access_point_name" "this" {
  # apn - (optional) is a type of string
  apn = var.apn
  # block_traffic_other_end_user_domains - (optional) is a type of bool
  block_traffic_other_end_user_domains = var.block_traffic_other_end_user_domains
  # block_traffic_this_end_user_domain - (optional) is a type of bool
  block_traffic_this_end_user_domain = var.block_traffic_this_end_user_domain
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # end_user_domain - (optional) is a type of string
  end_user_domain = var.end_user_domain
  # enforce_end_user_domain - (optional) is a type of bool
  enforce_end_user_domain = var.enforce_end_user_domain
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_access_point_name.this.id
}

output "this" {
  value = checkpoint_management_access_point_name.this
}
```

[top](#index)