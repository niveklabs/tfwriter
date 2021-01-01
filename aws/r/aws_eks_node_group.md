# aws_eks_node_group

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
module "aws_eks_node_group" {
  source = "./modules/aws/r/aws_eks_node_group"

  # ami_type - (optional) is a type of string
  ami_type = null
  # capacity_type - (optional) is a type of string
  capacity_type = null
  # cluster_name - (required) is a type of string
  cluster_name = null
  # disk_size - (optional) is a type of number
  disk_size = null
  # force_update_version - (optional) is a type of bool
  force_update_version = null
  # instance_types - (optional) is a type of list of string
  instance_types = []
  # labels - (optional) is a type of map of string
  labels = {}
  # node_group_name - (required) is a type of string
  node_group_name = null
  # node_role_arn - (required) is a type of string
  node_role_arn = null
  # release_version - (optional) is a type of string
  release_version = null
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (optional) is a type of string
  version = null

  launch_template = [{
    id      = null
    name    = null
    version = null
  }]

  remote_access = [{
    ec2_ssh_key               = null
    source_security_group_ids = []
  }]

  scaling_config = [{
    desired_size = null
    max_size     = null
    min_size     = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "ami_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capacity_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "force_update_version" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "node_group_name" {
  description = "(required)"
  type        = string
}

variable "node_role_arn" {
  description = "(required)"
  type        = string
}

variable "release_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "launch_template" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id      = string
      name    = string
      version = string
    }
  ))
  default = []
}

variable "remote_access" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ec2_ssh_key               = string
      source_security_group_ids = set(string)
    }
  ))
  default = []
}

variable "scaling_config" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      desired_size = number
      max_size     = number
      min_size     = number
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_eks_node_group" "this" {
  ami_type             = var.ami_type
  capacity_type        = var.capacity_type
  cluster_name         = var.cluster_name
  disk_size            = var.disk_size
  force_update_version = var.force_update_version
  instance_types       = var.instance_types
  labels               = var.labels
  node_group_name      = var.node_group_name
  node_role_arn        = var.node_role_arn
  release_version      = var.release_version
  subnet_ids           = var.subnet_ids
  tags                 = var.tags
  version              = var.version

  dynamic "launch_template" {
    for_each = var.launch_template
    content {
      id      = launch_template.value["id"]
      name    = launch_template.value["name"]
      version = launch_template.value["version"]
    }
  }

  dynamic "remote_access" {
    for_each = var.remote_access
    content {
      ec2_ssh_key               = remote_access.value["ec2_ssh_key"]
      source_security_group_ids = remote_access.value["source_security_group_ids"]
    }
  }

  dynamic "scaling_config" {
    for_each = var.scaling_config
    content {
      desired_size = scaling_config.value["desired_size"]
      max_size     = scaling_config.value["max_size"]
      min_size     = scaling_config.value["min_size"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "ami_type" {
  description = "returns a string"
  value       = aws_eks_node_group.this.ami_type
}

output "arn" {
  description = "returns a string"
  value       = aws_eks_node_group.this.arn
}

output "capacity_type" {
  description = "returns a string"
  value       = aws_eks_node_group.this.capacity_type
}

output "disk_size" {
  description = "returns a number"
  value       = aws_eks_node_group.this.disk_size
}

output "id" {
  description = "returns a string"
  value       = aws_eks_node_group.this.id
}

output "instance_types" {
  description = "returns a list of string"
  value       = aws_eks_node_group.this.instance_types
}

output "release_version" {
  description = "returns a string"
  value       = aws_eks_node_group.this.release_version
}

output "resources" {
  description = "returns a list of object"
  value       = aws_eks_node_group.this.resources
}

output "status" {
  description = "returns a string"
  value       = aws_eks_node_group.this.status
}

output "version" {
  description = "returns a string"
  value       = aws_eks_node_group.this.version
}

output "this" {
  value = aws_eks_node_group.this
}
```

[top](#index)