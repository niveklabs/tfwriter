# thunder_slb_template_smpp

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_smpp" {
  source = "./modules/thunder/r/thunder_slb_template_smpp"

  # client_enquire_link - (optional) is a type of number
  client_enquire_link = null
  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # server_enquire_link - (optional) is a type of number
  server_enquire_link = null
  # server_enquire_link_val - (optional) is a type of number
  server_enquire_link_val = null
  # server_selection_per_request - (optional) is a type of number
  server_selection_per_request = null
  # user - (optional) is a type of string
  user = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "client_enquire_link" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_enquire_link" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_enquire_link_val" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_selection_per_request" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_smpp" "this" {
  client_enquire_link          = var.client_enquire_link
  name                         = var.name
  password                     = var.password
  server_enquire_link          = var.server_enquire_link
  server_enquire_link_val      = var.server_enquire_link_val
  server_selection_per_request = var.server_selection_per_request
  user                         = var.user
  user_tag                     = var.user_tag
  uuid                         = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_smpp.this.id
}

output "this" {
  value = thunder_slb_template_smpp.this
}
```

[top](#index)