# tencentcloud_gaap_http_rules

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_gaap_http_rules" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_http_rules"

  # domain - (optional) is a type of string
  domain = null
  # forward_host - (optional) is a type of string
  forward_host = null
  # listener_id - (required) is a type of string
  listener_id = null
  # path - (optional) is a type of string
  path = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional) - Forward domain of the layer7 listener to be queried."
  type        = string
  default     = null
}

variable "forward_host" {
  description = "(optional) - Requested host which is forwarded to the realserver by the listener to be queried."
  type        = string
  default     = null
}

variable "listener_id" {
  description = "(required) - ID of the layer7 listener to be queried."
  type        = string
}

variable "path" {
  description = "(optional) - Path of the forward rule to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_gaap_http_rules" "this" {
  domain             = var.domain
  forward_host       = var.forward_host
  listener_id        = var.listener_id
  path               = var.path
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_http_rules.this.id
}

output "rules" {
  description = "returns a set of object"
  value       = data.tencentcloud_gaap_http_rules.this.rules
}

output "this" {
  value = tencentcloud_gaap_http_rules.this
}
```

[top](#index)