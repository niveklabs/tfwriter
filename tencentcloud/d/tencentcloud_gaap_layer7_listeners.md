# tencentcloud_gaap_layer7_listeners

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
module "tencentcloud_gaap_layer7_listeners" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_layer7_listeners"

  # listener_id - (optional) is a type of string
  listener_id = null
  # listener_name - (optional) is a type of string
  listener_name = null
  # port - (optional) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # proxy_id - (optional) is a type of string
  proxy_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "listener_id" {
  description = "(optional) - ID of the layer7 listener to be queried."
  type        = string
  default     = null
}

variable "listener_name" {
  description = "(optional) - Name of the layer7 listener to be queried."
  type        = string
  default     = null
}

variable "port" {
  description = "(optional) - Port of the layer7 listener to be queried."
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required) - Protocol of the layer7 listener to be queried. Valid values: `HTTP` and `HTTPS`."
  type        = string
}

variable "proxy_id" {
  description = "(optional) - ID of the GAAP proxy to be queried."
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
data "tencentcloud_gaap_layer7_listeners" "this" {
  listener_id        = var.listener_id
  listener_name      = var.listener_name
  port               = var.port
  protocol           = var.protocol
  proxy_id           = var.proxy_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_gaap_layer7_listeners.this.id
}

output "listeners" {
  description = "returns a list of object"
  value       = data.tencentcloud_gaap_layer7_listeners.this.listeners
}

output "this" {
  value = tencentcloud_gaap_layer7_listeners.this
}
```

[top](#index)