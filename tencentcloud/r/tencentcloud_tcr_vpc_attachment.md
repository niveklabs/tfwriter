# tencentcloud_tcr_vpc_attachment

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
module "tencentcloud_tcr_vpc_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_tcr_vpc_attachment"

  # enable_public_domain_dns - (optional) is a type of bool
  enable_public_domain_dns = null
  # enable_vpc_domain_dns - (optional) is a type of bool
  enable_vpc_domain_dns = null
  # instance_id - (required) is a type of string
  instance_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_public_domain_dns" {
  description = "(optional) - Whether to enable public domain dns. Default value is `false`."
  type        = bool
  default     = null
}

variable "enable_vpc_domain_dns" {
  description = "(optional) - Whether to enable vpc domain dns. Default value is `false`."
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(required) - ID of the TCR instance."
  type        = string
}

variable "subnet_id" {
  description = "(required) - ID of subnet."
  type        = string
}

variable "vpc_id" {
  description = "(required) - ID of VPC."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcr_vpc_attachment" "this" {
  enable_public_domain_dns = var.enable_public_domain_dns
  enable_vpc_domain_dns    = var.enable_vpc_domain_dns
  instance_id              = var.instance_id
  subnet_id                = var.subnet_id
  vpc_id                   = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "access_ip" {
  description = "returns a string"
  value       = tencentcloud_tcr_vpc_attachment.this.access_ip
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_tcr_vpc_attachment.this.id
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_tcr_vpc_attachment.this.status
}

output "this" {
  value = tencentcloud_tcr_vpc_attachment.this
}
```

[top](#index)