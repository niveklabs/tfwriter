# circonus_overlay_set

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    circonus = ">= 0.11.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_overlay_set" {
  source = "./modules/circonus/r/circonus_overlay_set"

  # graph_cid - (required) is a type of string
  graph_cid = null
  # title - (required) is a type of string
  title = null

  overlays = [{
    data_opts = [{
      graph_title = null
      graph_uuid  = null
      x_shift     = null
    }]
    id = null
    ui_specs = [{
      decouple = null
      id       = null
      label    = null
      type     = null
      z        = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "graph_cid" {
  description = "(required)"
  type        = string
}

variable "title" {
  description = "(required)"
  type        = string
}

variable "overlays" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      data_opts = set(object(
        {
          graph_title = string
          graph_uuid  = string
          x_shift     = string
        }
      ))
      id = string
      ui_specs = set(object(
        {
          decouple = bool
          id       = string
          label    = string
          type     = string
          z        = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "circonus_overlay_set" "this" {
  graph_cid = var.graph_cid
  title     = var.title

  dynamic "overlays" {
    for_each = var.overlays
    content {
      id = overlays.value["id"]

      dynamic "data_opts" {
        for_each = overlays.value.data_opts
        content {
          graph_title = data_opts.value["graph_title"]
          graph_uuid  = data_opts.value["graph_uuid"]
          x_shift     = data_opts.value["x_shift"]
        }
      }

      dynamic "ui_specs" {
        for_each = overlays.value.ui_specs
        content {
          decouple = ui_specs.value["decouple"]
          id       = ui_specs.value["id"]
          label    = ui_specs.value["label"]
          type     = ui_specs.value["type"]
          z        = ui_specs.value["z"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = circonus_overlay_set.this.id
}

output "this" {
  value = circonus_overlay_set.this
}
```

[top](#index)