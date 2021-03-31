# consul_agent_self

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_agent_self" {
  source = "./modules/consul/d/consul_agent_self"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "consul_agent_self" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "acl_datacenter" {
  description = "returns a string"
  value       = data.consul_agent_self.this.acl_datacenter
}

output "acl_default_policy" {
  description = "returns a string"
  value       = data.consul_agent_self.this.acl_default_policy
}

output "acl_disabled_ttl" {
  description = "returns a string"
  value       = data.consul_agent_self.this.acl_disabled_ttl
}

output "acl_down_policy" {
  description = "returns a string"
  value       = data.consul_agent_self.this.acl_down_policy
}

output "acl_enforce_0_8_semantics" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.acl_enforce_0_8_semantics
}

output "acl_ttl" {
  description = "returns a string"
  value       = data.consul_agent_self.this.acl_ttl
}

output "addresses" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.addresses
}

output "advertise_addr" {
  description = "returns a string"
  value       = data.consul_agent_self.this.advertise_addr
}

output "advertise_addr_wan" {
  description = "returns a string"
  value       = data.consul_agent_self.this.advertise_addr_wan
}

output "advertise_addrs" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.advertise_addrs
}

output "atlas_join" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.atlas_join
}

output "bind_addr" {
  description = "returns a string"
  value       = data.consul_agent_self.this.bind_addr
}

output "bootstrap_expect" {
  description = "returns a number"
  value       = data.consul_agent_self.this.bootstrap_expect
}

output "bootstrap_mode" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.bootstrap_mode
}

output "check_deregister_interval_min" {
  description = "returns a string"
  value       = data.consul_agent_self.this.check_deregister_interval_min
}

output "check_reap_interval" {
  description = "returns a string"
  value       = data.consul_agent_self.this.check_reap_interval
}

output "check_update_interval" {
  description = "returns a string"
  value       = data.consul_agent_self.this.check_update_interval
}

output "client_addr" {
  description = "returns a string"
  value       = data.consul_agent_self.this.client_addr
}

output "data_dir" {
  description = "returns a string"
  value       = data.consul_agent_self.this.data_dir
}

output "datacenter" {
  description = "returns a string"
  value       = data.consul_agent_self.this.datacenter
}

output "dev_mode" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.dev_mode
}

output "dns" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.dns
}

output "dns_recursors" {
  description = "returns a list of string"
  value       = data.consul_agent_self.this.dns_recursors
}

output "domain" {
  description = "returns a string"
  value       = data.consul_agent_self.this.domain
}

output "enable_anonymous_signature" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.enable_anonymous_signature
}

output "enable_coordinates" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.enable_coordinates
}

output "enable_debug" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.enable_debug
}

output "enable_remote_exec" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.enable_remote_exec
}

output "enable_syslog" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.enable_syslog
}

output "enable_ui" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.enable_ui
}

output "enable_update_check" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.enable_update_check
}

output "id" {
  description = "returns a string"
  value       = data.consul_agent_self.this.id
}

output "leave_on_int" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.leave_on_int
}

output "leave_on_term" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.leave_on_term
}

output "log_level" {
  description = "returns a string"
  value       = data.consul_agent_self.this.log_level
}

output "name" {
  description = "returns a string"
  value       = data.consul_agent_self.this.name
}

output "performance" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.performance
}

output "pid_file" {
  description = "returns a string"
  value       = data.consul_agent_self.this.pid_file
}

output "ports" {
  description = "returns a map of number"
  value       = data.consul_agent_self.this.ports
}

output "protocol_version" {
  description = "returns a number"
  value       = data.consul_agent_self.this.protocol_version
}

output "reconnect_timeout_lan" {
  description = "returns a string"
  value       = data.consul_agent_self.this.reconnect_timeout_lan
}

output "reconnect_timeout_wan" {
  description = "returns a string"
  value       = data.consul_agent_self.this.reconnect_timeout_wan
}

output "rejoin_after_leave" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.rejoin_after_leave
}

output "retry_join" {
  description = "returns a list of string"
  value       = data.consul_agent_self.this.retry_join
}

output "retry_join_ec2" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.retry_join_ec2
}

output "retry_join_gce" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.retry_join_gce
}

output "retry_join_wan" {
  description = "returns a list of string"
  value       = data.consul_agent_self.this.retry_join_wan
}

output "retry_max_attempts" {
  description = "returns a number"
  value       = data.consul_agent_self.this.retry_max_attempts
}

output "retry_max_attempts_wan" {
  description = "returns a number"
  value       = data.consul_agent_self.this.retry_max_attempts_wan
}

output "serf_lan_bind_addr" {
  description = "returns a string"
  value       = data.consul_agent_self.this.serf_lan_bind_addr
}

output "serf_wan_bind_addr" {
  description = "returns a string"
  value       = data.consul_agent_self.this.serf_wan_bind_addr
}

output "server_mode" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.server_mode
}

output "server_name" {
  description = "returns a string"
  value       = data.consul_agent_self.this.server_name
}

output "session_ttl_min" {
  description = "returns a string"
  value       = data.consul_agent_self.this.session_ttl_min
}

output "start_join" {
  description = "returns a list of string"
  value       = data.consul_agent_self.this.start_join
}

output "start_join_wan" {
  description = "returns a list of string"
  value       = data.consul_agent_self.this.start_join_wan
}

output "syslog_facility" {
  description = "returns a string"
  value       = data.consul_agent_self.this.syslog_facility
}

output "tagged_addresses" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.tagged_addresses
}

output "telemetry" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.telemetry
}

output "tls_ca_file" {
  description = "returns a string"
  value       = data.consul_agent_self.this.tls_ca_file
}

output "tls_cert_file" {
  description = "returns a string"
  value       = data.consul_agent_self.this.tls_cert_file
}

output "tls_key_file" {
  description = "returns a string"
  value       = data.consul_agent_self.this.tls_key_file
}

output "tls_min_version" {
  description = "returns a string"
  value       = data.consul_agent_self.this.tls_min_version
}

output "tls_verify_incoming" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.tls_verify_incoming
}

output "tls_verify_outgoing" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.tls_verify_outgoing
}

output "tls_verify_server_hostname" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.tls_verify_server_hostname
}

output "translate_wan_addrs" {
  description = "returns a bool"
  value       = data.consul_agent_self.this.translate_wan_addrs
}

output "ui_dir" {
  description = "returns a string"
  value       = data.consul_agent_self.this.ui_dir
}

output "unix_sockets" {
  description = "returns a map of string"
  value       = data.consul_agent_self.this.unix_sockets
}

output "version" {
  description = "returns a string"
  value       = data.consul_agent_self.this.version
}

output "version_prerelease" {
  description = "returns a string"
  value       = data.consul_agent_self.this.version_prerelease
}

output "version_revision" {
  description = "returns a string"
  value       = data.consul_agent_self.this.version_revision
}

output "this" {
  value = consul_agent_self.this
}
```

[top](#index)