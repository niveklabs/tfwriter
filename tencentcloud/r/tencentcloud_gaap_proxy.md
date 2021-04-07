# tencentcloud_gaap_proxy

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
module "tencentcloud_gaap_proxy" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_proxy"

  # access_region - (required) is a type of string
  access_region = null
  # bandwidth - (required) is a type of number
  bandwidth = null
  # concurrent - (required) is a type of number
  concurrent = null
  # enable - (optional) is a type of bool
  enable = null
  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # realserver_region - (required) is a type of string
  realserver_region = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "access_region" {
  description = "(required) - Access region of the GAAP proxy. Valid value: `NorthChina`, `EastChina`, `SouthChina`, `SouthwestChina`, `Hongkong`, `SL_TAIWAN`, `SoutheastAsia`, `Korea`, `SL_India`, `SL_Australia`, `Europe`, `SL_UK`, `SL_SouthAmerica`, `NorthAmerica`, `SL_MiddleUSA`, `Canada`, `SL_VIET`, `WestIndia`, `Thailand`, `Virginia`, `Russia`, `Japan` and `SL_Indonesia`."
  type        = string
}

variable "bandwidth" {
  description = "(required) - Maximum bandwidth of the GAAP proxy, unit is Mbps. Valid value: `10`, `20`, `50`, `100`, `200`, `500` and `1000`."
  type        = number
}

variable "concurrent" {
  description = "(required) - Maximum concurrency of the GAAP proxy, unit is 10k. Valid value: `2`, `5`, `10`, `20`, `30`, `40`, `50`, `60`, `70`, `80`, `90` and `100`."
  type        = number
}

variable "enable" {
  description = "(optional) - Indicates whether GAAP proxy is enabled, default value is `true`."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the GAAP proxy, the maximum length is 30."
  type        = string
}

variable "project_id" {
  description = "(optional) - ID of the project within the GAAP proxy, `0` means is default project."
  type        = number
  default     = null
}

variable "realserver_region" {
  description = "(required) - Region of the GAAP realserver. Valid value: `NorthChina`, `EastChina`, `SouthChina`, `SouthwestChina`, `Hongkong`, `SL_TAIWAN`, `SoutheastAsia`, `Korea`, `SL_India`, `SL_Australia`, `Europe`, `SL_UK`, `SL_SouthAmerica`, `NorthAmerica`, `SL_MiddleUSA`, `Canada`, `SL_VIET`, `WestIndia`, `Thailand`, `Virginia`, `Russia`, `Japan` and `SL_Indonesia`."
  type        = string
}

variable "tags" {
  description = "(optional) - Tags of the GAAP proxy."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_proxy" "this" {
  # access_region - (required) is a type of string
  access_region = var.access_region
  # bandwidth - (required) is a type of number
  bandwidth = var.bandwidth
  # concurrent - (required) is a type of number
  concurrent = var.concurrent
  # enable - (optional) is a type of bool
  enable = var.enable
  # name - (required) is a type of string
  name = var.name
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # realserver_region - (required) is a type of string
  realserver_region = var.realserver_region
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_gaap_proxy.this.create_time
}

output "domain" {
  description = "returns a string"
  value       = tencentcloud_gaap_proxy.this.domain
}

output "forward_ip" {
  description = "returns a string"
  value       = tencentcloud_gaap_proxy.this.forward_ip
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_proxy.this.id
}

output "ip" {
  description = "returns a string"
  value       = tencentcloud_gaap_proxy.this.ip
}

output "scalable" {
  description = "returns a bool"
  value       = tencentcloud_gaap_proxy.this.scalable
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_gaap_proxy.this.status
}

output "support_protocols" {
  description = "returns a list of string"
  value       = tencentcloud_gaap_proxy.this.support_protocols
}

output "this" {
  value = tencentcloud_gaap_proxy.this
}
```

[top](#index)