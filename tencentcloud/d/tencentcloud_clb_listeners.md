# tencentcloud_clb_listeners

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
module "tencentcloud_clb_listeners" {
  source = "./modules/tencentcloud/d/tencentcloud_clb_listeners"

  # clb_id - (required) is a type of string
  clb_id = null
  # listener_id - (optional) is a type of string
  listener_id = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "clb_id" {
  description = "(required) - Id of the CLB to be queried."
  type        = string
}

variable "listener_id" {
  description = "(optional) - Id of the listener to be queried."
  type        = string
  default     = null
}

variable "port" {
  description = "(optional) - Port of the CLB listener."
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional) - Type of protocol within the listener, and available values are `TCP`, `UDP`, `HTTP`, `HTTPS` and `TCP_SSL`."
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
data "tencentcloud_clb_listeners" "this" {
  clb_id             = var.clb_id
  listener_id        = var.listener_id
  port               = var.port
  protocol           = var.protocol
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_clb_listeners.this.id
}

output "listener_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_clb_listeners.this.listener_list
}

output "this" {
  value = tencentcloud_clb_listeners.this
}
```

[top](#index)