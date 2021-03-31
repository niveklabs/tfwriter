# fastly_service_compute

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_service_compute" {
  source = "./modules/fastly/r/fastly_service_compute"

  # activate - (optional) is a type of bool
  activate = null
  # comment - (optional) is a type of string
  comment = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # name - (required) is a type of string
  name = null
  # version_comment - (optional) is a type of string
  version_comment = null

  backend = [{
    address               = null
    auto_loadbalance      = null
    between_bytes_timeout = null
    connect_timeout       = null
    error_threshold       = null
    first_byte_timeout    = null
    healthcheck           = null
    max_conn              = null
    max_tls_version       = null
    min_tls_version       = null
    name                  = null
    override_host         = null
    port                  = null
    shield                = null
    ssl_ca_cert           = null
    ssl_cert_hostname     = null
    ssl_check_cert        = null
    ssl_ciphers           = null
    ssl_client_cert       = null
    ssl_client_key        = null
    ssl_hostname          = null
    ssl_sni_hostname      = null
    use_ssl               = null
    weight                = null
  }]

  bigquerylogging = [{
    dataset    = null
    email      = null
    name       = null
    project_id = null
    secret_key = null
    table      = null
    template   = null
  }]

  blobstoragelogging = [{
    account_name     = null
    container        = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    public_key       = null
    sas_token        = null
    timestamp_format = null
  }]

  dictionary = [{
    dictionary_id = null
    force_destroy = null
    name          = null
    write_only    = null
  }]

  domain = [{
    comment = null
    name    = null
  }]

  gcslogging = [{
    bucket_name      = null
    email            = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    secret_key       = null
    timestamp_format = null
  }]

  healthcheck = [{
    check_interval    = null
    expected_response = null
    host              = null
    http_version      = null
    initial           = null
    method            = null
    name              = null
    path              = null
    threshold         = null
    timeout           = null
    window            = null
  }]

  httpslogging = [{
    content_type        = null
    header_name         = null
    header_value        = null
    json_format         = null
    message_type        = null
    method              = null
    name                = null
    request_max_bytes   = null
    request_max_entries = null
    tls_ca_cert         = null
    tls_client_cert     = null
    tls_client_key      = null
    tls_hostname        = null
    url                 = null
  }]

  logentries = [{
    name    = null
    port    = null
    token   = null
    use_tls = null
  }]

  logging_cloudfiles = [{
    access_key       = null
    bucket_name      = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    public_key       = null
    region           = null
    timestamp_format = null
    user             = null
  }]

  logging_datadog = [{
    name   = null
    region = null
    token  = null
  }]

  logging_digitalocean = [{
    access_key       = null
    bucket_name      = null
    domain           = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    public_key       = null
    secret_key       = null
    timestamp_format = null
  }]

  logging_elasticsearch = [{
    index               = null
    name                = null
    password            = null
    pipeline            = null
    request_max_bytes   = null
    request_max_entries = null
    tls_ca_cert         = null
    tls_client_cert     = null
    tls_client_key      = null
    tls_hostname        = null
    url                 = null
    user                = null
  }]

  logging_ftp = [{
    address          = null
    gzip_level       = null
    message_type     = null
    name             = null
    password         = null
    path             = null
    period           = null
    port             = null
    public_key       = null
    timestamp_format = null
    user             = null
  }]

  logging_googlepubsub = [{
    name       = null
    project_id = null
    secret_key = null
    topic      = null
    user       = null
  }]

  logging_heroku = [{
    name  = null
    token = null
    url   = null
  }]

  logging_honeycomb = [{
    dataset = null
    name    = null
    token   = null
  }]

  logging_kafka = [{
    auth_method       = null
    brokers           = null
    compression_codec = null
    name              = null
    parse_log_keyvals = null
    password          = null
    request_max_bytes = null
    required_acks     = null
    tls_ca_cert       = null
    tls_client_cert   = null
    tls_client_key    = null
    tls_hostname      = null
    topic             = null
    use_tls           = null
    user              = null
  }]

  logging_kinesis = [{
    access_key = null
    name       = null
    region     = null
    secret_key = null
    topic      = null
  }]

  logging_loggly = [{
    name  = null
    token = null
  }]

  logging_logshuttle = [{
    name  = null
    token = null
    url   = null
  }]

  logging_newrelic = [{
    name  = null
    token = null
  }]

  logging_openstack = [{
    access_key       = null
    bucket_name      = null
    gzip_level       = null
    message_type     = null
    name             = null
    path             = null
    period           = null
    public_key       = null
    timestamp_format = null
    url              = null
    user             = null
  }]

  logging_scalyr = [{
    name   = null
    region = null
    token  = null
  }]

  logging_sftp = [{
    address          = null
    gzip_level       = null
    message_type     = null
    name             = null
    password         = null
    path             = null
    period           = null
    port             = null
    public_key       = null
    secret_key       = null
    ssh_known_hosts  = null
    timestamp_format = null
    user             = null
  }]

  package = [{
    filename         = null
    source_code_hash = null
  }]

  papertrail = [{
    address = null
    name    = null
    port    = null
  }]

  s3logging = [{
    bucket_name                       = null
    domain                            = null
    gzip_level                        = null
    message_type                      = null
    name                              = null
    path                              = null
    period                            = null
    public_key                        = null
    redundancy                        = null
    s3_access_key                     = null
    s3_secret_key                     = null
    server_side_encryption            = null
    server_side_encryption_kms_key_id = null
    timestamp_format                  = null
  }]

  splunk = [{
    name            = null
    tls_ca_cert     = null
    tls_client_cert = null
    tls_client_key  = null
    tls_hostname    = null
    token           = null
    url             = null
  }]

  sumologic = [{
    message_type = null
    name         = null
    url          = null
  }]

  syslog = [{
    address         = null
    message_type    = null
    name            = null
    port            = null
    tls_ca_cert     = null
    tls_client_cert = null
    tls_client_key  = null
    tls_hostname    = null
    token           = null
    use_tls         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "activate" {
  description = "(optional) - Conditionally prevents the Service from being activated. The apply step will continue to create a new draft version but will not activate it if this is set to `false`. Default `true`"
  type        = bool
  default     = null
}

variable "comment" {
  description = "(optional) - Description field for the service. Default `Managed by Terraform`"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional) - Services that are active cannot be destroyed. In order to destroy the Service, set `force_destroy` to `true`. Default `false`"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The unique name for the Service to create"
  type        = string
}

variable "version_comment" {
  description = "(optional) - Description field for the version"
  type        = string
  default     = null
}

variable "backend" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      address               = string
      auto_loadbalance      = bool
      between_bytes_timeout = number
      connect_timeout       = number
      error_threshold       = number
      first_byte_timeout    = number
      healthcheck           = string
      max_conn              = number
      max_tls_version       = string
      min_tls_version       = string
      name                  = string
      override_host         = string
      port                  = number
      shield                = string
      ssl_ca_cert           = string
      ssl_cert_hostname     = string
      ssl_check_cert        = bool
      ssl_ciphers           = string
      ssl_client_cert       = string
      ssl_client_key        = string
      ssl_hostname          = string
      ssl_sni_hostname      = string
      use_ssl               = bool
      weight                = number
    }
  ))
}

variable "bigquerylogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dataset    = string
      email      = string
      name       = string
      project_id = string
      secret_key = string
      table      = string
      template   = string
    }
  ))
  default = []
}

variable "blobstoragelogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      account_name     = string
      container        = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      public_key       = string
      sas_token        = string
      timestamp_format = string
    }
  ))
  default = []
}

variable "dictionary" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dictionary_id = string
      force_destroy = bool
      name          = string
      write_only    = bool
    }
  ))
  default = []
}

variable "domain" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      comment = string
      name    = string
    }
  ))
}

variable "gcslogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name      = string
      email            = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      secret_key       = string
      timestamp_format = string
    }
  ))
  default = []
}

variable "healthcheck" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      check_interval    = number
      expected_response = number
      host              = string
      http_version      = string
      initial           = number
      method            = string
      name              = string
      path              = string
      threshold         = number
      timeout           = number
      window            = number
    }
  ))
  default = []
}

variable "httpslogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      content_type        = string
      header_name         = string
      header_value        = string
      json_format         = string
      message_type        = string
      method              = string
      name                = string
      request_max_bytes   = number
      request_max_entries = number
      tls_ca_cert         = string
      tls_client_cert     = string
      tls_client_key      = string
      tls_hostname        = string
      url                 = string
    }
  ))
  default = []
}

variable "logentries" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name    = string
      port    = number
      token   = string
      use_tls = bool
    }
  ))
  default = []
}

variable "logging_cloudfiles" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key       = string
      bucket_name      = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      public_key       = string
      region           = string
      timestamp_format = string
      user             = string
    }
  ))
  default = []
}

variable "logging_datadog" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      region = string
      token  = string
    }
  ))
  default = []
}

variable "logging_digitalocean" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key       = string
      bucket_name      = string
      domain           = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      public_key       = string
      secret_key       = string
      timestamp_format = string
    }
  ))
  default = []
}

variable "logging_elasticsearch" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      index               = string
      name                = string
      password            = string
      pipeline            = string
      request_max_bytes   = number
      request_max_entries = number
      tls_ca_cert         = string
      tls_client_cert     = string
      tls_client_key      = string
      tls_hostname        = string
      url                 = string
      user                = string
    }
  ))
  default = []
}

variable "logging_ftp" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address          = string
      gzip_level       = number
      message_type     = string
      name             = string
      password         = string
      path             = string
      period           = number
      port             = number
      public_key       = string
      timestamp_format = string
      user             = string
    }
  ))
  default = []
}

variable "logging_googlepubsub" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name       = string
      project_id = string
      secret_key = string
      topic      = string
      user       = string
    }
  ))
  default = []
}

variable "logging_heroku" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      token = string
      url   = string
    }
  ))
  default = []
}

variable "logging_honeycomb" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dataset = string
      name    = string
      token   = string
    }
  ))
  default = []
}

variable "logging_kafka" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auth_method       = string
      brokers           = string
      compression_codec = string
      name              = string
      parse_log_keyvals = bool
      password          = string
      request_max_bytes = number
      required_acks     = string
      tls_ca_cert       = string
      tls_client_cert   = string
      tls_client_key    = string
      tls_hostname      = string
      topic             = string
      use_tls           = bool
      user              = string
    }
  ))
  default = []
}

variable "logging_kinesis" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key = string
      name       = string
      region     = string
      secret_key = string
      topic      = string
    }
  ))
  default = []
}

variable "logging_loggly" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      token = string
    }
  ))
  default = []
}

variable "logging_logshuttle" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      token = string
      url   = string
    }
  ))
  default = []
}

variable "logging_newrelic" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      token = string
    }
  ))
  default = []
}

variable "logging_openstack" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key       = string
      bucket_name      = string
      gzip_level       = number
      message_type     = string
      name             = string
      path             = string
      period           = number
      public_key       = string
      timestamp_format = string
      url              = string
      user             = string
    }
  ))
  default = []
}

variable "logging_scalyr" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      region = string
      token  = string
    }
  ))
  default = []
}

variable "logging_sftp" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address          = string
      gzip_level       = number
      message_type     = string
      name             = string
      password         = string
      path             = string
      period           = number
      port             = number
      public_key       = string
      secret_key       = string
      ssh_known_hosts  = string
      timestamp_format = string
      user             = string
    }
  ))
  default = []
}

variable "package" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      filename         = string
      source_code_hash = string
    }
  ))
}

variable "papertrail" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address = string
      name    = string
      port    = number
    }
  ))
  default = []
}

variable "s3logging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name                       = string
      domain                            = string
      gzip_level                        = number
      message_type                      = string
      name                              = string
      path                              = string
      period                            = number
      public_key                        = string
      redundancy                        = string
      s3_access_key                     = string
      s3_secret_key                     = string
      server_side_encryption            = string
      server_side_encryption_kms_key_id = string
      timestamp_format                  = string
    }
  ))
  default = []
}

variable "splunk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name            = string
      tls_ca_cert     = string
      tls_client_cert = string
      tls_client_key  = string
      tls_hostname    = string
      token           = string
      url             = string
    }
  ))
  default = []
}

variable "sumologic" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      message_type = string
      name         = string
      url          = string
    }
  ))
  default = []
}

variable "syslog" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address         = string
      message_type    = string
      name            = string
      port            = number
      tls_ca_cert     = string
      tls_client_cert = string
      tls_client_key  = string
      tls_hostname    = string
      token           = string
      use_tls         = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fastly_service_compute" "this" {
  activate        = var.activate
  comment         = var.comment
  force_destroy   = var.force_destroy
  name            = var.name
  version_comment = var.version_comment

  dynamic "backend" {
    for_each = var.backend
    content {
      address               = backend.value["address"]
      auto_loadbalance      = backend.value["auto_loadbalance"]
      between_bytes_timeout = backend.value["between_bytes_timeout"]
      connect_timeout       = backend.value["connect_timeout"]
      error_threshold       = backend.value["error_threshold"]
      first_byte_timeout    = backend.value["first_byte_timeout"]
      healthcheck           = backend.value["healthcheck"]
      max_conn              = backend.value["max_conn"]
      max_tls_version       = backend.value["max_tls_version"]
      min_tls_version       = backend.value["min_tls_version"]
      name                  = backend.value["name"]
      override_host         = backend.value["override_host"]
      port                  = backend.value["port"]
      shield                = backend.value["shield"]
      ssl_ca_cert           = backend.value["ssl_ca_cert"]
      ssl_cert_hostname     = backend.value["ssl_cert_hostname"]
      ssl_check_cert        = backend.value["ssl_check_cert"]
      ssl_ciphers           = backend.value["ssl_ciphers"]
      ssl_client_cert       = backend.value["ssl_client_cert"]
      ssl_client_key        = backend.value["ssl_client_key"]
      ssl_hostname          = backend.value["ssl_hostname"]
      ssl_sni_hostname      = backend.value["ssl_sni_hostname"]
      use_ssl               = backend.value["use_ssl"]
      weight                = backend.value["weight"]
    }
  }

  dynamic "bigquerylogging" {
    for_each = var.bigquerylogging
    content {
      dataset    = bigquerylogging.value["dataset"]
      email      = bigquerylogging.value["email"]
      name       = bigquerylogging.value["name"]
      project_id = bigquerylogging.value["project_id"]
      secret_key = bigquerylogging.value["secret_key"]
      table      = bigquerylogging.value["table"]
      template   = bigquerylogging.value["template"]
    }
  }

  dynamic "blobstoragelogging" {
    for_each = var.blobstoragelogging
    content {
      account_name     = blobstoragelogging.value["account_name"]
      container        = blobstoragelogging.value["container"]
      gzip_level       = blobstoragelogging.value["gzip_level"]
      message_type     = blobstoragelogging.value["message_type"]
      name             = blobstoragelogging.value["name"]
      path             = blobstoragelogging.value["path"]
      period           = blobstoragelogging.value["period"]
      public_key       = blobstoragelogging.value["public_key"]
      sas_token        = blobstoragelogging.value["sas_token"]
      timestamp_format = blobstoragelogging.value["timestamp_format"]
    }
  }

  dynamic "dictionary" {
    for_each = var.dictionary
    content {
      force_destroy = dictionary.value["force_destroy"]
      name          = dictionary.value["name"]
      write_only    = dictionary.value["write_only"]
    }
  }

  dynamic "domain" {
    for_each = var.domain
    content {
      comment = domain.value["comment"]
      name    = domain.value["name"]
    }
  }

  dynamic "gcslogging" {
    for_each = var.gcslogging
    content {
      bucket_name      = gcslogging.value["bucket_name"]
      email            = gcslogging.value["email"]
      gzip_level       = gcslogging.value["gzip_level"]
      message_type     = gcslogging.value["message_type"]
      name             = gcslogging.value["name"]
      path             = gcslogging.value["path"]
      period           = gcslogging.value["period"]
      secret_key       = gcslogging.value["secret_key"]
      timestamp_format = gcslogging.value["timestamp_format"]
    }
  }

  dynamic "healthcheck" {
    for_each = var.healthcheck
    content {
      check_interval    = healthcheck.value["check_interval"]
      expected_response = healthcheck.value["expected_response"]
      host              = healthcheck.value["host"]
      http_version      = healthcheck.value["http_version"]
      initial           = healthcheck.value["initial"]
      method            = healthcheck.value["method"]
      name              = healthcheck.value["name"]
      path              = healthcheck.value["path"]
      threshold         = healthcheck.value["threshold"]
      timeout           = healthcheck.value["timeout"]
      window            = healthcheck.value["window"]
    }
  }

  dynamic "httpslogging" {
    for_each = var.httpslogging
    content {
      content_type        = httpslogging.value["content_type"]
      header_name         = httpslogging.value["header_name"]
      header_value        = httpslogging.value["header_value"]
      json_format         = httpslogging.value["json_format"]
      message_type        = httpslogging.value["message_type"]
      method              = httpslogging.value["method"]
      name                = httpslogging.value["name"]
      request_max_bytes   = httpslogging.value["request_max_bytes"]
      request_max_entries = httpslogging.value["request_max_entries"]
      tls_ca_cert         = httpslogging.value["tls_ca_cert"]
      tls_client_cert     = httpslogging.value["tls_client_cert"]
      tls_client_key      = httpslogging.value["tls_client_key"]
      tls_hostname        = httpslogging.value["tls_hostname"]
      url                 = httpslogging.value["url"]
    }
  }

  dynamic "logentries" {
    for_each = var.logentries
    content {
      name    = logentries.value["name"]
      port    = logentries.value["port"]
      token   = logentries.value["token"]
      use_tls = logentries.value["use_tls"]
    }
  }

  dynamic "logging_cloudfiles" {
    for_each = var.logging_cloudfiles
    content {
      access_key       = logging_cloudfiles.value["access_key"]
      bucket_name      = logging_cloudfiles.value["bucket_name"]
      gzip_level       = logging_cloudfiles.value["gzip_level"]
      message_type     = logging_cloudfiles.value["message_type"]
      name             = logging_cloudfiles.value["name"]
      path             = logging_cloudfiles.value["path"]
      period           = logging_cloudfiles.value["period"]
      public_key       = logging_cloudfiles.value["public_key"]
      region           = logging_cloudfiles.value["region"]
      timestamp_format = logging_cloudfiles.value["timestamp_format"]
      user             = logging_cloudfiles.value["user"]
    }
  }

  dynamic "logging_datadog" {
    for_each = var.logging_datadog
    content {
      name   = logging_datadog.value["name"]
      region = logging_datadog.value["region"]
      token  = logging_datadog.value["token"]
    }
  }

  dynamic "logging_digitalocean" {
    for_each = var.logging_digitalocean
    content {
      access_key       = logging_digitalocean.value["access_key"]
      bucket_name      = logging_digitalocean.value["bucket_name"]
      domain           = logging_digitalocean.value["domain"]
      gzip_level       = logging_digitalocean.value["gzip_level"]
      message_type     = logging_digitalocean.value["message_type"]
      name             = logging_digitalocean.value["name"]
      path             = logging_digitalocean.value["path"]
      period           = logging_digitalocean.value["period"]
      public_key       = logging_digitalocean.value["public_key"]
      secret_key       = logging_digitalocean.value["secret_key"]
      timestamp_format = logging_digitalocean.value["timestamp_format"]
    }
  }

  dynamic "logging_elasticsearch" {
    for_each = var.logging_elasticsearch
    content {
      index               = logging_elasticsearch.value["index"]
      name                = logging_elasticsearch.value["name"]
      password            = logging_elasticsearch.value["password"]
      pipeline            = logging_elasticsearch.value["pipeline"]
      request_max_bytes   = logging_elasticsearch.value["request_max_bytes"]
      request_max_entries = logging_elasticsearch.value["request_max_entries"]
      tls_ca_cert         = logging_elasticsearch.value["tls_ca_cert"]
      tls_client_cert     = logging_elasticsearch.value["tls_client_cert"]
      tls_client_key      = logging_elasticsearch.value["tls_client_key"]
      tls_hostname        = logging_elasticsearch.value["tls_hostname"]
      url                 = logging_elasticsearch.value["url"]
      user                = logging_elasticsearch.value["user"]
    }
  }

  dynamic "logging_ftp" {
    for_each = var.logging_ftp
    content {
      address          = logging_ftp.value["address"]
      gzip_level       = logging_ftp.value["gzip_level"]
      message_type     = logging_ftp.value["message_type"]
      name             = logging_ftp.value["name"]
      password         = logging_ftp.value["password"]
      path             = logging_ftp.value["path"]
      period           = logging_ftp.value["period"]
      port             = logging_ftp.value["port"]
      public_key       = logging_ftp.value["public_key"]
      timestamp_format = logging_ftp.value["timestamp_format"]
      user             = logging_ftp.value["user"]
    }
  }

  dynamic "logging_googlepubsub" {
    for_each = var.logging_googlepubsub
    content {
      name       = logging_googlepubsub.value["name"]
      project_id = logging_googlepubsub.value["project_id"]
      secret_key = logging_googlepubsub.value["secret_key"]
      topic      = logging_googlepubsub.value["topic"]
      user       = logging_googlepubsub.value["user"]
    }
  }

  dynamic "logging_heroku" {
    for_each = var.logging_heroku
    content {
      name  = logging_heroku.value["name"]
      token = logging_heroku.value["token"]
      url   = logging_heroku.value["url"]
    }
  }

  dynamic "logging_honeycomb" {
    for_each = var.logging_honeycomb
    content {
      dataset = logging_honeycomb.value["dataset"]
      name    = logging_honeycomb.value["name"]
      token   = logging_honeycomb.value["token"]
    }
  }

  dynamic "logging_kafka" {
    for_each = var.logging_kafka
    content {
      auth_method       = logging_kafka.value["auth_method"]
      brokers           = logging_kafka.value["brokers"]
      compression_codec = logging_kafka.value["compression_codec"]
      name              = logging_kafka.value["name"]
      parse_log_keyvals = logging_kafka.value["parse_log_keyvals"]
      password          = logging_kafka.value["password"]
      request_max_bytes = logging_kafka.value["request_max_bytes"]
      required_acks     = logging_kafka.value["required_acks"]
      tls_ca_cert       = logging_kafka.value["tls_ca_cert"]
      tls_client_cert   = logging_kafka.value["tls_client_cert"]
      tls_client_key    = logging_kafka.value["tls_client_key"]
      tls_hostname      = logging_kafka.value["tls_hostname"]
      topic             = logging_kafka.value["topic"]
      use_tls           = logging_kafka.value["use_tls"]
      user              = logging_kafka.value["user"]
    }
  }

  dynamic "logging_kinesis" {
    for_each = var.logging_kinesis
    content {
      access_key = logging_kinesis.value["access_key"]
      name       = logging_kinesis.value["name"]
      region     = logging_kinesis.value["region"]
      secret_key = logging_kinesis.value["secret_key"]
      topic      = logging_kinesis.value["topic"]
    }
  }

  dynamic "logging_loggly" {
    for_each = var.logging_loggly
    content {
      name  = logging_loggly.value["name"]
      token = logging_loggly.value["token"]
    }
  }

  dynamic "logging_logshuttle" {
    for_each = var.logging_logshuttle
    content {
      name  = logging_logshuttle.value["name"]
      token = logging_logshuttle.value["token"]
      url   = logging_logshuttle.value["url"]
    }
  }

  dynamic "logging_newrelic" {
    for_each = var.logging_newrelic
    content {
      name  = logging_newrelic.value["name"]
      token = logging_newrelic.value["token"]
    }
  }

  dynamic "logging_openstack" {
    for_each = var.logging_openstack
    content {
      access_key       = logging_openstack.value["access_key"]
      bucket_name      = logging_openstack.value["bucket_name"]
      gzip_level       = logging_openstack.value["gzip_level"]
      message_type     = logging_openstack.value["message_type"]
      name             = logging_openstack.value["name"]
      path             = logging_openstack.value["path"]
      period           = logging_openstack.value["period"]
      public_key       = logging_openstack.value["public_key"]
      timestamp_format = logging_openstack.value["timestamp_format"]
      url              = logging_openstack.value["url"]
      user             = logging_openstack.value["user"]
    }
  }

  dynamic "logging_scalyr" {
    for_each = var.logging_scalyr
    content {
      name   = logging_scalyr.value["name"]
      region = logging_scalyr.value["region"]
      token  = logging_scalyr.value["token"]
    }
  }

  dynamic "logging_sftp" {
    for_each = var.logging_sftp
    content {
      address          = logging_sftp.value["address"]
      gzip_level       = logging_sftp.value["gzip_level"]
      message_type     = logging_sftp.value["message_type"]
      name             = logging_sftp.value["name"]
      password         = logging_sftp.value["password"]
      path             = logging_sftp.value["path"]
      period           = logging_sftp.value["period"]
      port             = logging_sftp.value["port"]
      public_key       = logging_sftp.value["public_key"]
      secret_key       = logging_sftp.value["secret_key"]
      ssh_known_hosts  = logging_sftp.value["ssh_known_hosts"]
      timestamp_format = logging_sftp.value["timestamp_format"]
      user             = logging_sftp.value["user"]
    }
  }

  dynamic "package" {
    for_each = var.package
    content {
      filename         = package.value["filename"]
      source_code_hash = package.value["source_code_hash"]
    }
  }

  dynamic "papertrail" {
    for_each = var.papertrail
    content {
      address = papertrail.value["address"]
      name    = papertrail.value["name"]
      port    = papertrail.value["port"]
    }
  }

  dynamic "s3logging" {
    for_each = var.s3logging
    content {
      bucket_name                       = s3logging.value["bucket_name"]
      domain                            = s3logging.value["domain"]
      gzip_level                        = s3logging.value["gzip_level"]
      message_type                      = s3logging.value["message_type"]
      name                              = s3logging.value["name"]
      path                              = s3logging.value["path"]
      period                            = s3logging.value["period"]
      public_key                        = s3logging.value["public_key"]
      redundancy                        = s3logging.value["redundancy"]
      s3_access_key                     = s3logging.value["s3_access_key"]
      s3_secret_key                     = s3logging.value["s3_secret_key"]
      server_side_encryption            = s3logging.value["server_side_encryption"]
      server_side_encryption_kms_key_id = s3logging.value["server_side_encryption_kms_key_id"]
      timestamp_format                  = s3logging.value["timestamp_format"]
    }
  }

  dynamic "splunk" {
    for_each = var.splunk
    content {
      name            = splunk.value["name"]
      tls_ca_cert     = splunk.value["tls_ca_cert"]
      tls_client_cert = splunk.value["tls_client_cert"]
      tls_client_key  = splunk.value["tls_client_key"]
      tls_hostname    = splunk.value["tls_hostname"]
      token           = splunk.value["token"]
      url             = splunk.value["url"]
    }
  }

  dynamic "sumologic" {
    for_each = var.sumologic
    content {
      message_type = sumologic.value["message_type"]
      name         = sumologic.value["name"]
      url          = sumologic.value["url"]
    }
  }

  dynamic "syslog" {
    for_each = var.syslog
    content {
      address         = syslog.value["address"]
      message_type    = syslog.value["message_type"]
      name            = syslog.value["name"]
      port            = syslog.value["port"]
      tls_ca_cert     = syslog.value["tls_ca_cert"]
      tls_client_cert = syslog.value["tls_client_cert"]
      tls_client_key  = syslog.value["tls_client_key"]
      tls_hostname    = syslog.value["tls_hostname"]
      token           = syslog.value["token"]
      use_tls         = syslog.value["use_tls"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "active_version" {
  description = "returns a number"
  value       = fastly_service_compute.this.active_version
}

output "cloned_version" {
  description = "returns a number"
  value       = fastly_service_compute.this.cloned_version
}

output "id" {
  description = "returns a string"
  value       = fastly_service_compute.this.id
}

output "this" {
  value = fastly_service_compute.this
}
```

[top](#index)