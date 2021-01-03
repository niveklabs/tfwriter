# oci_core_peer_region_for_remote_peerings

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_peer_region_for_remote_peerings" {
  source = "./modules/oci/d/oci_core_peer_region_for_remote_peerings"


  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_peer_region_for_remote_peerings" "this" {

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_core_peer_region_for_remote_peerings.this.id
}

output "peer_region_for_remote_peerings" {
  description = "returns a list of object"
  value       = data.oci_core_peer_region_for_remote_peerings.this.peer_region_for_remote_peerings
}

output "this" {
  value = oci_core_peer_region_for_remote_peerings.this
}
```

[top](#index)