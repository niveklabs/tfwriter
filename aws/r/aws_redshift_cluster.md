# aws_redshift_cluster

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_redshift_cluster" {
  source = "./modules/aws/r/aws_redshift_cluster"

  # allow_version_upgrade - (optional) is a type of bool
  allow_version_upgrade = null
  # automated_snapshot_retention_period - (optional) is a type of number
  automated_snapshot_retention_period = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cluster_identifier - (required) is a type of string
  cluster_identifier = null
  # cluster_parameter_group_name - (optional) is a type of string
  cluster_parameter_group_name = null
  # cluster_public_key - (optional) is a type of string
  cluster_public_key = null
  # cluster_revision_number - (optional) is a type of string
  cluster_revision_number = null
  # cluster_security_groups - (optional) is a type of set of string
  cluster_security_groups = []
  # cluster_subnet_group_name - (optional) is a type of string
  cluster_subnet_group_name = null
  # cluster_type - (optional) is a type of string
  cluster_type = null
  # cluster_version - (optional) is a type of string
  cluster_version = null
  # database_name - (optional) is a type of string
  database_name = null
  # elastic_ip - (optional) is a type of string
  elastic_ip = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # enhanced_vpc_routing - (optional) is a type of bool
  enhanced_vpc_routing = null
  # final_snapshot_identifier - (optional) is a type of string
  final_snapshot_identifier = null
  # iam_roles - (optional) is a type of set of string
  iam_roles = []
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # master_password - (optional) is a type of string
  master_password = null
  # master_username - (optional) is a type of string
  master_username = null
  # node_type - (required) is a type of string
  node_type = null
  # number_of_nodes - (optional) is a type of number
  number_of_nodes = null
  # owner_account - (optional) is a type of string
  owner_account = null
  # port - (optional) is a type of number
  port = null
  # preferred_maintenance_window - (optional) is a type of string
  preferred_maintenance_window = null
  # publicly_accessible - (optional) is a type of bool
  publicly_accessible = null
  # skip_final_snapshot - (optional) is a type of bool
  skip_final_snapshot = null
  # snapshot_cluster_identifier - (optional) is a type of string
  snapshot_cluster_identifier = null
  # snapshot_identifier - (optional) is a type of string
  snapshot_identifier = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = []

  logging = [{
    bucket_name   = null
    enable        = null
    s3_key_prefix = null
  }]

  snapshot_copy = [{
    destination_region = null
    grant_name         = null
    retention_period   = null
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

```terraform
variable "allow_version_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "automated_snapshot_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_identifier" {
  description = "(required)"
  type        = string
}

variable "cluster_parameter_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_public_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_revision_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cluster_subnet_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "elastic_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enhanced_vpc_routing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "final_snapshot_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_roles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_type" {
  description = "(required)"
  type        = string
}

variable "number_of_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "owner_account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preferred_maintenance_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publicly_accessible" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "skip_final_snapshot" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "snapshot_cluster_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "logging" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_name   = string
      enable        = bool
      s3_key_prefix = string
    }
  ))
  default = []
}

variable "snapshot_copy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      destination_region = string
      grant_name         = string
      retention_period   = number
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
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

```terraform
resource "aws_redshift_cluster" "this" {
  allow_version_upgrade               = var.allow_version_upgrade
  automated_snapshot_retention_period = var.automated_snapshot_retention_period
  availability_zone                   = var.availability_zone
  cluster_identifier                  = var.cluster_identifier
  cluster_parameter_group_name        = var.cluster_parameter_group_name
  cluster_public_key                  = var.cluster_public_key
  cluster_revision_number             = var.cluster_revision_number
  cluster_security_groups             = var.cluster_security_groups
  cluster_subnet_group_name           = var.cluster_subnet_group_name
  cluster_type                        = var.cluster_type
  cluster_version                     = var.cluster_version
  database_name                       = var.database_name
  elastic_ip                          = var.elastic_ip
  encrypted                           = var.encrypted
  endpoint                            = var.endpoint
  enhanced_vpc_routing                = var.enhanced_vpc_routing
  final_snapshot_identifier           = var.final_snapshot_identifier
  iam_roles                           = var.iam_roles
  kms_key_id                          = var.kms_key_id
  master_password                     = var.master_password
  master_username                     = var.master_username
  node_type                           = var.node_type
  number_of_nodes                     = var.number_of_nodes
  owner_account                       = var.owner_account
  port                                = var.port
  preferred_maintenance_window        = var.preferred_maintenance_window
  publicly_accessible                 = var.publicly_accessible
  skip_final_snapshot                 = var.skip_final_snapshot
  snapshot_cluster_identifier         = var.snapshot_cluster_identifier
  snapshot_identifier                 = var.snapshot_identifier
  tags                                = var.tags
  vpc_security_group_ids              = var.vpc_security_group_ids

  dynamic "logging" {
    for_each = var.logging
    content {
      bucket_name   = logging.value["bucket_name"]
      enable        = logging.value["enable"]
      s3_key_prefix = logging.value["s3_key_prefix"]
    }
  }

  dynamic "snapshot_copy" {
    for_each = var.snapshot_copy
    content {
      destination_region = snapshot_copy.value["destination_region"]
      grant_name         = snapshot_copy.value["grant_name"]
      retention_period   = snapshot_copy.value["retention_period"]
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

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.availability_zone
}

output "cluster_parameter_group_name" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.cluster_parameter_group_name
}

output "cluster_public_key" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.cluster_public_key
}

output "cluster_revision_number" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.cluster_revision_number
}

output "cluster_security_groups" {
  description = "returns a set of string"
  value       = aws_redshift_cluster.this.cluster_security_groups
}

output "cluster_subnet_group_name" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.cluster_subnet_group_name
}

output "cluster_type" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.cluster_type
}

output "database_name" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.database_name
}

output "dns_name" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.dns_name
}

output "endpoint" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.endpoint
}

output "enhanced_vpc_routing" {
  description = "returns a bool"
  value       = aws_redshift_cluster.this.enhanced_vpc_routing
}

output "iam_roles" {
  description = "returns a set of string"
  value       = aws_redshift_cluster.this.iam_roles
}

output "id" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.kms_key_id
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = aws_redshift_cluster.this.preferred_maintenance_window
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = aws_redshift_cluster.this.vpc_security_group_ids
}

output "this" {
  value = aws_redshift_cluster.this
}
```

[top](#index)