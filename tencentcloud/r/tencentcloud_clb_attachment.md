# tencentcloud_clb_attachment

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
module "tencentcloud_clb_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_clb_attachment"

  # clb_id - (required) is a type of string
  clb_id = null
  # listener_id - (required) is a type of string
  listener_id = null
  # rule_id - (optional) is a type of string
  rule_id = null

  targets = [{
    instance_id = null
    port        = null
    weight      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "clb_id" {
  description = "(required) - ID of the CLB."
  type        = string
}

variable "listener_id" {
  description = "(required) - ID of the CLB listener."
  type        = string
}

variable "rule_id" {
  description = "(optional) - ID of the CLB listener rule. Only supports listeners of `HTTPS` and `HTTP` protocol."
  type        = string
  default     = null
}

variable "targets" {
  description = "nested block: NestingSet, min items: 1, max items: 100"
  type = set(object(
    {
      instance_id = string
      port        = number
      weight      = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_clb_attachment" "this" {
  # clb_id - (required) is a type of string
  clb_id = var.clb_id
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # rule_id - (optional) is a type of string
  rule_id = var.rule_id

  dynamic "targets" {
    for_each = var.targets
    content {
      # instance_id - (required) is a type of string
      instance_id = targets.value["instance_id"]
      # port - (required) is a type of number
      port = targets.value["port"]
      # weight - (optional) is a type of number
      weight = targets.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_clb_attachment.this.id
}

output "protocol_type" {
  description = "returns a string"
  value       = tencentcloud_clb_attachment.this.protocol_type
}

output "this" {
  value = tencentcloud_clb_attachment.this
}
```

[top](#index)