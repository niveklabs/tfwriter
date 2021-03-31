# alicloud_edas_instance_cluster_attachment

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_edas_instance_cluster_attachment" {
  source = "./modules/alicloud/r/alicloud_edas_instance_cluster_attachment"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # instance_ids - (required) is a type of list of string
  instance_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "instance_ids" {
  description = "(required)"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_instance_cluster_attachment" "this" {
  cluster_id   = var.cluster_id
  instance_ids = var.instance_ids
}
```

[top](#index)

### Outputs

```terraform
output "cluster_member_ids" {
  description = "returns a map of string"
  value       = alicloud_edas_instance_cluster_attachment.this.cluster_member_ids
}

output "ecu_map" {
  description = "returns a map of string"
  value       = alicloud_edas_instance_cluster_attachment.this.ecu_map
}

output "id" {
  description = "returns a string"
  value       = alicloud_edas_instance_cluster_attachment.this.id
}

output "status_map" {
  description = "returns a map of number"
  value       = alicloud_edas_instance_cluster_attachment.this.status_map
}

output "this" {
  value = alicloud_edas_instance_cluster_attachment.this
}
```

[top](#index)