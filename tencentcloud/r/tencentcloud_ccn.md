# tencentcloud_ccn

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
module "tencentcloud_ccn" {
  source = "./modules/tencentcloud/r/tencentcloud_ccn"

  # bandwidth_limit_type - (optional) is a type of string
  bandwidth_limit_type = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # qos - (optional) is a type of string
  qos = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth_limit_type" {
  description = "(optional) - The speed limit type. Valid values: `INTER_REGION_LIMIT`, `OUTER_REGION_LIMIT`. `OUTER_REGION_LIMIT` represents the regional export speed limit, `INTER_REGION_LIMIT` is the inter-regional speed limit. The default is `OUTER_REGION_LIMIT`."
  type        = string
  default     = null
}

variable "charge_type" {
  description = "(optional) - Billing mode. Valid values: `PREPAID`, `POSTPAID`. `PREPAID` means prepaid, which means annual and monthly subscription, `POSTPAID` means post-payment, which means billing by volume. The default is `POSTPAID`. The prepaid model only supports inter-regional speed limit, and the post-paid model supports inter-regional speed limit and regional export speed limit."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of CCN, and maximum length does not exceed 100 bytes."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the CCN to be queried, and maximum length does not exceed 60 bytes."
  type        = string
}

variable "qos" {
  description = "(optional) - Service quality of CCN. Valid values: `PT`, `AU`, `AG`. The default is `AU`."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Instance tag."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ccn" "this" {
  bandwidth_limit_type = var.bandwidth_limit_type
  charge_type          = var.charge_type
  description          = var.description
  name                 = var.name
  qos                  = var.qos
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_ccn.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_ccn.this.id
}

output "instance_count" {
  description = "returns a number"
  value       = tencentcloud_ccn.this.instance_count
}

output "state" {
  description = "returns a string"
  value       = tencentcloud_ccn.this.state
}

output "this" {
  value = tencentcloud_ccn.this
}
```

[top](#index)