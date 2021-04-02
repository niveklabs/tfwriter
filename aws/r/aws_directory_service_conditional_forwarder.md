# aws_directory_service_conditional_forwarder

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_directory_service_conditional_forwarder" {
  source = "./modules/aws/r/aws_directory_service_conditional_forwarder"

  # directory_id - (required) is a type of string
  directory_id = null
  # dns_ips - (required) is a type of list of string
  dns_ips = []
  # remote_domain_name - (required) is a type of string
  remote_domain_name = null
}
```

[top](#index)

### Variables

```terraform
variable "directory_id" {
  description = "(required)"
  type        = string
}

variable "dns_ips" {
  description = "(required)"
  type        = list(string)
}

variable "remote_domain_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_directory_service_conditional_forwarder" "this" {
  directory_id       = var.directory_id
  dns_ips            = var.dns_ips
  remote_domain_name = var.remote_domain_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_directory_service_conditional_forwarder.this.id
}

output "this" {
  value = aws_directory_service_conditional_forwarder.this
}
```

[top](#index)