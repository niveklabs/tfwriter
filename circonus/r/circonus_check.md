# circonus_check

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
module "circonus_check" {
  source = "./modules/circonus/r/circonus_check"

  # active - (optional) is a type of bool
  active = null
  # metric_limit - (optional) is a type of number
  metric_limit = null
  # name - (optional) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # period - (optional) is a type of string
  period = null
  # tags - (optional) is a type of set of string
  tags = []
  # target - (optional) is a type of string
  target = null
  # timeout - (optional) is a type of string
  timeout = null
  # type - (optional) is a type of string
  type = null

  caql = [{
    query = null
  }]

  cloudwatch = [{
    api_key     = null
    api_secret  = null
    dimmensions = {}
    metric      = []
    namespace   = null
    url         = null
    version     = null
  }]

  collector = [{
    id = null
  }]

  consul = [{
    acl_token         = null
    allow_stale       = null
    ca_chain          = null
    certificate_file  = null
    check_blacklist   = []
    ciphers           = null
    dc                = null
    headers           = {}
    http_addr         = null
    key_file          = null
    node              = null
    node_blacklist    = []
    service           = null
    service_blacklist = []
    state             = null
  }]

  dns = [{
    ctype      = null
    nameserver = null
    query      = null
    rtype      = null
  }]

  external = [{
    arg1           = null
    arg10          = null
    arg2           = null
    arg3           = null
    arg4           = null
    arg5           = null
    arg6           = null
    arg7           = null
    arg8           = null
    arg9           = null
    command        = null
    env            = {}
    output_extract = null
  }]

  http = [{
    auth_method      = null
    auth_password    = null
    auth_user        = null
    body_regexp      = null
    ca_chain         = null
    certificate_file = null
    ciphers          = null
    code             = null
    extract          = null
    headers          = {}
    key_file         = null
    method           = null
    payload          = null
    read_limit       = null
    redirects        = null
    url              = null
    version          = null
  }]

  httptrap = [{
    async_metrics = null
    secret        = null
  }]

  icmp_ping = [{
    availability = null
    count        = null
    interval     = null
  }]

  jmx = [{
    host          = null
    mbean_domains = []
    mbean_properties = [{
      index = null
      name  = null
      type  = null
    }]
    password = null
    port     = null
    uri      = null
    username = null
  }]

  json = [{
    auth_method      = null
    auth_password    = null
    auth_user        = null
    ca_chain         = null
    certificate_file = null
    ciphers          = null
    headers          = {}
    key_file         = null
    method           = null
    payload          = null
    port             = null
    read_limit       = null
    url              = null
    version          = null
  }]

  memcached = [{
    port = null
  }]

  metric = [{
    active = null
    name   = null
    type   = null
  }]

  metric_filter = [{
    comment   = null
    regex     = null
    tag_query = null
    type      = null
  }]

  mysql = [{
    dsn   = null
    query = null
  }]

  ntp = [{
    port        = null
    use_control = null
  }]

  postgresql = [{
    dsn   = null
    query = null
  }]

  promtext = [{
    port = null
    url  = null
  }]

  redis = [{
    command  = null
    db_index = null
    password = null
    port     = null
  }]

  smtp = [{
    ehlo                 = null
    from                 = null
    payload              = null
    port                 = null
    proxy_dest_address   = null
    proxy_dest_port      = null
    proxy_family         = null
    proxy_protocol       = null
    proxy_source_address = null
    proxy_source_port    = null
    sasl_auth_id         = null
    sasl_authentication  = null
    sasl_password        = null
    sasl_user            = null
    starttls             = null
    to                   = null
  }]

  snmp = [{
    auth_passphrase = null
    auth_protocol   = null
    community       = null
    context_engine  = null
    context_name    = null
    oid = [{
      name = null
      path = null
      type = null
    }]
    port               = null
    privacy_passphrase = null
    privacy_protocol   = null
    security_engine    = null
    security_level     = null
    security_name      = null
    separate_queries   = null
    version            = null
  }]

  statsd = [{
    source_ip = null
  }]

  tcp = [{
    banner_regexp    = null
    ca_chain         = null
    certificate_file = null
    ciphers          = null
    host             = null
    key_file         = null
    port             = null
    tls              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional) - If the check is activate or disabled"
  type        = bool
  default     = null
}

variable "metric_limit" {
  description = "(optional) - Setting a metric_limit will enable all (-1), disable (0), or allow up to the specified limit of metrics for this check (\"N+\", where N is a positive integer)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional) - The name of the check bundle that will be displayed in the web interface"
  type        = string
  default     = null
}

variable "notes" {
  description = "(optional) - Notes about this check bundle"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional) - The period between each time the check is made"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tags assigned to the check"
  type        = set(string)
  default     = null
}

variable "target" {
  description = "(optional) - The target of the check (e.g. hostname, URL, IP, etc)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional) - The length of time in seconds (and fractions of a second) before the check will timeout if no response is returned to the collector"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - The check type"
  type        = string
  default     = null
}

variable "caql" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      query = string
    }
  ))
  default = []
}

variable "cloudwatch" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      api_key     = string
      api_secret  = string
      dimmensions = map(string)
      metric      = set(string)
      namespace   = string
      url         = string
      version     = string
    }
  ))
  default = []
}

variable "collector" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id = string
    }
  ))
  default = []
}

variable "consul" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      acl_token         = string
      allow_stale       = bool
      ca_chain          = string
      certificate_file  = string
      check_blacklist   = list(string)
      ciphers           = string
      dc                = string
      headers           = map(string)
      http_addr         = string
      key_file          = string
      node              = string
      node_blacklist    = list(string)
      service           = string
      service_blacklist = list(string)
      state             = string
    }
  ))
  default = []
}

variable "dns" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      ctype      = string
      nameserver = string
      query      = string
      rtype      = string
    }
  ))
  default = []
}

variable "external" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      arg1           = string
      arg10          = string
      arg2           = string
      arg3           = string
      arg4           = string
      arg5           = string
      arg6           = string
      arg7           = string
      arg8           = string
      arg9           = string
      command        = string
      env            = map(string)
      output_extract = string
    }
  ))
  default = []
}

variable "http" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      auth_method      = string
      auth_password    = string
      auth_user        = string
      body_regexp      = string
      ca_chain         = string
      certificate_file = string
      ciphers          = string
      code             = string
      extract          = string
      headers          = map(string)
      key_file         = string
      method           = string
      payload          = string
      read_limit       = number
      redirects        = string
      url              = string
      version          = string
    }
  ))
  default = []
}

variable "httptrap" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      async_metrics = bool
      secret        = string
    }
  ))
  default = []
}

variable "icmp_ping" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      availability = number
      count        = number
      interval     = string
    }
  ))
  default = []
}

variable "jmx" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      host          = string
      mbean_domains = list(string)
      mbean_properties = list(object(
        {
          index = string
          name  = string
          type  = string
        }
      ))
      password = string
      port     = number
      uri      = string
      username = string
    }
  ))
  default = []
}

variable "json" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      auth_method      = string
      auth_password    = string
      auth_user        = string
      ca_chain         = string
      certificate_file = string
      ciphers          = string
      headers          = map(string)
      key_file         = string
      method           = string
      payload          = string
      port             = number
      read_limit       = number
      url              = string
      version          = string
    }
  ))
  default = []
}

variable "memcached" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      port = number
    }
  ))
  default = []
}

variable "metric" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      active = bool
      name   = string
      type   = string
    }
  ))
  default = []
}

variable "metric_filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comment   = string
      regex     = string
      tag_query = string
      type      = string
    }
  ))
  default = []
}

variable "mysql" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      dsn   = string
      query = string
    }
  ))
  default = []
}

variable "ntp" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      port        = number
      use_control = bool
    }
  ))
  default = []
}

variable "postgresql" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      dsn   = string
      query = string
    }
  ))
  default = []
}

variable "promtext" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      port = number
      url  = string
    }
  ))
  default = []
}

variable "redis" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      command  = string
      db_index = number
      password = string
      port     = number
    }
  ))
  default = []
}

variable "smtp" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      ehlo                 = string
      from                 = string
      payload              = string
      port                 = number
      proxy_dest_address   = string
      proxy_dest_port      = number
      proxy_family         = string
      proxy_protocol       = bool
      proxy_source_address = string
      proxy_source_port    = number
      sasl_auth_id         = string
      sasl_authentication  = string
      sasl_password        = string
      sasl_user            = string
      starttls             = bool
      to                   = string
    }
  ))
  default = []
}

variable "snmp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_passphrase = string
      auth_protocol   = string
      community       = string
      context_engine  = string
      context_name    = string
      oid = list(object(
        {
          name = string
          path = string
          type = string
        }
      ))
      port               = number
      privacy_passphrase = string
      privacy_protocol   = string
      security_engine    = string
      security_level     = string
      security_name      = string
      separate_queries   = bool
      version            = string
    }
  ))
  default = []
}

variable "statsd" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      source_ip = string
    }
  ))
  default = []
}

variable "tcp" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      banner_regexp    = string
      ca_chain         = string
      certificate_file = string
      ciphers          = string
      host             = string
      key_file         = string
      port             = number
      tls              = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "circonus_check" "this" {
  # active - (optional) is a type of bool
  active = var.active
  # metric_limit - (optional) is a type of number
  metric_limit = var.metric_limit
  # name - (optional) is a type of string
  name = var.name
  # notes - (optional) is a type of string
  notes = var.notes
  # period - (optional) is a type of string
  period = var.period
  # tags - (optional) is a type of set of string
  tags = var.tags
  # target - (optional) is a type of string
  target = var.target
  # timeout - (optional) is a type of string
  timeout = var.timeout
  # type - (optional) is a type of string
  type = var.type

  dynamic "caql" {
    for_each = var.caql
    content {
      # query - (required) is a type of string
      query = caql.value["query"]
    }
  }

  dynamic "cloudwatch" {
    for_each = var.cloudwatch
    content {
      # api_key - (optional) is a type of string
      api_key = cloudwatch.value["api_key"]
      # api_secret - (optional) is a type of string
      api_secret = cloudwatch.value["api_secret"]
      # dimmensions - (required) is a type of map of string
      dimmensions = cloudwatch.value["dimmensions"]
      # metric - (required) is a type of set of string
      metric = cloudwatch.value["metric"]
      # namespace - (required) is a type of string
      namespace = cloudwatch.value["namespace"]
      # url - (required) is a type of string
      url = cloudwatch.value["url"]
      # version - (optional) is a type of string
      version = cloudwatch.value["version"]
    }
  }

  dynamic "collector" {
    for_each = var.collector
    content {
      # id - (required) is a type of string
      id = collector.value["id"]
    }
  }

  dynamic "consul" {
    for_each = var.consul
    content {
      # acl_token - (optional) is a type of string
      acl_token = consul.value["acl_token"]
      # allow_stale - (optional) is a type of bool
      allow_stale = consul.value["allow_stale"]
      # ca_chain - (optional) is a type of string
      ca_chain = consul.value["ca_chain"]
      # certificate_file - (optional) is a type of string
      certificate_file = consul.value["certificate_file"]
      # check_blacklist - (optional) is a type of list of string
      check_blacklist = consul.value["check_blacklist"]
      # ciphers - (optional) is a type of string
      ciphers = consul.value["ciphers"]
      # dc - (optional) is a type of string
      dc = consul.value["dc"]
      # headers - (optional) is a type of map of string
      headers = consul.value["headers"]
      # http_addr - (optional) is a type of string
      http_addr = consul.value["http_addr"]
      # key_file - (optional) is a type of string
      key_file = consul.value["key_file"]
      # node - (optional) is a type of string
      node = consul.value["node"]
      # node_blacklist - (optional) is a type of list of string
      node_blacklist = consul.value["node_blacklist"]
      # service - (optional) is a type of string
      service = consul.value["service"]
      # service_blacklist - (optional) is a type of list of string
      service_blacklist = consul.value["service_blacklist"]
      # state - (optional) is a type of string
      state = consul.value["state"]
    }
  }

  dynamic "dns" {
    for_each = var.dns
    content {
      # ctype - (optional) is a type of string
      ctype = dns.value["ctype"]
      # nameserver - (optional) is a type of string
      nameserver = dns.value["nameserver"]
      # query - (required) is a type of string
      query = dns.value["query"]
      # rtype - (optional) is a type of string
      rtype = dns.value["rtype"]
    }
  }

  dynamic "external" {
    for_each = var.external
    content {
      # arg1 - (optional) is a type of string
      arg1 = external.value["arg1"]
      # arg10 - (optional) is a type of string
      arg10 = external.value["arg10"]
      # arg2 - (optional) is a type of string
      arg2 = external.value["arg2"]
      # arg3 - (optional) is a type of string
      arg3 = external.value["arg3"]
      # arg4 - (optional) is a type of string
      arg4 = external.value["arg4"]
      # arg5 - (optional) is a type of string
      arg5 = external.value["arg5"]
      # arg6 - (optional) is a type of string
      arg6 = external.value["arg6"]
      # arg7 - (optional) is a type of string
      arg7 = external.value["arg7"]
      # arg8 - (optional) is a type of string
      arg8 = external.value["arg8"]
      # arg9 - (optional) is a type of string
      arg9 = external.value["arg9"]
      # command - (required) is a type of string
      command = external.value["command"]
      # env - (optional) is a type of map of string
      env = external.value["env"]
      # output_extract - (required) is a type of string
      output_extract = external.value["output_extract"]
    }
  }

  dynamic "http" {
    for_each = var.http
    content {
      # auth_method - (optional) is a type of string
      auth_method = http.value["auth_method"]
      # auth_password - (optional) is a type of string
      auth_password = http.value["auth_password"]
      # auth_user - (optional) is a type of string
      auth_user = http.value["auth_user"]
      # body_regexp - (optional) is a type of string
      body_regexp = http.value["body_regexp"]
      # ca_chain - (optional) is a type of string
      ca_chain = http.value["ca_chain"]
      # certificate_file - (optional) is a type of string
      certificate_file = http.value["certificate_file"]
      # ciphers - (optional) is a type of string
      ciphers = http.value["ciphers"]
      # code - (optional) is a type of string
      code = http.value["code"]
      # extract - (optional) is a type of string
      extract = http.value["extract"]
      # headers - (optional) is a type of map of string
      headers = http.value["headers"]
      # key_file - (optional) is a type of string
      key_file = http.value["key_file"]
      # method - (optional) is a type of string
      method = http.value["method"]
      # payload - (optional) is a type of string
      payload = http.value["payload"]
      # read_limit - (optional) is a type of number
      read_limit = http.value["read_limit"]
      # redirects - (optional) is a type of string
      redirects = http.value["redirects"]
      # url - (required) is a type of string
      url = http.value["url"]
      # version - (optional) is a type of string
      version = http.value["version"]
    }
  }

  dynamic "httptrap" {
    for_each = var.httptrap
    content {
      # async_metrics - (optional) is a type of bool
      async_metrics = httptrap.value["async_metrics"]
      # secret - (optional) is a type of string
      secret = httptrap.value["secret"]
    }
  }

  dynamic "icmp_ping" {
    for_each = var.icmp_ping
    content {
      # availability - (optional) is a type of number
      availability = icmp_ping.value["availability"]
      # count - (optional) is a type of number
      count = icmp_ping.value["count"]
      # interval - (optional) is a type of string
      interval = icmp_ping.value["interval"]
    }
  }

  dynamic "jmx" {
    for_each = var.jmx
    content {
      # host - (required) is a type of string
      host = jmx.value["host"]
      # mbean_domains - (optional) is a type of list of string
      mbean_domains = jmx.value["mbean_domains"]
      # password - (optional) is a type of string
      password = jmx.value["password"]
      # port - (required) is a type of number
      port = jmx.value["port"]
      # uri - (optional) is a type of string
      uri = jmx.value["uri"]
      # username - (optional) is a type of string
      username = jmx.value["username"]

      dynamic "mbean_properties" {
        for_each = jmx.value.mbean_properties
        content {
          # index - (required) is a type of string
          index = mbean_properties.value["index"]
          # name - (required) is a type of string
          name = mbean_properties.value["name"]
          # type - (required) is a type of string
          type = mbean_properties.value["type"]
        }
      }

    }
  }

  dynamic "json" {
    for_each = var.json
    content {
      # auth_method - (optional) is a type of string
      auth_method = json.value["auth_method"]
      # auth_password - (optional) is a type of string
      auth_password = json.value["auth_password"]
      # auth_user - (optional) is a type of string
      auth_user = json.value["auth_user"]
      # ca_chain - (optional) is a type of string
      ca_chain = json.value["ca_chain"]
      # certificate_file - (optional) is a type of string
      certificate_file = json.value["certificate_file"]
      # ciphers - (optional) is a type of string
      ciphers = json.value["ciphers"]
      # headers - (optional) is a type of map of string
      headers = json.value["headers"]
      # key_file - (optional) is a type of string
      key_file = json.value["key_file"]
      # method - (optional) is a type of string
      method = json.value["method"]
      # payload - (optional) is a type of string
      payload = json.value["payload"]
      # port - (optional) is a type of number
      port = json.value["port"]
      # read_limit - (optional) is a type of number
      read_limit = json.value["read_limit"]
      # url - (required) is a type of string
      url = json.value["url"]
      # version - (optional) is a type of string
      version = json.value["version"]
    }
  }

  dynamic "memcached" {
    for_each = var.memcached
    content {
      # port - (optional) is a type of number
      port = memcached.value["port"]
    }
  }

  dynamic "metric" {
    for_each = var.metric
    content {
      # active - (optional) is a type of bool
      active = metric.value["active"]
      # name - (required) is a type of string
      name = metric.value["name"]
      # type - (required) is a type of string
      type = metric.value["type"]
    }
  }

  dynamic "metric_filter" {
    for_each = var.metric_filter
    content {
      # comment - (optional) is a type of string
      comment = metric_filter.value["comment"]
      # regex - (required) is a type of string
      regex = metric_filter.value["regex"]
      # tag_query - (optional) is a type of string
      tag_query = metric_filter.value["tag_query"]
      # type - (required) is a type of string
      type = metric_filter.value["type"]
    }
  }

  dynamic "mysql" {
    for_each = var.mysql
    content {
      # dsn - (required) is a type of string
      dsn = mysql.value["dsn"]
      # query - (required) is a type of string
      query = mysql.value["query"]
    }
  }

  dynamic "ntp" {
    for_each = var.ntp
    content {
      # port - (optional) is a type of number
      port = ntp.value["port"]
      # use_control - (optional) is a type of bool
      use_control = ntp.value["use_control"]
    }
  }

  dynamic "postgresql" {
    for_each = var.postgresql
    content {
      # dsn - (required) is a type of string
      dsn = postgresql.value["dsn"]
      # query - (required) is a type of string
      query = postgresql.value["query"]
    }
  }

  dynamic "promtext" {
    for_each = var.promtext
    content {
      # port - (optional) is a type of number
      port = promtext.value["port"]
      # url - (required) is a type of string
      url = promtext.value["url"]
    }
  }

  dynamic "redis" {
    for_each = var.redis
    content {
      # command - (optional) is a type of string
      command = redis.value["command"]
      # db_index - (optional) is a type of number
      db_index = redis.value["db_index"]
      # password - (optional) is a type of string
      password = redis.value["password"]
      # port - (optional) is a type of number
      port = redis.value["port"]
    }
  }

  dynamic "smtp" {
    for_each = var.smtp
    content {
      # ehlo - (optional) is a type of string
      ehlo = smtp.value["ehlo"]
      # from - (optional) is a type of string
      from = smtp.value["from"]
      # payload - (optional) is a type of string
      payload = smtp.value["payload"]
      # port - (optional) is a type of number
      port = smtp.value["port"]
      # proxy_dest_address - (optional) is a type of string
      proxy_dest_address = smtp.value["proxy_dest_address"]
      # proxy_dest_port - (optional) is a type of number
      proxy_dest_port = smtp.value["proxy_dest_port"]
      # proxy_family - (optional) is a type of string
      proxy_family = smtp.value["proxy_family"]
      # proxy_protocol - (optional) is a type of bool
      proxy_protocol = smtp.value["proxy_protocol"]
      # proxy_source_address - (optional) is a type of string
      proxy_source_address = smtp.value["proxy_source_address"]
      # proxy_source_port - (optional) is a type of number
      proxy_source_port = smtp.value["proxy_source_port"]
      # sasl_auth_id - (optional) is a type of string
      sasl_auth_id = smtp.value["sasl_auth_id"]
      # sasl_authentication - (optional) is a type of string
      sasl_authentication = smtp.value["sasl_authentication"]
      # sasl_password - (optional) is a type of string
      sasl_password = smtp.value["sasl_password"]
      # sasl_user - (optional) is a type of string
      sasl_user = smtp.value["sasl_user"]
      # starttls - (optional) is a type of bool
      starttls = smtp.value["starttls"]
      # to - (required) is a type of string
      to = smtp.value["to"]
    }
  }

  dynamic "snmp" {
    for_each = var.snmp
    content {
      # auth_passphrase - (optional) is a type of string
      auth_passphrase = snmp.value["auth_passphrase"]
      # auth_protocol - (optional) is a type of string
      auth_protocol = snmp.value["auth_protocol"]
      # community - (required) is a type of string
      community = snmp.value["community"]
      # context_engine - (optional) is a type of string
      context_engine = snmp.value["context_engine"]
      # context_name - (optional) is a type of string
      context_name = snmp.value["context_name"]
      # port - (optional) is a type of number
      port = snmp.value["port"]
      # privacy_passphrase - (optional) is a type of string
      privacy_passphrase = snmp.value["privacy_passphrase"]
      # privacy_protocol - (optional) is a type of string
      privacy_protocol = snmp.value["privacy_protocol"]
      # security_engine - (optional) is a type of string
      security_engine = snmp.value["security_engine"]
      # security_level - (optional) is a type of string
      security_level = snmp.value["security_level"]
      # security_name - (optional) is a type of string
      security_name = snmp.value["security_name"]
      # separate_queries - (optional) is a type of bool
      separate_queries = snmp.value["separate_queries"]
      # version - (required) is a type of string
      version = snmp.value["version"]

      dynamic "oid" {
        for_each = snmp.value.oid
        content {
          # name - (required) is a type of string
          name = oid.value["name"]
          # path - (required) is a type of string
          path = oid.value["path"]
          # type - (optional) is a type of string
          type = oid.value["type"]
        }
      }

    }
  }

  dynamic "statsd" {
    for_each = var.statsd
    content {
      # source_ip - (required) is a type of string
      source_ip = statsd.value["source_ip"]
    }
  }

  dynamic "tcp" {
    for_each = var.tcp
    content {
      # banner_regexp - (optional) is a type of string
      banner_regexp = tcp.value["banner_regexp"]
      # ca_chain - (optional) is a type of string
      ca_chain = tcp.value["ca_chain"]
      # certificate_file - (optional) is a type of string
      certificate_file = tcp.value["certificate_file"]
      # ciphers - (optional) is a type of string
      ciphers = tcp.value["ciphers"]
      # host - (required) is a type of string
      host = tcp.value["host"]
      # key_file - (optional) is a type of string
      key_file = tcp.value["key_file"]
      # port - (required) is a type of number
      port = tcp.value["port"]
      # tls - (optional) is a type of bool
      tls = tcp.value["tls"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "check_by_collector" {
  description = "returns a map of string"
  value       = circonus_check.this.check_by_collector
}

output "check_id" {
  description = "returns a string"
  value       = circonus_check.this.check_id
}

output "checks" {
  description = "returns a list of string"
  value       = circonus_check.this.checks
}

output "created" {
  description = "returns a number"
  value       = circonus_check.this.created
}

output "id" {
  description = "returns a string"
  value       = circonus_check.this.id
}

output "last_modified" {
  description = "returns a number"
  value       = circonus_check.this.last_modified
}

output "last_modified_by" {
  description = "returns a string"
  value       = circonus_check.this.last_modified_by
}

output "metric_limit" {
  description = "returns a number"
  value       = circonus_check.this.metric_limit
}

output "notes" {
  description = "returns a string"
  value       = circonus_check.this.notes
}

output "period" {
  description = "returns a string"
  value       = circonus_check.this.period
}

output "reverse_connect_urls" {
  description = "returns a list of string"
  value       = circonus_check.this.reverse_connect_urls
}

output "target" {
  description = "returns a string"
  value       = circonus_check.this.target
}

output "timeout" {
  description = "returns a string"
  value       = circonus_check.this.timeout
}

output "type" {
  description = "returns a string"
  value       = circonus_check.this.type
}

output "uuids" {
  description = "returns a list of string"
  value       = circonus_check.this.uuids
}

output "this" {
  value = circonus_check.this
}
```

[top](#index)