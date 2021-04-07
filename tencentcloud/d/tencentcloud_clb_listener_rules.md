# tencentcloud_clb_listener_rules

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
module "tencentcloud_clb_listener_rules" {
  source = "./modules/tencentcloud/d/tencentcloud_clb_listener_rules"

  # clb_id - (required) is a type of string
  clb_id = null
  # domain - (optional) is a type of string
  domain = null
  # listener_id - (required) is a type of string
  listener_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # rule_id - (optional) is a type of string
  rule_id = null
  # scheduler - (optional) is a type of string
  scheduler = null
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "clb_id" {
  description = "(required) - ID of the CLB to be queried."
  type        = string
}

variable "domain" {
  description = "(optional) - Domain name of the forwarding rule to be queried."
  type        = string
  default     = null
}

variable "listener_id" {
  description = "(required) - ID of the CLB listener to be queried."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(optional) - ID of the forwarding rule to be queried."
  type        = string
  default     = null
}

variable "scheduler" {
  description = "(optional) - Scheduling method of the forwarding rule of thr CLB listener, and available values include `WRR`, `IP HASH` and `LEAST_CONN`. The default is `WRR`."
  type        = string
  default     = null
}

variable "url" {
  description = "(optional) - Url of the forwarding rule to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_clb_listener_rules" "this" {
  clb_id             = var.clb_id
  domain             = var.domain
  listener_id        = var.listener_id
  result_output_file = var.result_output_file
  rule_id            = var.rule_id
  scheduler          = var.scheduler
  url                = var.url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_clb_listener_rules.this.id
}

output "rule_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_clb_listener_rules.this.rule_list
}

output "this" {
  value = tencentcloud_clb_listener_rules.this
}
```

[top](#index)