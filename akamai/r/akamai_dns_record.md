# akamai_dns_record

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_dns_record" {
  source = "./modules/akamai/r/akamai_dns_record"

  # active - (optional) is a type of bool
  active = null
  # algorithm - (optional) is a type of number
  algorithm = null
  # certificate - (optional) is a type of string
  certificate = null
  # digest - (optional) is a type of string
  digest = null
  # digest_type - (optional) is a type of number
  digest_type = null
  # email_address - (optional) is a type of string
  email_address = null
  # expiration - (optional) is a type of string
  expiration = null
  # expiry - (optional) is a type of number
  expiry = null
  # fingerprint - (optional) is a type of string
  fingerprint = null
  # fingerprint_type - (optional) is a type of number
  fingerprint_type = null
  # flags - (optional) is a type of number
  flags = null
  # flagsnaptr - (optional) is a type of string
  flagsnaptr = null
  # hardware - (optional) is a type of string
  hardware = null
  # inception - (optional) is a type of string
  inception = null
  # iterations - (optional) is a type of number
  iterations = null
  # key - (optional) is a type of string
  key = null
  # keytag - (optional) is a type of number
  keytag = null
  # labels - (optional) is a type of number
  labels = null
  # mailbox - (optional) is a type of string
  mailbox = null
  # match_type - (optional) is a type of number
  match_type = null
  # name - (required) is a type of string
  name = null
  # name_server - (optional) is a type of string
  name_server = null
  # next_hashed_owner_name - (optional) is a type of string
  next_hashed_owner_name = null
  # nxdomain_ttl - (optional) is a type of number
  nxdomain_ttl = null
  # order - (optional) is a type of number
  order = null
  # original_ttl - (optional) is a type of number
  original_ttl = null
  # port - (optional) is a type of number
  port = null
  # preference - (optional) is a type of number
  preference = null
  # priority - (optional) is a type of number
  priority = null
  # priority_increment - (optional) is a type of number
  priority_increment = null
  # protocol - (optional) is a type of number
  protocol = null
  # recordtype - (required) is a type of string
  recordtype = null
  # refresh - (optional) is a type of number
  refresh = null
  # regexp - (optional) is a type of string
  regexp = null
  # replacement - (optional) is a type of string
  replacement = null
  # retry - (optional) is a type of number
  retry = null
  # salt - (optional) is a type of string
  salt = null
  # selector - (optional) is a type of number
  selector = null
  # service - (optional) is a type of string
  service = null
  # signature - (optional) is a type of string
  signature = null
  # signer - (optional) is a type of string
  signer = null
  # software - (optional) is a type of string
  software = null
  # subtype - (optional) is a type of number
  subtype = null
  # svc_params - (optional) is a type of string
  svc_params = null
  # svc_priority - (optional) is a type of number
  svc_priority = null
  # target - (optional) is a type of list of string
  target = []
  # target_name - (optional) is a type of string
  target_name = null
  # ttl - (required) is a type of number
  ttl = null
  # txt - (optional) is a type of string
  txt = null
  # type_bitmaps - (optional) is a type of string
  type_bitmaps = null
  # type_covered - (optional) is a type of string
  type_covered = null
  # type_mnemonic - (optional) is a type of string
  type_mnemonic = null
  # type_value - (optional) is a type of number
  type_value = null
  # usage - (optional) is a type of number
  usage = null
  # weight - (optional) is a type of number
  weight = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "algorithm" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "digest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "digest_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "email_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fingerprint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fingerprint_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "flags" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "flagsnaptr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hardware" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inception" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iterations" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keytag" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mailbox" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "next_hashed_owner_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nxdomain_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "order" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "original_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preference" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "priority_increment" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "recordtype" {
  description = "(required)"
  type        = string
}

variable "refresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "regexp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replacement" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "salt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selector" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signature" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "software" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subtype" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "svc_params" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "svc_priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "target" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "target_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(required)"
  type        = number
}

variable "txt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type_bitmaps" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type_covered" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type_mnemonic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "usage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "akamai_dns_record" "this" {
  active                 = var.active
  algorithm              = var.algorithm
  certificate            = var.certificate
  digest                 = var.digest
  digest_type            = var.digest_type
  email_address          = var.email_address
  expiration             = var.expiration
  expiry                 = var.expiry
  fingerprint            = var.fingerprint
  fingerprint_type       = var.fingerprint_type
  flags                  = var.flags
  flagsnaptr             = var.flagsnaptr
  hardware               = var.hardware
  inception              = var.inception
  iterations             = var.iterations
  key                    = var.key
  keytag                 = var.keytag
  labels                 = var.labels
  mailbox                = var.mailbox
  match_type             = var.match_type
  name                   = var.name
  name_server            = var.name_server
  next_hashed_owner_name = var.next_hashed_owner_name
  nxdomain_ttl           = var.nxdomain_ttl
  order                  = var.order
  original_ttl           = var.original_ttl
  port                   = var.port
  preference             = var.preference
  priority               = var.priority
  priority_increment     = var.priority_increment
  protocol               = var.protocol
  recordtype             = var.recordtype
  refresh                = var.refresh
  regexp                 = var.regexp
  replacement            = var.replacement
  retry                  = var.retry
  salt                   = var.salt
  selector               = var.selector
  service                = var.service
  signature              = var.signature
  signer                 = var.signer
  software               = var.software
  subtype                = var.subtype
  svc_params             = var.svc_params
  svc_priority           = var.svc_priority
  target                 = var.target
  target_name            = var.target_name
  ttl                    = var.ttl
  txt                    = var.txt
  type_bitmaps           = var.type_bitmaps
  type_covered           = var.type_covered
  type_mnemonic          = var.type_mnemonic
  type_value             = var.type_value
  usage                  = var.usage
  weight                 = var.weight
  zone                   = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "answer_type" {
  description = "returns a string"
  value       = akamai_dns_record.this.answer_type
}

output "dns_name" {
  description = "returns a string"
  value       = akamai_dns_record.this.dns_name
}

output "id" {
  description = "returns a string"
  value       = akamai_dns_record.this.id
}

output "record_sha" {
  description = "returns a string"
  value       = akamai_dns_record.this.record_sha
}

output "serial" {
  description = "returns a number"
  value       = akamai_dns_record.this.serial
}

output "this" {
  value = akamai_dns_record.this
}
```

[top](#index)