# aws_instance

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_instance" {
  source = "./modules/aws/d/aws_instance"

  # get_password_data - (optional) is a type of bool
  get_password_data = null
  # get_user_data - (optional) is a type of bool
  get_user_data = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # instance_tags - (optional) is a type of map of string
  instance_tags = {}
  # tags - (optional) is a type of map of string
  tags = {}

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```hcl
variable "get_password_data" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "get_user_data" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```hcl
data "aws_instance" "this" {
  get_password_data = var.get_password_data
  get_user_data     = var.get_user_data
  instance_id       = var.instance_id
  instance_tags     = var.instance_tags
  tags              = var.tags

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "ami" {
  description = "returns a string"
  value       = data.aws_instance.this.ami
}

output "arn" {
  description = "returns a string"
  value       = data.aws_instance.this.arn
}

output "associate_public_ip_address" {
  description = "returns a bool"
  value       = data.aws_instance.this.associate_public_ip_address
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_instance.this.availability_zone
}

output "credit_specification" {
  description = "returns a list of object"
  value       = data.aws_instance.this.credit_specification
}

output "disable_api_termination" {
  description = "returns a bool"
  value       = data.aws_instance.this.disable_api_termination
}

output "ebs_block_device" {
  description = "returns a set of object"
  value       = data.aws_instance.this.ebs_block_device
}

output "ebs_optimized" {
  description = "returns a bool"
  value       = data.aws_instance.this.ebs_optimized
}

output "enclave_options" {
  description = "returns a list of object"
  value       = data.aws_instance.this.enclave_options
}

output "ephemeral_block_device" {
  description = "returns a list of object"
  value       = data.aws_instance.this.ephemeral_block_device
}

output "host_id" {
  description = "returns a string"
  value       = data.aws_instance.this.host_id
}

output "iam_instance_profile" {
  description = "returns a string"
  value       = data.aws_instance.this.iam_instance_profile
}

output "id" {
  description = "returns a string"
  value       = data.aws_instance.this.id
}

output "instance_state" {
  description = "returns a string"
  value       = data.aws_instance.this.instance_state
}

output "instance_tags" {
  description = "returns a map of string"
  value       = data.aws_instance.this.instance_tags
}

output "instance_type" {
  description = "returns a string"
  value       = data.aws_instance.this.instance_type
}

output "key_name" {
  description = "returns a string"
  value       = data.aws_instance.this.key_name
}

output "metadata_options" {
  description = "returns a list of object"
  value       = data.aws_instance.this.metadata_options
}

output "monitoring" {
  description = "returns a bool"
  value       = data.aws_instance.this.monitoring
}

output "network_interface_id" {
  description = "returns a string"
  value       = data.aws_instance.this.network_interface_id
}

output "outpost_arn" {
  description = "returns a string"
  value       = data.aws_instance.this.outpost_arn
}

output "password_data" {
  description = "returns a string"
  value       = data.aws_instance.this.password_data
}

output "placement_group" {
  description = "returns a string"
  value       = data.aws_instance.this.placement_group
}

output "private_dns" {
  description = "returns a string"
  value       = data.aws_instance.this.private_dns
}

output "private_ip" {
  description = "returns a string"
  value       = data.aws_instance.this.private_ip
}

output "public_dns" {
  description = "returns a string"
  value       = data.aws_instance.this.public_dns
}

output "public_ip" {
  description = "returns a string"
  value       = data.aws_instance.this.public_ip
}

output "root_block_device" {
  description = "returns a set of object"
  value       = data.aws_instance.this.root_block_device
}

output "secondary_private_ips" {
  description = "returns a set of string"
  value       = data.aws_instance.this.secondary_private_ips
}

output "security_groups" {
  description = "returns a set of string"
  value       = data.aws_instance.this.security_groups
}

output "source_dest_check" {
  description = "returns a bool"
  value       = data.aws_instance.this.source_dest_check
}

output "subnet_id" {
  description = "returns a string"
  value       = data.aws_instance.this.subnet_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_instance.this.tags
}

output "tenancy" {
  description = "returns a string"
  value       = data.aws_instance.this.tenancy
}

output "user_data" {
  description = "returns a string"
  value       = data.aws_instance.this.user_data
}

output "user_data_base64" {
  description = "returns a string"
  value       = data.aws_instance.this.user_data_base64
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = data.aws_instance.this.vpc_security_group_ids
}

output "this" {
  value = aws_instance.this
}
```

[top](#index)