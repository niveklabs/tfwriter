# aws_ec2_client_vpn_endpoint

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
module "aws_ec2_client_vpn_endpoint" {
  source = "./modules/aws/r/aws_ec2_client_vpn_endpoint"

  # client_cidr_block - (required) is a type of string
  client_cidr_block = null
  # description - (optional) is a type of string
  description = null
  # dns_servers - (optional) is a type of set of string
  dns_servers = []
  # server_certificate_arn - (required) is a type of string
  server_certificate_arn = null
  # split_tunnel - (optional) is a type of bool
  split_tunnel = null
  # tags - (optional) is a type of map of string
  tags = {}
  # transport_protocol - (optional) is a type of string
  transport_protocol = null

  authentication_options = [{
    active_directory_id        = null
    root_certificate_chain_arn = null
    saml_provider_arn          = null
    type                       = null
  }]

  connection_log_options = [{
    cloudwatch_log_group  = null
    cloudwatch_log_stream = null
    enabled               = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "client_cidr_block" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_servers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "server_certificate_arn" {
  description = "(required)"
  type        = string
}

variable "split_tunnel" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "transport_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authentication_options" {
  description = "nested mode: NestingList, min items: 1, max items: 2"
  type = set(object(
    {
      active_directory_id        = string
      root_certificate_chain_arn = string
      saml_provider_arn          = string
      type                       = string
    }
  ))
}

variable "connection_log_options" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cloudwatch_log_group  = string
      cloudwatch_log_stream = string
      enabled               = bool
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_ec2_client_vpn_endpoint" "this" {
  client_cidr_block      = var.client_cidr_block
  description            = var.description
  dns_servers            = var.dns_servers
  server_certificate_arn = var.server_certificate_arn
  split_tunnel           = var.split_tunnel
  tags                   = var.tags
  transport_protocol     = var.transport_protocol

  dynamic "authentication_options" {
    for_each = var.authentication_options
    content {
      active_directory_id        = authentication_options.value["active_directory_id"]
      root_certificate_chain_arn = authentication_options.value["root_certificate_chain_arn"]
      saml_provider_arn          = authentication_options.value["saml_provider_arn"]
      type                       = authentication_options.value["type"]
    }
  }

  dynamic "connection_log_options" {
    for_each = var.connection_log_options
    content {
      cloudwatch_log_group  = connection_log_options.value["cloudwatch_log_group"]
      cloudwatch_log_stream = connection_log_options.value["cloudwatch_log_stream"]
      enabled               = connection_log_options.value["enabled"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_endpoint.this.arn
}

output "dns_name" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_endpoint.this.dns_name
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_endpoint.this.id
}

output "status" {
  description = "returns a string"
  value       = aws_ec2_client_vpn_endpoint.this.status
}

output "this" {
  value = aws_ec2_client_vpn_endpoint.this
}
```

[top](#index)