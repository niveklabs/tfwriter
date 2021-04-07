# circonus_graph

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
    circonus = ">= 0.12.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_graph" {
  source = "./modules/circonus/r/circonus_graph"

  # description - (optional) is a type of string
  description = null
  # graph_style - (optional) is a type of string
  graph_style = null
  # left - (optional) is a type of map of string
  left = {}
  # line_style - (optional) is a type of string
  line_style = null
  # name - (required) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # right - (optional) is a type of map of string
  right = {}
  # tags - (optional) is a type of set of string
  tags = []

  guide = [{
    color          = null
    formula        = null
    hidden         = null
    legend_formula = null
    name           = null
  }]

  metric = [{
    active         = null
    alpha          = null
    axis           = null
    caql           = null
    check          = null
    color          = null
    formula        = null
    function       = null
    legend_formula = null
    metric_name    = null
    metric_type    = null
    name           = null
    search         = null
    stack          = null
  }]

  metric_cluster = [{
    active    = null
    aggregate = null
    axis      = null
    color     = null
    name      = null
    query     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "graph_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "left" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "line_style" {
  description = "(optional) - How the line should change between point. A string containing either 'stepped', 'interpolated' or null."
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "right" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "guide" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      color          = string
      formula        = string
      hidden         = bool
      legend_formula = string
      name           = string
    }
  ))
  default = []
}

variable "metric" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      active         = bool
      alpha          = string
      axis           = string
      caql           = string
      check          = string
      color          = string
      formula        = string
      function       = string
      legend_formula = string
      metric_name    = string
      metric_type    = string
      name           = string
      search         = string
      stack          = string
    }
  ))
  default = []
}

variable "metric_cluster" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      active    = bool
      aggregate = string
      axis      = string
      color     = string
      name      = string
      query     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "circonus_graph" "this" {
  # description - (optional) is a type of string
  description = var.description
  # graph_style - (optional) is a type of string
  graph_style = var.graph_style
  # left - (optional) is a type of map of string
  left = var.left
  # line_style - (optional) is a type of string
  line_style = var.line_style
  # name - (required) is a type of string
  name = var.name
  # notes - (optional) is a type of string
  notes = var.notes
  # right - (optional) is a type of map of string
  right = var.right
  # tags - (optional) is a type of set of string
  tags = var.tags

  dynamic "guide" {
    for_each = var.guide
    content {
      # color - (optional) is a type of string
      color = guide.value["color"]
      # formula - (optional) is a type of string
      formula = guide.value["formula"]
      # hidden - (optional) is a type of bool
      hidden = guide.value["hidden"]
      # legend_formula - (optional) is a type of string
      legend_formula = guide.value["legend_formula"]
      # name - (optional) is a type of string
      name = guide.value["name"]
    }
  }

  dynamic "metric" {
    for_each = var.metric
    content {
      # active - (optional) is a type of bool
      active = metric.value["active"]
      # alpha - (optional) is a type of string
      alpha = metric.value["alpha"]
      # axis - (optional) is a type of string
      axis = metric.value["axis"]
      # caql - (optional) is a type of string
      caql = metric.value["caql"]
      # check - (optional) is a type of string
      check = metric.value["check"]
      # color - (optional) is a type of string
      color = metric.value["color"]
      # formula - (optional) is a type of string
      formula = metric.value["formula"]
      # function - (optional) is a type of string
      function = metric.value["function"]
      # legend_formula - (optional) is a type of string
      legend_formula = metric.value["legend_formula"]
      # metric_name - (optional) is a type of string
      metric_name = metric.value["metric_name"]
      # metric_type - (required) is a type of string
      metric_type = metric.value["metric_type"]
      # name - (optional) is a type of string
      name = metric.value["name"]
      # search - (optional) is a type of string
      search = metric.value["search"]
      # stack - (optional) is a type of string
      stack = metric.value["stack"]
    }
  }

  dynamic "metric_cluster" {
    for_each = var.metric_cluster
    content {
      # active - (optional) is a type of bool
      active = metric_cluster.value["active"]
      # aggregate - (optional) is a type of string
      aggregate = metric_cluster.value["aggregate"]
      # axis - (optional) is a type of string
      axis = metric_cluster.value["axis"]
      # color - (optional) is a type of string
      color = metric_cluster.value["color"]
      # name - (required) is a type of string
      name = metric_cluster.value["name"]
      # query - (optional) is a type of string
      query = metric_cluster.value["query"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = circonus_graph.this.id
}

output "this" {
  value = circonus_graph.this
}
```

[top](#index)