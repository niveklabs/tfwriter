# aviatrix_aws_tgw_connect

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
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_aws_tgw_connect" {
  source = "./modules/aviatrix/r/aviatrix_aws_tgw_connect"

  # connection_name - (required) is a type of string
  connection_name = null
  # security_domain_name - (required) is a type of string
  security_domain_name = null
  # tgw_name - (required) is a type of string
  tgw_name = null
  # transport_vpc_id - (required) is a type of string
  transport_vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_name" {
  description = "(required) - Connection Name."
  type        = string
}

variable "security_domain_name" {
  description = "(required) - Security Domain Name."
  type        = string
}

variable "tgw_name" {
  description = "(required) - AWS TGW Name."
  type        = string
}

variable "transport_vpc_id" {
  description = "(required) - Transport Attachment VPC ID."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_tgw_connect" "this" {
  # connection_name - (required) is a type of string
  connection_name = var.connection_name
  # security_domain_name - (required) is a type of string
  security_domain_name = var.security_domain_name
  # tgw_name - (required) is a type of string
  tgw_name = var.tgw_name
  # transport_vpc_id - (required) is a type of string
  transport_vpc_id = var.transport_vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "connect_attachment_id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_connect.this.connect_attachment_id
}

output "id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_connect.this.id
}

output "transport_attachment_id" {
  description = "returns a string"
  value       = aviatrix_aws_tgw_connect.this.transport_attachment_id
}

output "this" {
  value = aviatrix_aws_tgw_connect.this
}
```

[top](#index)