# checkpoint_management_access_layer

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
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_access_layer" {
  source = "./modules/checkpoint/r/checkpoint_management_access_layer"

  # applications_and_url_filtering - (optional) is a type of bool
  applications_and_url_filtering = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # content_awareness - (optional) is a type of bool
  content_awareness = null
  # detect_using_x_forward_for - (optional) is a type of bool
  detect_using_x_forward_for = null
  # firewall - (optional) is a type of bool
  firewall = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # implicit_cleanup_action - (optional) is a type of string
  implicit_cleanup_action = null
  # mobile_access - (optional) is a type of bool
  mobile_access = null
  # name - (required) is a type of string
  name = null
  # shared - (optional) is a type of bool
  shared = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "applications_and_url_filtering" {
  description = "(optional) - Whether to enable Applications & URL Filtering blade on the layer."
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

variable "content_awareness" {
  description = "(optional) - Whether to enable Content Awareness blade on the layer."
  type        = bool
  default     = null
}

variable "detect_using_x_forward_for" {
  description = "(optional) - Whether to use X-Forward-For HTTP header, which is added by the  proxy server to keep track of the original source IP."
  type        = bool
  default     = null
}

variable "firewall" {
  description = "(optional) - Whether to enable Firewall blade on the layer."
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

variable "implicit_cleanup_action" {
  description = "(optional) - The default \"catch-all\" action for traffic that does not match any explicit or implied rules in the layer."
  type        = string
  default     = null
}

variable "mobile_access" {
  description = "(optional) - Whether to enable Mobile Access blade on the layer."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "shared" {
  description = "(optional) - Whether this layer is shared."
  type        = bool
  default     = null
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
resource "checkpoint_management_access_layer" "this" {
  applications_and_url_filtering = var.applications_and_url_filtering
  color                          = var.color
  comments                       = var.comments
  content_awareness              = var.content_awareness
  detect_using_x_forward_for     = var.detect_using_x_forward_for
  firewall                       = var.firewall
  ignore_errors                  = var.ignore_errors
  ignore_warnings                = var.ignore_warnings
  implicit_cleanup_action        = var.implicit_cleanup_action
  mobile_access                  = var.mobile_access
  name                           = var.name
  shared                         = var.shared
  tags                           = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_access_layer.this.id
}

output "this" {
  value = checkpoint_management_access_layer.this
}
```

[top](#index)