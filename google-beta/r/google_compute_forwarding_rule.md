# google_compute_forwarding_rule

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_forwarding_rule" {
  source = "./modules/google-beta/r/google_compute_forwarding_rule"

  # all_ports - (optional) is a type of bool
  all_ports = null
  # allow_global_access - (optional) is a type of bool
  allow_global_access = null
  # backend_service - (optional) is a type of string
  backend_service = null
  # description - (optional) is a type of string
  description = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # is_mirroring_collector - (optional) is a type of bool
  is_mirroring_collector = null
  # labels - (optional) is a type of map of string
  labels = {}
  # load_balancing_scheme - (optional) is a type of string
  load_balancing_scheme = null
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # network_tier - (optional) is a type of string
  network_tier = null
  # port_range - (optional) is a type of string
  port_range = null
  # ports - (optional) is a type of set of string
  ports = []
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # service_label - (optional) is a type of string
  service_label = null
  # subnetwork - (optional) is a type of string
  subnetwork = null
  # target - (optional) is a type of string
  target = null

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
variable "all_ports" {
  description = "(optional) - For internal TCP/UDP load balancing (i.e. load balancing scheme is\nINTERNAL and protocol is TCP/UDP), set this to true to allow packets\naddressed to any ports to be forwarded to the backends configured\nwith this forwarding rule. Used with backend service. Cannot be set\nif port or portRange are set."
  type        = bool
  default     = null
}

variable "allow_global_access" {
  description = "(optional) - If true, clients can access ILB from all regions.\nOtherwise only allows from the local region the ILB is located at."
  type        = bool
  default     = null
}

variable "backend_service" {
  description = "(optional) - A BackendService to receive the matched traffic. This is used only\nfor INTERNAL load balancing."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource."
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional) - The IP address that this forwarding rule is serving on behalf of.\n\nAddresses are restricted based on the forwarding rule's load balancing\nscheme (EXTERNAL or INTERNAL) and scope (global or regional).\n\nWhen the load balancing scheme is EXTERNAL, for global forwarding\nrules, the address must be a global IP, and for regional forwarding\nrules, the address must live in the same region as the forwarding\nrule. If this field is empty, an ephemeral IPv4 address from the same\nscope (global or regional) will be assigned. A regional forwarding\nrule supports IPv4 only. A global forwarding rule supports either IPv4\nor IPv6.\n\nWhen the load balancing scheme is INTERNAL, this can only be an RFC\n1918 IP address belonging to the network/subnet configured for the\nforwarding rule. By default, if this field is empty, an ephemeral\ninternal IP address will be automatically allocated from the IP range\nof the subnet or network configured for this forwarding rule.\n\nAn address must be specified by a literal IP address. ~> **NOTE:** While\nthe API allows you to specify various resource paths for an address resource\ninstead, Terraform requires this to specifically be an IP address to\navoid needing to fetching the IP address from resource paths on refresh\nor unnecessary diffs."
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(optional) - The IP protocol to which this rule applies.\n\nWhen the load balancing scheme is INTERNAL, only TCP and UDP are\nvalid. Possible values: [\"TCP\", \"UDP\", \"ESP\", \"AH\", \"SCTP\", \"ICMP\"]"
  type        = string
  default     = null
}

variable "is_mirroring_collector" {
  description = "(optional) - Indicates whether or not this load balancer can be used\nas a collector for packet mirroring. To prevent mirroring loops,\ninstances behind this load balancer will not have their traffic\nmirrored even if a PacketMirroring rule applies to them. This\ncan only be set to true for load balancers that have their\nloadBalancingScheme set to INTERNAL."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this forwarding rule.  A list of key->value pairs."
  type        = map(string)
  default     = null
}

variable "load_balancing_scheme" {
  description = "(optional) - This signifies what the ForwardingRule will be used for and can be\nEXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is used for Classic\nCloud VPN gateways, protocol forwarding to VMs from an external IP address,\nand HTTP(S), SSL Proxy, TCP Proxy, and Network TCP/UDP load balancers.\nINTERNAL is used for protocol forwarding to VMs from an internal IP address,\nand internal TCP/UDP load balancers.\nINTERNAL_MANAGED is used for internal HTTP(S) load balancers. Default value: \"EXTERNAL\" Possible values: [\"EXTERNAL\", \"INTERNAL\", \"INTERNAL_MANAGED\"]"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource; provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "network" {
  description = "(optional) - For internal load balancing, this field identifies the network that\nthe load balanced IP should belong to for this Forwarding Rule. If\nthis field is not specified, the default network will be used.\nThis field is only used for INTERNAL load balancing."
  type        = string
  default     = null
}

variable "network_tier" {
  description = "(optional) - The networking tier used for configuring this address. If this field is not\nspecified, it is assumed to be PREMIUM. Possible values: [\"PREMIUM\", \"STANDARD\"]"
  type        = string
  default     = null
}

variable "port_range" {
  description = "(optional) - This field is used along with the target field for TargetHttpProxy,\nTargetHttpsProxy, TargetSslProxy, TargetTcpProxy, TargetVpnGateway,\nTargetPool, TargetInstance.\n\nApplicable only when IPProtocol is TCP, UDP, or SCTP, only packets\naddressed to ports in the specified range will be forwarded to target.\nForwarding rules with the same [IPAddress, IPProtocol] pair must have\ndisjoint port ranges.\n\nSome types of forwarding target have constraints on the acceptable\nports:\n\n* TargetHttpProxy: 80, 8080\n* TargetHttpsProxy: 443\n* TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995,\n                  1883, 5222\n* TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995,\n                  1883, 5222\n* TargetVpnGateway: 500, 4500"
  type        = string
  default     = null
}

variable "ports" {
  description = "(optional) - This field is used along with the backend_service field for internal\nload balancing.\n\nWhen the load balancing scheme is INTERNAL, a single port or a comma\nseparated list of ports can be configured. Only packets addressed to\nthese ports will be forwarded to the backends configured with this\nforwarding rule.\n\nYou may specify a maximum of up to 5 ports."
  type        = set(string)
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - A reference to the region where the regional forwarding rule resides.\nThis field is not applicable to global forwarding rules."
  type        = string
  default     = null
}

variable "service_label" {
  description = "(optional) - An optional prefix to the service name for this Forwarding Rule.\nIf specified, will be the first label of the fully qualified service\nname.\n\nThe label must be 1-63 characters long, and comply with RFC1035.\nSpecifically, the label must be 1-63 characters long and match the\nregular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the first\ncharacter must be a lowercase letter, and all following characters\nmust be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash.\n\nThis field is only used for INTERNAL load balancing."
  type        = string
  default     = null
}

variable "subnetwork" {
  description = "(optional) - The subnetwork that the load balanced IP should belong to for this\nForwarding Rule.  This field is only used for INTERNAL load balancing.\n\nIf the network specified is in auto subnet mode, this field is\noptional. However, if the network is in custom subnet mode, a\nsubnetwork must be specified."
  type        = string
  default     = null
}

variable "target" {
  description = "(optional) - The URL of the target resource to receive the matched traffic.\nThe target must live in the same region as the forwarding rule.\nThe forwarded traffic must be of a type appropriate to the target\nobject."
  type        = string
  default     = null
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
resource "google_compute_forwarding_rule" "this" {
  # all_ports - (optional) is a type of bool
  all_ports = var.all_ports
  # allow_global_access - (optional) is a type of bool
  allow_global_access = var.allow_global_access
  # backend_service - (optional) is a type of string
  backend_service = var.backend_service
  # description - (optional) is a type of string
  description = var.description
  # ip_address - (optional) is a type of string
  ip_address = var.ip_address
  # ip_protocol - (optional) is a type of string
  ip_protocol = var.ip_protocol
  # is_mirroring_collector - (optional) is a type of bool
  is_mirroring_collector = var.is_mirroring_collector
  # labels - (optional) is a type of map of string
  labels = var.labels
  # load_balancing_scheme - (optional) is a type of string
  load_balancing_scheme = var.load_balancing_scheme
  # name - (required) is a type of string
  name = var.name
  # network - (optional) is a type of string
  network = var.network
  # network_tier - (optional) is a type of string
  network_tier = var.network_tier
  # port_range - (optional) is a type of string
  port_range = var.port_range
  # ports - (optional) is a type of set of string
  ports = var.ports
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # service_label - (optional) is a type of string
  service_label = var.service_label
  # subnetwork - (optional) is a type of string
  subnetwork = var.subnetwork
  # target - (optional) is a type of string
  target = var.target

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.ip_address
}

output "ip_protocol" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.ip_protocol
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.label_fingerprint
}

output "network" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.network
}

output "network_tier" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.network_tier
}

output "project" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.self_link
}

output "service_name" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.service_name
}

output "subnetwork" {
  description = "returns a string"
  value       = google_compute_forwarding_rule.this.subnetwork
}

output "this" {
  value = google_compute_forwarding_rule.this
}
```

[top](#index)