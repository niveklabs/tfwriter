# thunder_slb_template_smtp

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
module "thunder_slb_template_smtp" {
  source = "./modules/thunder/r/thunder_slb_template_smtp"

  # client_starttls_type - (optional) is a type of string
  client_starttls_type = null
  # name - (optional) is a type of string
  name = null
  # server_domain - (optional) is a type of string
  server_domain = null
  # server_starttls_type - (optional) is a type of string
  server_starttls_type = null
  # service_ready_msg - (optional) is a type of string
  service_ready_msg = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  client_domain_switching = [{
    match_string   = null
    service_group  = null
    switching_type = null
  }]

  command_disable = [{
    disable_type = null
  }]

  template = [{
    logging = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "client_starttls_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_starttls_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_ready_msg" {
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

variable "client_domain_switching" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      match_string   = string
      service_group  = string
      switching_type = string
    }
  ))
  default = []
}

variable "command_disable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      disable_type = string
    }
  ))
  default = []
}

variable "template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      logging = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_smtp" "this" {
  client_starttls_type = var.client_starttls_type
  name                 = var.name
  server_domain        = var.server_domain
  server_starttls_type = var.server_starttls_type
  service_ready_msg    = var.service_ready_msg
  user_tag             = var.user_tag
  uuid                 = var.uuid

  dynamic "client_domain_switching" {
    for_each = var.client_domain_switching
    content {
      match_string   = client_domain_switching.value["match_string"]
      service_group  = client_domain_switching.value["service_group"]
      switching_type = client_domain_switching.value["switching_type"]
    }
  }

  dynamic "command_disable" {
    for_each = var.command_disable
    content {
      disable_type = command_disable.value["disable_type"]
    }
  }

  dynamic "template" {
    for_each = var.template
    content {
      logging = template.value["logging"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_smtp.this.id
}

output "this" {
  value = thunder_slb_template_smtp.this
}
```

[top](#index)