# thunder_glm

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
module "thunder_glm" {
  source = "./modules/thunder/r/thunder_glm"

  # allocate_bandwidth - (optional) is a type of number
  allocate_bandwidth = null
  # appliance_name - (optional) is a type of string
  appliance_name = null
  # burst - (optional) is a type of number
  burst = null
  # enable_requests - (optional) is a type of number
  enable_requests = null
  # enterprise - (optional) is a type of string
  enterprise = null
  # interval - (optional) is a type of number
  interval = null
  # port - (optional) is a type of number
  port = null
  # token - (optional) is a type of string
  token = null
  # use_mgmt_port - (optional) is a type of number
  use_mgmt_port = null
  # uuid - (optional) is a type of string
  uuid = null

  proxy_server = [{
    encrypted     = null
    host          = null
    password      = null
    port          = null
    secret_string = null
    username      = null
    uuid          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allocate_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "appliance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "burst" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_requests" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enterprise" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_mgmt_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_server" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      encrypted     = string
      host          = string
      password      = number
      port          = number
      secret_string = string
      username      = string
      uuid          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_glm" "this" {
  # allocate_bandwidth - (optional) is a type of number
  allocate_bandwidth = var.allocate_bandwidth
  # appliance_name - (optional) is a type of string
  appliance_name = var.appliance_name
  # burst - (optional) is a type of number
  burst = var.burst
  # enable_requests - (optional) is a type of number
  enable_requests = var.enable_requests
  # enterprise - (optional) is a type of string
  enterprise = var.enterprise
  # interval - (optional) is a type of number
  interval = var.interval
  # port - (optional) is a type of number
  port = var.port
  # token - (optional) is a type of string
  token = var.token
  # use_mgmt_port - (optional) is a type of number
  use_mgmt_port = var.use_mgmt_port
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "proxy_server" {
    for_each = var.proxy_server
    content {
      # encrypted - (optional) is a type of string
      encrypted = proxy_server.value["encrypted"]
      # host - (optional) is a type of string
      host = proxy_server.value["host"]
      # password - (optional) is a type of number
      password = proxy_server.value["password"]
      # port - (optional) is a type of number
      port = proxy_server.value["port"]
      # secret_string - (optional) is a type of string
      secret_string = proxy_server.value["secret_string"]
      # username - (optional) is a type of string
      username = proxy_server.value["username"]
      # uuid - (optional) is a type of string
      uuid = proxy_server.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_glm.this.id
}

output "this" {
  value = thunder_glm.this
}
```

[top](#index)