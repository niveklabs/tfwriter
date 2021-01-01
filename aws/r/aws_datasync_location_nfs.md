# aws_datasync_location_nfs

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
module "aws_datasync_location_nfs" {
  source = "./modules/aws/r/aws_datasync_location_nfs"

  # server_hostname - (required) is a type of string
  server_hostname = null
  # subdirectory - (required) is a type of string
  subdirectory = null
  # tags - (optional) is a type of map of string
  tags = {}

  on_prem_config = [{
    agent_arns = []
  }]
}
```

[top](#index)

### Variables

```hcl
variable "server_hostname" {
  description = "(required)"
  type        = string
}

variable "subdirectory" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "on_prem_config" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      agent_arns = set(string)
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_datasync_location_nfs" "this" {
  server_hostname = var.server_hostname
  subdirectory    = var.subdirectory
  tags            = var.tags

  dynamic "on_prem_config" {
    for_each = var.on_prem_config
    content {
      agent_arns = on_prem_config.value["agent_arns"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_datasync_location_nfs.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_datasync_location_nfs.this.id
}

output "uri" {
  description = "returns a string"
  value       = aws_datasync_location_nfs.this.uri
}

output "this" {
  value = aws_datasync_location_nfs.this
}
```

[top](#index)