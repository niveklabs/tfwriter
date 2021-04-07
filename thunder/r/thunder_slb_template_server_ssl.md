# thunder_slb_template_server_ssl

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_server_ssl" {
  source = "./modules/thunder/r/thunder_slb_template_server_ssl"

  # alert_type - (optional) is a type of string
  alert_type = null
  # cert - (optional) is a type of string
  cert = null
  # cert_shared_str - (optional) is a type of string
  cert_shared_str = null
  # cipher_template - (optional) is a type of string
  cipher_template = null
  # close_notify - (optional) is a type of number
  close_notify = null
  # dgversion - (optional) is a type of number
  dgversion = null
  # dh_type - (optional) is a type of string
  dh_type = null
  # enable_tls_alert_logging - (optional) is a type of number
  enable_tls_alert_logging = null
  # encrypted - (optional) is a type of string
  encrypted = null
  # forward_proxy_enable - (optional) is a type of number
  forward_proxy_enable = null
  # handshake_logging_enable - (optional) is a type of number
  handshake_logging_enable = null
  # key - (optional) is a type of string
  key = null
  # key_shared_encrypted - (optional) is a type of string
  key_shared_encrypted = null
  # key_shared_passphrase - (optional) is a type of string
  key_shared_passphrase = null
  # key_shared_str - (optional) is a type of string
  key_shared_str = null
  # name - (optional) is a type of string
  name = null
  # ocsp_stapling - (optional) is a type of number
  ocsp_stapling = null
  # passphrase - (optional) is a type of string
  passphrase = null
  # renegotiation_disable - (optional) is a type of number
  renegotiation_disable = null
  # session_cache_size - (optional) is a type of number
  session_cache_size = null
  # session_cache_timeout - (optional) is a type of number
  session_cache_timeout = null
  # session_ticket_enable - (optional) is a type of number
  session_ticket_enable = null
  # shared_partition_cipher_template - (optional) is a type of number
  shared_partition_cipher_template = null
  # ssli_logging - (optional) is a type of number
  ssli_logging = null
  # sslilogging - (optional) is a type of string
  sslilogging = null
  # template_cipher_shared - (optional) is a type of string
  template_cipher_shared = null
  # use_client_sni - (optional) is a type of number
  use_client_sni = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # version - (optional) is a type of number
  version = null

  ca_certs = [{
    ca_cert                  = null
    ca_cert_partition_shared = null
    server_ocsp_sg           = null
    server_ocsp_srvr         = null
  }]

  cipher_without_prio_list = [{
    cipher_wo_prio = null
  }]

  crl_certs = [{
    crl = null
  }]

  ec_list = [{
    ec = null
  }]

  server_certificate_error = [{
    error_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alert_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_shared_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cipher_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "close_notify" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dgversion" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dh_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_tls_alert_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_proxy_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "handshake_logging_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_shared_encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_shared_passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_shared_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ocsp_stapling" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "passphrase" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "renegotiation_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_cache_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_cache_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_ticket_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_cipher_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssli_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sslilogging" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_cipher_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_client_sni" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ca_certs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ca_cert                  = string
      ca_cert_partition_shared = number
      server_ocsp_sg           = string
      server_ocsp_srvr         = string
    }
  ))
  default = []
}

variable "cipher_without_prio_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cipher_wo_prio = string
    }
  ))
  default = []
}

variable "crl_certs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      crl = string
    }
  ))
  default = []
}

variable "ec_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ec = string
    }
  ))
  default = []
}

variable "server_certificate_error" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      error_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_server_ssl" "this" {
  # alert_type - (optional) is a type of string
  alert_type = var.alert_type
  # cert - (optional) is a type of string
  cert = var.cert
  # cert_shared_str - (optional) is a type of string
  cert_shared_str = var.cert_shared_str
  # cipher_template - (optional) is a type of string
  cipher_template = var.cipher_template
  # close_notify - (optional) is a type of number
  close_notify = var.close_notify
  # dgversion - (optional) is a type of number
  dgversion = var.dgversion
  # dh_type - (optional) is a type of string
  dh_type = var.dh_type
  # enable_tls_alert_logging - (optional) is a type of number
  enable_tls_alert_logging = var.enable_tls_alert_logging
  # encrypted - (optional) is a type of string
  encrypted = var.encrypted
  # forward_proxy_enable - (optional) is a type of number
  forward_proxy_enable = var.forward_proxy_enable
  # handshake_logging_enable - (optional) is a type of number
  handshake_logging_enable = var.handshake_logging_enable
  # key - (optional) is a type of string
  key = var.key
  # key_shared_encrypted - (optional) is a type of string
  key_shared_encrypted = var.key_shared_encrypted
  # key_shared_passphrase - (optional) is a type of string
  key_shared_passphrase = var.key_shared_passphrase
  # key_shared_str - (optional) is a type of string
  key_shared_str = var.key_shared_str
  # name - (optional) is a type of string
  name = var.name
  # ocsp_stapling - (optional) is a type of number
  ocsp_stapling = var.ocsp_stapling
  # passphrase - (optional) is a type of string
  passphrase = var.passphrase
  # renegotiation_disable - (optional) is a type of number
  renegotiation_disable = var.renegotiation_disable
  # session_cache_size - (optional) is a type of number
  session_cache_size = var.session_cache_size
  # session_cache_timeout - (optional) is a type of number
  session_cache_timeout = var.session_cache_timeout
  # session_ticket_enable - (optional) is a type of number
  session_ticket_enable = var.session_ticket_enable
  # shared_partition_cipher_template - (optional) is a type of number
  shared_partition_cipher_template = var.shared_partition_cipher_template
  # ssli_logging - (optional) is a type of number
  ssli_logging = var.ssli_logging
  # sslilogging - (optional) is a type of string
  sslilogging = var.sslilogging
  # template_cipher_shared - (optional) is a type of string
  template_cipher_shared = var.template_cipher_shared
  # use_client_sni - (optional) is a type of number
  use_client_sni = var.use_client_sni
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # version - (optional) is a type of number
  version = var.version

  dynamic "ca_certs" {
    for_each = var.ca_certs
    content {
      # ca_cert - (optional) is a type of string
      ca_cert = ca_certs.value["ca_cert"]
      # ca_cert_partition_shared - (optional) is a type of number
      ca_cert_partition_shared = ca_certs.value["ca_cert_partition_shared"]
      # server_ocsp_sg - (optional) is a type of string
      server_ocsp_sg = ca_certs.value["server_ocsp_sg"]
      # server_ocsp_srvr - (optional) is a type of string
      server_ocsp_srvr = ca_certs.value["server_ocsp_srvr"]
    }
  }

  dynamic "cipher_without_prio_list" {
    for_each = var.cipher_without_prio_list
    content {
      # cipher_wo_prio - (optional) is a type of string
      cipher_wo_prio = cipher_without_prio_list.value["cipher_wo_prio"]
    }
  }

  dynamic "crl_certs" {
    for_each = var.crl_certs
    content {
      # crl - (optional) is a type of string
      crl = crl_certs.value["crl"]
    }
  }

  dynamic "ec_list" {
    for_each = var.ec_list
    content {
      # ec - (optional) is a type of string
      ec = ec_list.value["ec"]
    }
  }

  dynamic "server_certificate_error" {
    for_each = var.server_certificate_error
    content {
      # error_type - (optional) is a type of string
      error_type = server_certificate_error.value["error_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_server_ssl.this.id
}

output "this" {
  value = thunder_slb_template_server_ssl.this
}
```

[top](#index)