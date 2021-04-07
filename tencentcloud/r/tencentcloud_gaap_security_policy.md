# tencentcloud_gaap_security_policy

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_gaap_security_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_security_policy"

  # action - (required) is a type of string
  action = null
  # enable - (optional) is a type of bool
  enable = null
  # proxy_id - (required) is a type of string
  proxy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required) - Default policy. Valid value: `ACCEPT` and `DROP`."
  type        = string
}

variable "enable" {
  description = "(optional) - Indicates whether policy is enable, default value is `true`."
  type        = bool
  default     = null
}

variable "proxy_id" {
  description = "(required) - ID of the GAAP proxy."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_security_policy" "this" {
  action   = var.action
  enable   = var.enable
  proxy_id = var.proxy_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_security_policy.this.id
}

output "this" {
  value = tencentcloud_gaap_security_policy.this
}
```

[top](#index)