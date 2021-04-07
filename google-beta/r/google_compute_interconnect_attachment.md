# google_compute_interconnect_attachment

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
module "google_compute_interconnect_attachment" {
  source = "./modules/google-beta/r/google_compute_interconnect_attachment"

  # admin_enabled - (optional) is a type of bool
  admin_enabled = null
  # bandwidth - (optional) is a type of string
  bandwidth = null
  # candidate_subnets - (optional) is a type of list of string
  candidate_subnets = []
  # description - (optional) is a type of string
  description = null
  # edge_availability_domain - (optional) is a type of string
  edge_availability_domain = null
  # interconnect - (optional) is a type of string
  interconnect = null
  # mtu - (optional) is a type of string
  mtu = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # router - (required) is a type of string
  router = null
  # type - (optional) is a type of string
  type = null
  # vlan_tag8021q - (optional) is a type of number
  vlan_tag8021q = null

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
variable "admin_enabled" {
  description = "(optional) - Whether the VLAN attachment is enabled or disabled.  When using\nPARTNER type this will Pre-Activate the interconnect attachment"
  type        = bool
  default     = null
}

variable "bandwidth" {
  description = "(optional) - Provisioned bandwidth capacity for the interconnect attachment.\nFor attachments of type DEDICATED, the user can set the bandwidth.\nFor attachments of type PARTNER, the Google Partner that is operating the interconnect must set the bandwidth.\nOutput only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED,\nDefaults to BPS_10G Possible values: [\"BPS_50M\", \"BPS_100M\", \"BPS_200M\", \"BPS_300M\", \"BPS_400M\", \"BPS_500M\", \"BPS_1G\", \"BPS_2G\", \"BPS_5G\", \"BPS_10G\", \"BPS_20G\", \"BPS_50G\"]"
  type        = string
  default     = null
}

variable "candidate_subnets" {
  description = "(optional) - Up to 16 candidate prefixes that can be used to restrict the allocation\nof cloudRouterIpAddress and customerRouterIpAddress for this attachment.\nAll prefixes must be within link-local address space (169.254.0.0/16)\nand must be /29 or shorter (/28, /27, etc). Google will attempt to select\nan unused /29 from the supplied candidate prefix(es). The request will\nfail if all possible /29s are in use on Google's edge. If not supplied,\nGoogle will randomly select an unused /29 from all of link-local space."
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "edge_availability_domain" {
  description = "(optional) - Desired availability domain for the attachment. Only available for type\nPARTNER, at creation time. For improved reliability, customers should\nconfigure a pair of attachments with one per availability domain. The\nselected availability domain will be provided to the Partner via the\npairing key so that the provisioned circuit will lie in the specified\ndomain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY."
  type        = string
  default     = null
}

variable "interconnect" {
  description = "(optional) - URL of the underlying Interconnect object that this attachment's\ntraffic will traverse through. Required if type is DEDICATED, must not\nbe set if type is PARTNER."
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional) - Maximum Transmission Unit (MTU), in bytes, of packets passing through\nthis interconnect attachment. Currently, only 1440 and 1500 are allowed. If not specified, the value will default to 1440."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is created. The\nname must be 1-63 characters long, and comply with RFC1035. Specifically, the\nname must be 1-63 characters long and match the regular expression\n'[a-z]([-a-z0-9]*[a-z0-9])?' which means the first character must be a\nlowercase letter, and all following characters must be a dash, lowercase\nletter, or digit, except the last character, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where the regional interconnect attachment resides."
  type        = string
  default     = null
}

variable "router" {
  description = "(required) - URL of the cloud router to be used for dynamic routing. This router must be in\nthe same region as this InterconnectAttachment. The InterconnectAttachment will\nautomatically connect the Interconnect to the network & region within which the\nCloud Router is configured."
  type        = string
}

variable "type" {
  description = "(optional) - The type of InterconnectAttachment you wish to create. Defaults to\nDEDICATED. Possible values: [\"DEDICATED\", \"PARTNER\", \"PARTNER_PROVIDER\"]"
  type        = string
  default     = null
}

variable "vlan_tag8021q" {
  description = "(optional) - The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When\nusing PARTNER type this will be managed upstream."
  type        = number
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
resource "google_compute_interconnect_attachment" "this" {
  # admin_enabled - (optional) is a type of bool
  admin_enabled = var.admin_enabled
  # bandwidth - (optional) is a type of string
  bandwidth = var.bandwidth
  # candidate_subnets - (optional) is a type of list of string
  candidate_subnets = var.candidate_subnets
  # description - (optional) is a type of string
  description = var.description
  # edge_availability_domain - (optional) is a type of string
  edge_availability_domain = var.edge_availability_domain
  # interconnect - (optional) is a type of string
  interconnect = var.interconnect
  # mtu - (optional) is a type of string
  mtu = var.mtu
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # router - (required) is a type of string
  router = var.router
  # type - (optional) is a type of string
  type = var.type
  # vlan_tag8021q - (optional) is a type of number
  vlan_tag8021q = var.vlan_tag8021q

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
output "bandwidth" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.bandwidth
}

output "cloud_router_ip_address" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.cloud_router_ip_address
}

output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.creation_timestamp
}

output "customer_router_ip_address" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.customer_router_ip_address
}

output "edge_availability_domain" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.edge_availability_domain
}

output "google_reference_id" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.google_reference_id
}

output "id" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.id
}

output "mtu" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.mtu
}

output "pairing_key" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.pairing_key
}

output "partner_asn" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.partner_asn
}

output "private_interconnect_info" {
  description = "returns a list of object"
  value       = google_compute_interconnect_attachment.this.private_interconnect_info
}

output "project" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.self_link
}

output "state" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.state
}

output "type" {
  description = "returns a string"
  value       = google_compute_interconnect_attachment.this.type
}

output "vlan_tag8021q" {
  description = "returns a number"
  value       = google_compute_interconnect_attachment.this.vlan_tag8021q
}

output "this" {
  value = google_compute_interconnect_attachment.this
}
```

[top](#index)