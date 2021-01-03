# bigip_ltm_profile_fasthttp

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_profile_fasthttp" {
  source = "./modules/bigip/r/bigip_ltm_profile_fasthttp"

  # connpool_maxreuse - (optional) is a type of number
  connpool_maxreuse = null
  # connpool_maxsize - (optional) is a type of number
  connpool_maxsize = null
  # connpool_minsize - (optional) is a type of number
  connpool_minsize = null
  # connpool_replenish - (optional) is a type of string
  connpool_replenish = null
  # connpool_step - (optional) is a type of number
  connpool_step = null
  # connpoolidle_timeoutoverride - (optional) is a type of number
  connpoolidle_timeoutoverride = null
  # defaults_from - (optional) is a type of string
  defaults_from = null
  # forcehttp_10response - (optional) is a type of string
  forcehttp_10response = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # maxheader_size - (optional) is a type of number
  maxheader_size = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "connpool_maxreuse" {
  description = "(optional) - connpool_maxreuse timer"
  type        = number
  default     = null
}

variable "connpool_maxsize" {
  description = "(optional) - timer integer"
  type        = number
  default     = null
}

variable "connpool_minsize" {
  description = "(optional) - Pool min size"
  type        = number
  default     = null
}

variable "connpool_replenish" {
  description = "(optional) - enabled or disabled"
  type        = string
  default     = null
}

variable "connpool_step" {
  description = "(optional) - integer value"
  type        = number
  default     = null
}

variable "connpoolidle_timeoutoverride" {
  description = "(optional) - idle_timeout can be given value"
  type        = number
  default     = null
}

variable "defaults_from" {
  description = "(optional) - Use the parent Fasthttp profile"
  type        = string
  default     = null
}

variable "forcehttp_10response" {
  description = "(optional) - disabled or enabled "
  type        = string
  default     = null
}

variable "idle_timeout" {
  description = "(optional) - integer value"
  type        = number
  default     = null
}

variable "maxheader_size" {
  description = "(optional) - integer value"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the Fasthttp Profile"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_profile_fasthttp" "this" {
  connpool_maxreuse            = var.connpool_maxreuse
  connpool_maxsize             = var.connpool_maxsize
  connpool_minsize             = var.connpool_minsize
  connpool_replenish           = var.connpool_replenish
  connpool_step                = var.connpool_step
  connpoolidle_timeoutoverride = var.connpoolidle_timeoutoverride
  defaults_from                = var.defaults_from
  forcehttp_10response         = var.forcehttp_10response
  idle_timeout                 = var.idle_timeout
  maxheader_size               = var.maxheader_size
  name                         = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_ltm_profile_fasthttp.this.id
}

output "this" {
  value = bigip_ltm_profile_fasthttp.this
}
```

[top](#index)