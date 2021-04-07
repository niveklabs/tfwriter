# aviatrix_proxy_config

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
module "aviatrix_proxy_config" {
  source = "./modules/aviatrix/r/aviatrix_proxy_config"

  # http_proxy - (required) is a type of string
  http_proxy = null
  # https_proxy - (required) is a type of string
  https_proxy = null
  # proxy_ca_certificate - (optional) is a type of string
  proxy_ca_certificate = null
}
```

[top](#index)

### Variables

```terraform
variable "http_proxy" {
  description = "(required) - http proxy URL."
  type        = string
}

variable "https_proxy" {
  description = "(required) - https proxy URL."
  type        = string
}

variable "proxy_ca_certificate" {
  description = "(optional) - Server CA Certificate file."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_proxy_config" "this" {
  # http_proxy - (required) is a type of string
  http_proxy = var.http_proxy
  # https_proxy - (required) is a type of string
  https_proxy = var.https_proxy
  # proxy_ca_certificate - (optional) is a type of string
  proxy_ca_certificate = var.proxy_ca_certificate
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_proxy_config.this.id
}

output "this" {
  value = aviatrix_proxy_config.this
}
```

[top](#index)