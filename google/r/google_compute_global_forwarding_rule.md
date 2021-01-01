# google_compute_global_forwarding_rule

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_compute_global_forwarding_rule" {
  source = "./modules/google/r/google_compute_global_forwarding_rule"

  # description - (optional) is a type of string
  description = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # load_balancing_scheme - (optional) is a type of string
  load_balancing_scheme = null
  # name - (required) is a type of string
  name = null
  # port_range - (optional) is a type of string
  port_range = null
  # project - (optional) is a type of string
  project = null
  # target - (required) is a type of string
  target = null

  metadata_filters = [{
    filter_labels = [{
      name  = null
      value = null
    }]
    filter_match_criteria = null
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
variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource."
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional) - The IP address that this forwarding rule is serving on behalf of.\n\nAddresses are restricted based on the forwarding rule's load balancing\nscheme (EXTERNAL or INTERNAL) and scope (global or regional).\n\nWhen the load balancing scheme is EXTERNAL, for global forwarding\nrules, the address must be a global IP, and for regional forwarding\nrules, the address must live in the same region as the forwarding\nrule. If this field is empty, an ephemeral IPv4 address from the same\nscope (global or regional) will be assigned. A regional forwarding\nrule supports IPv4 only. A global forwarding rule supports either IPv4\nor IPv6.\n\nWhen the load balancing scheme is INTERNAL, this can only be an RFC\n1918 IP address belonging to the network/subnet configured for the\nforwarding rule. By default, if this field is empty, an ephemeral\ninternal IP address will be automatically allocated from the IP range\nof the subnet or network configured for this forwarding rule.\n\nAn address must be specified by a literal IP address. ~> **NOTE**: While\nthe API allows you to specify various resource paths for an address resource\ninstead, Terraform requires this to specifically be an IP address to\navoid needing to fetching the IP address from resource paths on refresh\nor unnecessary diffs."
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(optional) - The IP protocol to which this rule applies. When the load balancing scheme is\nINTERNAL_SELF_MANAGED, only TCP is valid. Possible values: [\"TCP\", \"UDP\", \"ESP\", \"AH\", \"SCTP\", \"ICMP\"]"
  type        = string
  default     = null
}

variable "ip_version" {
  description = "(optional) - The IP Version that will be used by this global forwarding rule. Possible values: [\"IPV4\", \"IPV6\"]"
  type        = string
  default     = null
}

variable "load_balancing_scheme" {
  description = "(optional) - This signifies what the GlobalForwardingRule will be used for.\nThe value of INTERNAL_SELF_MANAGED means that this will be used for\nInternal Global HTTP(S) LB. The value of EXTERNAL means that this\nwill be used for External Global Load Balancing (HTTP(S) LB,\nExternal TCP/UDP LB, SSL Proxy)\n\nNOTE: Currently global forwarding rules cannot be used for INTERNAL\nload balancing. Default value: \"EXTERNAL\" Possible values: [\"EXTERNAL\", \"INTERNAL_SELF_MANAGED\"]"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource; provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "port_range" {
  description = "(optional) - This field is used along with the target field for TargetHttpProxy,\nTargetHttpsProxy, TargetSslProxy, TargetTcpProxy, TargetVpnGateway,\nTargetPool, TargetInstance.\n\nApplicable only when IPProtocol is TCP, UDP, or SCTP, only packets\naddressed to ports in the specified range will be forwarded to target.\nForwarding rules with the same [IPAddress, IPProtocol] pair must have\ndisjoint port ranges.\n\nSome types of forwarding target have constraints on the acceptable\nports:\n\n* TargetHttpProxy: 80, 8080\n* TargetHttpsProxy: 443\n* TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995,\n                  1883, 5222\n* TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995,\n                  1883, 5222\n* TargetVpnGateway: 500, 4500"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target" {
  description = "(required) - The URL of the target resource to receive the matched traffic.\nThe forwarded traffic must be of a type appropriate to the target object.\nFor INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets\nare valid."
  type        = string
}

variable "metadata_filters" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      filter_labels = list(object(
        {
          name  = string
          value = string
        }
      ))
      filter_match_criteria = string
    }
  ))
  default = []
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
resource "google_compute_global_forwarding_rule" "this" {
  description           = var.description
  ip_address            = var.ip_address
  ip_protocol           = var.ip_protocol
  ip_version            = var.ip_version
  load_balancing_scheme = var.load_balancing_scheme
  name                  = var.name
  port_range            = var.port_range
  project               = var.project
  target                = var.target

  dynamic "metadata_filters" {
    for_each = var.metadata_filters
    content {
      filter_match_criteria = metadata_filters.value["filter_match_criteria"]

      dynamic "filter_labels" {
        for_each = metadata_filters.value.filter_labels
        content {
          name  = filter_labels.value["name"]
          value = filter_labels.value["value"]
        }
      }

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
output "id" {
  description = "returns a string"
  value       = google_compute_global_forwarding_rule.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = google_compute_global_forwarding_rule.this.ip_address
}

output "ip_protocol" {
  description = "returns a string"
  value       = google_compute_global_forwarding_rule.this.ip_protocol
}

output "project" {
  description = "returns a string"
  value       = google_compute_global_forwarding_rule.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_global_forwarding_rule.this.self_link
}

output "this" {
  value = google_compute_global_forwarding_rule.this
}
```

[top](#index)