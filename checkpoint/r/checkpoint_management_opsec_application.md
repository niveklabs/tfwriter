# checkpoint_management_opsec_application

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
module "checkpoint_management_opsec_application" {
  source = "./modules/checkpoint/r/checkpoint_management_opsec_application"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # cpmi - (optional) is a type of map of string
  cpmi = {}
  # host - (optional) is a type of string
  host = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # lea - (optional) is a type of map of string
  lea = {}
  # name - (required) is a type of string
  name = null
  # one_time_password - (optional) is a type of string
  one_time_password = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
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

variable "cpmi" {
  description = "(optional) - Used to setup the CPMI client entity."
  type        = map(string)
  default     = null
}

variable "host" {
  description = "(optional) - The host where the server is running. Pre-define the host as a network object."
  type        = string
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

variable "lea" {
  description = "(optional) - Used to setup the LEA client entity."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "one_time_password" {
  description = "(optional) - A password required for establishing a Secure Internal Communication (SIC)."
  type        = string
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
resource "checkpoint_management_opsec_application" "this" {
  color             = var.color
  comments          = var.comments
  cpmi              = var.cpmi
  host              = var.host
  ignore_errors     = var.ignore_errors
  ignore_warnings   = var.ignore_warnings
  lea               = var.lea
  name              = var.name
  one_time_password = var.one_time_password
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_opsec_application.this.id
}

output "this" {
  value = checkpoint_management_opsec_application.this
}
```

[top](#index)