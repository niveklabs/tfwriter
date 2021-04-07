# tencentcloud_ccn_bandwidth_limit

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
module "tencentcloud_ccn_bandwidth_limit" {
  source = "./modules/tencentcloud/r/tencentcloud_ccn_bandwidth_limit"

  # bandwidth_limit - (optional) is a type of number
  bandwidth_limit = null
  # ccn_id - (required) is a type of string
  ccn_id = null
  # dst_region - (optional) is a type of string
  dst_region = null
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth_limit" {
  description = "(optional) - Limitation of bandwidth."
  type        = number
  default     = null
}

variable "ccn_id" {
  description = "(required) - ID of the CCN."
  type        = string
}

variable "dst_region" {
  description = "(optional) - Destination area restriction. If the `CCN` rate limit type is `OUTER_REGION_LIMIT`, this value does not need to be set."
  type        = string
  default     = null
}

variable "region" {
  description = "(required) - Limitation of region."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ccn_bandwidth_limit" "this" {
  bandwidth_limit = var.bandwidth_limit
  ccn_id          = var.ccn_id
  dst_region      = var.dst_region
  region          = var.region
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_limit" {
  description = "returns a number"
  value       = tencentcloud_ccn_bandwidth_limit.this.bandwidth_limit
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_ccn_bandwidth_limit.this.id
}

output "this" {
  value = tencentcloud_ccn_bandwidth_limit.this
}
```

[top](#index)