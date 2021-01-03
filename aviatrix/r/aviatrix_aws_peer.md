# aviatrix_aws_peer

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_aws_peer" {
  source = "./modules/aviatrix/r/aviatrix_aws_peer"

  # account_name1 - (required) is a type of string
  account_name1 = null
  # account_name2 - (required) is a type of string
  account_name2 = null
  # rtb_list1 - (optional) is a type of list of string
  rtb_list1 = []
  # rtb_list2 - (optional) is a type of list of string
  rtb_list2 = []
  # vpc_id1 - (required) is a type of string
  vpc_id1 = null
  # vpc_id2 - (required) is a type of string
  vpc_id2 = null
  # vpc_reg1 - (required) is a type of string
  vpc_reg1 = null
  # vpc_reg2 - (required) is a type of string
  vpc_reg2 = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name1" {
  description = "(required) - This parameter represents the name of an AWS Cloud-Account in Aviatrix controller."
  type        = string
}

variable "account_name2" {
  description = "(required) - This parameter represents the name of an AWS Cloud-Account in Aviatrix controller."
  type        = string
}

variable "rtb_list1" {
  description = "(optional) - List of Route table ID."
  type        = list(string)
  default     = null
}

variable "rtb_list2" {
  description = "(optional) - List of Route table ID."
  type        = list(string)
  default     = null
}

variable "vpc_id1" {
  description = "(required) - VPC-ID of AWS cloud."
  type        = string
}

variable "vpc_id2" {
  description = "(required) - VPC-ID of AWS cloud."
  type        = string
}

variable "vpc_reg1" {
  description = "(required) - Region of AWS cloud."
  type        = string
}

variable "vpc_reg2" {
  description = "(required) - Region of AWS cloud."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_peer" "this" {
  account_name1 = var.account_name1
  account_name2 = var.account_name2
  rtb_list1     = var.rtb_list1
  rtb_list2     = var.rtb_list2
  vpc_id1       = var.vpc_id1
  vpc_id2       = var.vpc_id2
  vpc_reg1      = var.vpc_reg1
  vpc_reg2      = var.vpc_reg2
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_peer.this.id
}

output "rtb_list1_output" {
  description = "returns a list of string"
  value       = aviatrix_aws_peer.this.rtb_list1_output
}

output "rtb_list2_output" {
  description = "returns a list of string"
  value       = aviatrix_aws_peer.this.rtb_list2_output
}

output "this" {
  value = aviatrix_aws_peer.this
}
```

[top](#index)