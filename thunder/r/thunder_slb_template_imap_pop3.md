# thunder_slb_template_imap_pop3

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
module "thunder_slb_template_imap_pop3" {
  source = "./modules/thunder/r/thunder_slb_template_imap_pop3"

  # logindisabled - (optional) is a type of number
  logindisabled = null
  # name - (optional) is a type of string
  name = null
  # starttls - (optional) is a type of string
  starttls = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "logindisabled" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "starttls" {
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
resource "thunder_slb_template_imap_pop3" "this" {
  # logindisabled - (optional) is a type of number
  logindisabled = var.logindisabled
  # name - (optional) is a type of string
  name = var.name
  # starttls - (optional) is a type of string
  starttls = var.starttls
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_imap_pop3.this.id
}

output "this" {
  value = thunder_slb_template_imap_pop3.this
}
```

[top](#index)