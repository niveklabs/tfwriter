# linode_object_storage_bucket

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.13.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_object_storage_bucket" {
  source = "./modules/linode/r/linode_object_storage_bucket"

  # cluster - (required) is a type of string
  cluster = null
  # label - (required) is a type of string
  label = null

  cert = [{
    certificate = null
    private_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster" {
  description = "(required) - The cluster of the Linode Object Storage Bucket."
  type        = string
}

variable "label" {
  description = "(required) - The label of the Linode Object Storage Bucket."
  type        = string
}

variable "cert" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate = string
      private_key = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "linode_object_storage_bucket" "this" {
  cluster = var.cluster
  label   = var.label

  dynamic "cert" {
    for_each = var.cert
    content {
      certificate = cert.value["certificate"]
      private_key = cert.value["private_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = linode_object_storage_bucket.this.id
}

output "this" {
  value = linode_object_storage_bucket.this
}
```

[top](#index)