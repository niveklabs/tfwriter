# aws_elastic_beanstalk_environment

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
module "aws_elastic_beanstalk_environment" {
  source = "./modules/aws/r/aws_elastic_beanstalk_environment"

  # application - (required) is a type of string
  application = null
  # cname_prefix - (optional) is a type of string
  cname_prefix = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # platform_arn - (optional) is a type of string
  platform_arn = null
  # poll_interval - (optional) is a type of string
  poll_interval = null
  # solution_stack_name - (optional) is a type of string
  solution_stack_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_name - (optional) is a type of string
  template_name = null
  # tier - (optional) is a type of string
  tier = null
  # version_label - (optional) is a type of string
  version_label = null
  # wait_for_ready_timeout - (optional) is a type of string
  wait_for_ready_timeout = null

  setting = [{
    name      = null
    namespace = null
    resource  = null
    value     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application" {
  description = "(required)"
  type        = string
}

variable "cname_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "platform_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "poll_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "solution_stack_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wait_for_ready_timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "setting" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name      = string
      namespace = string
      resource  = string
      value     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_elastic_beanstalk_environment" "this" {
  application            = var.application
  cname_prefix           = var.cname_prefix
  description            = var.description
  name                   = var.name
  platform_arn           = var.platform_arn
  poll_interval          = var.poll_interval
  solution_stack_name    = var.solution_stack_name
  tags                   = var.tags
  template_name          = var.template_name
  tier                   = var.tier
  version_label          = var.version_label
  wait_for_ready_timeout = var.wait_for_ready_timeout

  dynamic "setting" {
    for_each = var.setting
    content {
      name      = setting.value["name"]
      namespace = setting.value["namespace"]
      resource  = setting.value["resource"]
      value     = setting.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "all_settings" {
  description = "returns a set of object"
  value       = aws_elastic_beanstalk_environment.this.all_settings
}

output "arn" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_environment.this.arn
}

output "autoscaling_groups" {
  description = "returns a list of string"
  value       = aws_elastic_beanstalk_environment.this.autoscaling_groups
}

output "cname" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_environment.this.cname
}

output "cname_prefix" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_environment.this.cname_prefix
}

output "endpoint_url" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_environment.this.endpoint_url
}

output "id" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_environment.this.id
}

output "instances" {
  description = "returns a list of string"
  value       = aws_elastic_beanstalk_environment.this.instances
}

output "launch_configurations" {
  description = "returns a list of string"
  value       = aws_elastic_beanstalk_environment.this.launch_configurations
}

output "load_balancers" {
  description = "returns a list of string"
  value       = aws_elastic_beanstalk_environment.this.load_balancers
}

output "platform_arn" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_environment.this.platform_arn
}

output "queues" {
  description = "returns a list of string"
  value       = aws_elastic_beanstalk_environment.this.queues
}

output "solution_stack_name" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_environment.this.solution_stack_name
}

output "triggers" {
  description = "returns a list of string"
  value       = aws_elastic_beanstalk_environment.this.triggers
}

output "version_label" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_environment.this.version_label
}

output "this" {
  value = aws_elastic_beanstalk_environment.this
}
```

[top](#index)