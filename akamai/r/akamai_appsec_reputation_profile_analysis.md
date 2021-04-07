# akamai_appsec_reputation_profile_analysis

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_reputation_profile_analysis" {
  source = "./modules/akamai/r/akamai_appsec_reputation_profile_analysis"

  # config_id - (required) is a type of number
  config_id = null
  # forward_shared_ip_to_http_header_siem - (required) is a type of bool
  forward_shared_ip_to_http_header_siem = null
  # forward_to_http_header - (required) is a type of bool
  forward_to_http_header = null
  # security_policy_id - (required) is a type of string
  security_policy_id = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "forward_shared_ip_to_http_header_siem" {
  description = "(required)"
  type        = bool
}

variable "forward_to_http_header" {
  description = "(required)"
  type        = bool
}

variable "security_policy_id" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_reputation_profile_analysis" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # forward_shared_ip_to_http_header_siem - (required) is a type of bool
  forward_shared_ip_to_http_header_siem = var.forward_shared_ip_to_http_header_siem
  # forward_to_http_header - (required) is a type of bool
  forward_to_http_header = var.forward_to_http_header
  # security_policy_id - (required) is a type of string
  security_policy_id = var.security_policy_id
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_reputation_profile_analysis.this.id
}

output "this" {
  value = akamai_appsec_reputation_profile_analysis.this
}
```

[top](#index)