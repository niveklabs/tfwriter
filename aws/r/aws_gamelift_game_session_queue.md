# aws_gamelift_game_session_queue

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

```terraform
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
  description = "nested block: NestingList, min items: 0, max items: 0"
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

```terraform
resource "aws_gamelift_game_session_queue" "this" {
  # destinations - (optional) is a type of list of string
  destinations = var.destinations
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # timeout_in_seconds - (optional) is a type of number
  timeout_in_seconds = var.timeout_in_seconds

  dynamic "player_latency_policy" {
    for_each = var.player_latency_policy
    content {
      # maximum_individual_player_latency_milliseconds - (required) is a type of number
      maximum_individual_player_latency_milliseconds = player_latency_policy.value["maximum_individual_player_latency_milliseconds"]
      # policy_duration_seconds - (optional) is a type of number
      policy_duration_seconds = player_latency_policy.value["policy_duration_seconds"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
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