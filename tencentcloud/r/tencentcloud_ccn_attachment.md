# tencentcloud_ccn_attachment

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
module "tencentcloud_ccn_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_ccn_attachment"

  # ccn_id - (required) is a type of string
  ccn_id = null
  # ccn_uin - (optional) is a type of string
  ccn_uin = null
  # instance_id - (required) is a type of string
  instance_id = null
  # instance_region - (required) is a type of string
  instance_region = null
  # instance_type - (required) is a type of string
  instance_type = null
}
```

[top](#index)

### Variables

```terraform
variable "ccn_id" {
  description = "(required) - ID of the CCN."
  type        = string
}

variable "ccn_uin" {
  description = "(optional) - Uin of the ccn attached. Default is ``, which means the uin of this account. This parameter is used with case when attaching ccn of other account to the instance of this account. For now only support instance type `VPC`."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - ID of instance is attached."
  type        = string
}

variable "instance_region" {
  description = "(required) - The region that the instance locates at."
  type        = string
}

variable "instance_type" {
  description = "(required) - Type of attached instance network, and available values include `VPC`, `DIRECTCONNECT`, `BMVPC` and `VPNGW`. Note: `VPNGW` type is only for whitelist customer now."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ccn_attachment" "this" {
  ccn_id          = var.ccn_id
  ccn_uin         = var.ccn_uin
  instance_id     = var.instance_id
  instance_region = var.instance_region
  instance_type   = var.instance_type
}
```

[top](#index)

### Outputs

```terraform
output "attached_time" {
  description = "returns a string"
  value       = tencentcloud_ccn_attachment.this.attached_time
}

output "ccn_uin" {
  description = "returns a string"
  value       = tencentcloud_ccn_attachment.this.ccn_uin
}

output "cidr_block" {
  description = "returns a list of string"
  value       = tencentcloud_ccn_attachment.this.cidr_block
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_ccn_attachment.this.id
}

output "state" {
  description = "returns a string"
  value       = tencentcloud_ccn_attachment.this.state
}

output "this" {
  value = tencentcloud_ccn_attachment.this
}
```

[top](#index)