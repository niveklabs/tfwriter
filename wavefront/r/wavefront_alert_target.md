# wavefront_alert_target

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_alert_target" {
  source = "./modules/wavefront/r/wavefront_alert_target"

  # content_type - (optional) is a type of string
  content_type = null
  # custom_headers - (optional) is a type of map of string
  custom_headers = {}
  # description - (required) is a type of string
  description = null
  # email_subject - (optional) is a type of string
  email_subject = null
  # is_html_content - (optional) is a type of bool
  is_html_content = null
  # method - (optional) is a type of string
  method = null
  # name - (required) is a type of string
  name = null
  # recipient - (required) is a type of string
  recipient = null
  # template - (required) is a type of string
  template = null
  # triggers - (required) is a type of list of string
  triggers = []

  route = [{
    filter = {}
    method = null
    target = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_headers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "email_subject" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_html_content" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "recipient" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "triggers" {
  description = "(required)"
  type        = list(string)
}

variable "route" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      filter = map(string)
      method = string
      target = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_alert_target" "this" {
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # custom_headers - (optional) is a type of map of string
  custom_headers = var.custom_headers
  # description - (required) is a type of string
  description = var.description
  # email_subject - (optional) is a type of string
  email_subject = var.email_subject
  # is_html_content - (optional) is a type of bool
  is_html_content = var.is_html_content
  # method - (optional) is a type of string
  method = var.method
  # name - (required) is a type of string
  name = var.name
  # recipient - (required) is a type of string
  recipient = var.recipient
  # template - (required) is a type of string
  template = var.template
  # triggers - (required) is a type of list of string
  triggers = var.triggers

  dynamic "route" {
    for_each = var.route
    content {
      # filter - (optional) is a type of map of string
      filter = route.value["filter"]
      # method - (required) is a type of string
      method = route.value["method"]
      # target - (required) is a type of string
      target = route.value["target"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_alert_target.this.id
}

output "target_id" {
  description = "returns a string"
  value       = wavefront_alert_target.this.target_id
}

output "this" {
  value = wavefront_alert_target.this
}
```

[top](#index)