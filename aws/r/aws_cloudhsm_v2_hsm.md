# aws_cloudhsm_v2_hsm
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_cloudhsm_v2_hsm" {
  source = "./modules/aws/r/aws_cloudhsm_v2_hsm"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # subnet_id - (optional) is a type of string
  subnet_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_cloudhsm_v2_hsm" "this" {
  availability_zone = var.availability_zone
  cluster_id        = var.cluster_id
  ip_address        = var.ip_address
  subnet_id         = var.subnet_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "availability_zone" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_hsm.this.availability_zone
}

output "hsm_eni_id" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_hsm.this.hsm_eni_id
}

output "hsm_id" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_hsm.this.hsm_id
}

output "hsm_state" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_hsm.this.hsm_state
}

output "id" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_hsm.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_hsm.this.ip_address
}

output "subnet_id" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_hsm.this.subnet_id
}

output "this" {
  value = aws_cloudhsm_v2_hsm.this
}
```
[top](#index)
