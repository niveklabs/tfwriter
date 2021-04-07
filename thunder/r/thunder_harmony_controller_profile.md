# thunder_harmony_controller_profile

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
module "thunder_harmony_controller_profile" {
  source = "./modules/thunder/r/thunder_harmony_controller_profile"

  # action - (optional) is a type of string
  action = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # host - (optional) is a type of string
  host = null
  # port - (optional) is a type of number
  port = null
  # provider2 - (optional) is a type of string
  provider2 = null
  # region - (optional) is a type of string
  region = null
  # secret_value - (optional) is a type of string
  secret_value = null
  # use_mgmt_port - (optional) is a type of number
  use_mgmt_port = null
  # user_name - (optional) is a type of string
  user_name = null

  thunder_mgmt_ip = [{
    ip_address = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "provider2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_mgmt_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "thunder_mgmt_ip" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip_address = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_harmony_controller_profile" "this" {
  # action - (optional) is a type of string
  action = var.action
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # host - (optional) is a type of string
  host = var.host
  # port - (optional) is a type of number
  port = var.port
  # provider2 - (optional) is a type of string
  provider2 = var.provider2
  # region - (optional) is a type of string
  region = var.region
  # secret_value - (optional) is a type of string
  secret_value = var.secret_value
  # use_mgmt_port - (optional) is a type of number
  use_mgmt_port = var.use_mgmt_port
  # user_name - (optional) is a type of string
  user_name = var.user_name

  dynamic "thunder_mgmt_ip" {
    for_each = var.thunder_mgmt_ip
    content {
      # ip_address - (optional) is a type of string
      ip_address = thunder_mgmt_ip.value["ip_address"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_harmony_controller_profile.this.id
}

output "this" {
  value = thunder_harmony_controller_profile.this
}
```

[top](#index)