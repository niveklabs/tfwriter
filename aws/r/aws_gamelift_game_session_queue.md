# aws_gamelift_game_session_queue
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
module "aws_gamelift_game_session_queue" {
  source = "./modules/aws/r/aws_gamelift_game_session_queue"

  # destinations - (optional) is a type of list of string
  destinations = []
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timeout_in_seconds - (optional) is a type of number
  timeout_in_seconds = null

  player_latency_policy = [{
    maximum_individual_player_latency_milliseconds = null
    policy_duration_seconds                        = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "destinations" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeout_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "player_latency_policy" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      maximum_individual_player_latency_milliseconds = number
      policy_duration_seconds                        = number
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_gamelift_game_session_queue" "this" {
  destinations       = var.destinations
  name               = var.name
  tags               = var.tags
  timeout_in_seconds = var.timeout_in_seconds

  dynamic "player_latency_policy" {
    for_each = var.player_latency_policy
    content {
      maximum_individual_player_latency_milliseconds = player_latency_policy.value["maximum_individual_player_latency_milliseconds"]
      policy_duration_seconds                        = player_latency_policy.value["policy_duration_seconds"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_gamelift_game_session_queue.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_gamelift_game_session_queue.this.id
}

output "this" {
  value = aws_gamelift_game_session_queue.this
}
```
[top](#index)
