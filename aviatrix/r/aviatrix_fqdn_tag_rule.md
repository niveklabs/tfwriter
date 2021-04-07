# aviatrix_fqdn_tag_rule

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_fqdn_tag_rule" {
  source = "./modules/aviatrix/r/aviatrix_fqdn_tag_rule"

  # action - (optional) is a type of string
  action = null
  # fqdn - (required) is a type of string
  fqdn = null
  # fqdn_tag_name - (required) is a type of string
  fqdn_tag_name = null
  # port - (required) is a type of string
  port = null
  # protocol - (required) is a type of string
  protocol = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional) - What action should happen to matching requests. Possible values are: 'Base Policy', 'Allow' or 'Deny'. Defaults to 'Base Policy' if no value is provided."
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(required) - FQDN."
  type        = string
}

variable "fqdn_tag_name" {
  description = "(required) - FQDN Filter Tag Name to attach this domain."
  type        = string
}

variable "port" {
  description = "(required) - Port."
  type        = string
}

variable "protocol" {
  description = "(required) - Protocol."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_fqdn_tag_rule" "this" {
  # action - (optional) is a type of string
  action = var.action
  # fqdn - (required) is a type of string
  fqdn = var.fqdn
  # fqdn_tag_name - (required) is a type of string
  fqdn_tag_name = var.fqdn_tag_name
  # port - (required) is a type of string
  port = var.port
  # protocol - (required) is a type of string
  protocol = var.protocol
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_fqdn_tag_rule.this.id
}

output "this" {
  value = aviatrix_fqdn_tag_rule.this
}
```

[top](#index)