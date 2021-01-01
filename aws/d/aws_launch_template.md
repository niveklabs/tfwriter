# aws_launch_template
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
module "aws_launch_template" {
  source = "./modules/aws/d/aws_launch_template"

  # name - (optional) is a type of string
  name = null
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
variable "name" {
  description = "(optional)"
  type        = string
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
data "aws_launch_template" "this" {
  name = var.name
  tags = var.tags

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
output "arn" {
  description = "returns a string"
  value       = data.aws_launch_template.this.arn
}

output "block_device_mappings" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.block_device_mappings
}

output "credit_specification" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.credit_specification
}

output "default_version" {
  description = "returns a number"
  value       = data.aws_launch_template.this.default_version
}

output "description" {
  description = "returns a string"
  value       = data.aws_launch_template.this.description
}

output "disable_api_termination" {
  description = "returns a bool"
  value       = data.aws_launch_template.this.disable_api_termination
}

output "ebs_optimized" {
  description = "returns a string"
  value       = data.aws_launch_template.this.ebs_optimized
}

output "elastic_gpu_specifications" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.elastic_gpu_specifications
}

output "enclave_options" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.enclave_options
}

output "hibernation_options" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.hibernation_options
}

output "iam_instance_profile" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.iam_instance_profile
}

output "id" {
  description = "returns a string"
  value       = data.aws_launch_template.this.id
}

output "image_id" {
  description = "returns a string"
  value       = data.aws_launch_template.this.image_id
}

output "instance_initiated_shutdown_behavior" {
  description = "returns a string"
  value       = data.aws_launch_template.this.instance_initiated_shutdown_behavior
}

output "instance_market_options" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.instance_market_options
}

output "instance_type" {
  description = "returns a string"
  value       = data.aws_launch_template.this.instance_type
}

output "kernel_id" {
  description = "returns a string"
  value       = data.aws_launch_template.this.kernel_id
}

output "key_name" {
  description = "returns a string"
  value       = data.aws_launch_template.this.key_name
}

output "latest_version" {
  description = "returns a number"
  value       = data.aws_launch_template.this.latest_version
}

output "metadata_options" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.metadata_options
}

output "monitoring" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.monitoring
}

output "network_interfaces" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.network_interfaces
}

output "placement" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.placement
}

output "ram_disk_id" {
  description = "returns a string"
  value       = data.aws_launch_template.this.ram_disk_id
}

output "security_group_names" {
  description = "returns a set of string"
  value       = data.aws_launch_template.this.security_group_names
}

output "tag_specifications" {
  description = "returns a list of object"
  value       = data.aws_launch_template.this.tag_specifications
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_launch_template.this.tags
}

output "user_data" {
  description = "returns a string"
  value       = data.aws_launch_template.this.user_data
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = data.aws_launch_template.this.vpc_security_group_ids
}

output "this" {
  value = aws_launch_template.this
}
```
[top](#index)
