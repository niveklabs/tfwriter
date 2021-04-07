# oci_network_load_balancer_network_load_balancers_policies

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_network_load_balancer_network_load_balancers_policies" {
  source = "./modules/oci/d/oci_network_load_balancer_network_load_balancers_policies"


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
data "oci_network_load_balancer_network_load_balancers_policies" "this" {

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
  value       = data.oci_network_load_balancer_network_load_balancers_policies.this.id
}

output "network_load_balancers_policy_collection" {
  description = "returns a list of object"
  value       = data.oci_network_load_balancer_network_load_balancers_policies.this.network_load_balancers_policy_collection
}

output "this" {
  value = oci_network_load_balancer_network_load_balancers_policies.this
}
```

[top](#index)