# aws_transfer_server

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
module "aws_transfer_server" {
  source = "./modules/aws/r/aws_transfer_server"

  # endpoint_type - (optional) is a type of string
  endpoint_type = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # host_key - (optional) is a type of string
  host_key = null
  # identity_provider_type - (optional) is a type of string
  identity_provider_type = null
  # invocation_role - (optional) is a type of string
  invocation_role = null
  # logging_role - (optional) is a type of string
  logging_role = null
  # tags - (optional) is a type of map of string
  tags = {}
  # url - (optional) is a type of string
  url = null

  endpoint_details = [{
    address_allocation_ids = []
    subnet_ids             = []
    vpc_endpoint_id        = null
    vpc_id                 = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "endpoint_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "host_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_provider_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "invocation_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logging_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endpoint_details" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address_allocation_ids = set(string)
      subnet_ids             = set(string)
      vpc_endpoint_id        = string
      vpc_id                 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_transfer_server" "this" {
  endpoint_type          = var.endpoint_type
  force_destroy          = var.force_destroy
  host_key               = var.host_key
  identity_provider_type = var.identity_provider_type
  invocation_role        = var.invocation_role
  logging_role           = var.logging_role
  tags                   = var.tags
  url                    = var.url

  dynamic "endpoint_details" {
    for_each = var.endpoint_details
    content {
      address_allocation_ids = endpoint_details.value["address_allocation_ids"]
      subnet_ids             = endpoint_details.value["subnet_ids"]
      vpc_endpoint_id        = endpoint_details.value["vpc_endpoint_id"]
      vpc_id                 = endpoint_details.value["vpc_id"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_transfer_server.this.arn
}

output "endpoint" {
  description = "returns a string"
  value       = aws_transfer_server.this.endpoint
}

output "host_key_fingerprint" {
  description = "returns a string"
  value       = aws_transfer_server.this.host_key_fingerprint
}

output "id" {
  description = "returns a string"
  value       = aws_transfer_server.this.id
}

output "this" {
  value = aws_transfer_server.this
}
```

[top](#index)