Ansible role: Prometheus Exporter - Blackbox
============================================

Install and configure Blackbox Exporter for Prometheus.

Requirements
------------

This role depends on the [base prometheus exporter role](https://github.com/wandansible/prometheus_exporter).


Role Variables
--------------

```
ENTRY POINT: *main* - Install and configure Blackbox Exporter for Prometheus

Options (= indicates it is required):

- blackbox_exporter_arch_map  Mapping of the possible values of
                               ansible_architecture to the exporter
                               package architectures
          default: null
          type: dict

- blackbox_exporter_archive_urls  Override the list of exporter
                                   archive urls for different
                                   platforms and architectures
          default: null
          elements: str
          type: list

- blackbox_exporter_bin_dir  Directory for the exporter executable
          default: null
          type: str

- blackbox_exporter_binary  Filename for the exporter executable
          default: null
          type: str

- blackbox_exporter_checksum_type  The exporter package checksum type
          default: null
          type: str

- blackbox_exporter_checksum_url  Override the URL for the exporter
                                   checksum file
          default: null
          type: str

- blackbox_exporter_checksums  Override exporter archive checksums
                                file contents
          default: null
          type: str

- blackbox_exporter_clean_src_dir  Remove old downloaded archive
                                    files from exporter src directory
          default: true
          type: bool

- blackbox_exporter_config_file  Path for configuration file
          default: /etc/prometheus/exporters/blackbox/config.yml
          type: str

- blackbox_exporter_configure_caddy  If true, configure caddy to add
                                      a TLS endpoint for the exporter
          default: false
          type: bool

- blackbox_exporter_default_modules  Default modules to configure for
                                      blackbox exporter. Defaults to a
                                      combination of
                                      blackbox_exporter_default_modules_http,
                                      blackbox_exporter_default_modules_icmp
                                      and
                                      blackbox_exporter_default_modules_tcp.
                                      For more information see
                                      https://github.com/prometheus/blackbox_exporter/blob/master/CONFIGURATION.md
          default: null
          elements: dict
          type: list
          options:

          = config  Blackbox module configuration
            type: dict
            options:

            - dns  Specific configuration for DNS prober
              default: null
              type: str

            - grpc  Specific configuration for GRPC prober
              default: null
              type: str

            - http  Specific configuration for HTTP prober
              default: null
              type: str

            - icmp  Specific configuration for ICMP prober
              default: null
              type: str

            = prober  The protocol over which the probe will take
                       place (http, tcp, dns, icmp, grpc)
              type: str

            - tcp  Specific configuration for TCP prober
              default: null
              type: str

            - timeout  How long the probe will wait before giving up
              default: null
              type: str

          = name  Blackbox module name
            type: str

- blackbox_exporter_default_modules_http  Default HTTP prober modules
                                           to configure for blackbox
                                           exporter.
                                           For more information see
                                           https://github.com/prometheus/blackbox_exporter/blob/master/CONFIGURATION.md
          default: null
          elements: dict
          type: list
          options:

          = config  Blackbox module configuration
            type: dict
            options:

            - dns  Specific configuration for DNS prober
              default: null
              type: str

            - grpc  Specific configuration for GRPC prober
              default: null
              type: str

            - http  Specific configuration for HTTP prober
              default: null
              type: str

            - icmp  Specific configuration for ICMP prober
              default: null
              type: str

            = prober  The protocol over which the probe will take
                       place (http, tcp, dns, icmp, grpc)
              type: str

            - tcp  Specific configuration for TCP prober
              default: null
              type: str

            - timeout  How long the probe will wait before giving up
              default: null
              type: str

          = name  Blackbox module name
            type: str

- blackbox_exporter_default_modules_icmp  Default ICMP prober modules
                                           to configure for blackbox
                                           exporter.
                                           For more information see
                                           https://github.com/prometheus/blackbox_exporter/blob/master/CONFIGURATION.md
          default: null
          elements: dict
          type: list
          options:

          = config  Blackbox module configuration
            type: dict
            options:

            - dns  Specific configuration for DNS prober
              default: null
              type: str

            - grpc  Specific configuration for GRPC prober
              default: null
              type: str

            - http  Specific configuration for HTTP prober
              default: null
              type: str

            - icmp  Specific configuration for ICMP prober
              default: null
              type: str

            = prober  The protocol over which the probe will take
                       place (http, tcp, dns, icmp, grpc)
              type: str

            - tcp  Specific configuration for TCP prober
              default: null
              type: str

            - timeout  How long the probe will wait before giving up
              default: null
              type: str

          = name  Blackbox module name
            type: str

- blackbox_exporter_default_modules_tcp  Default TCP prober modules
                                          to configure for blackbox
                                          exporter.
                                          For more information see
                                          https://github.com/prometheus/blackbox_exporter/blob/master/CONFIGURATION.md
          default: null
          elements: dict
          type: list
          options:

          = config  Blackbox module configuration
            type: dict
            options:

            - dns  Specific configuration for DNS prober
              default: null
              type: str

            - grpc  Specific configuration for GRPC prober
              default: null
              type: str

            - http  Specific configuration for HTTP prober
              default: null
              type: str

            - icmp  Specific configuration for ICMP prober
              default: null
              type: str

            = prober  The protocol over which the probe will take
                       place (http, tcp, dns, icmp, grpc)
              type: str

            - tcp  Specific configuration for TCP prober
              default: null
              type: str

            - timeout  How long the probe will wait before giving up
              default: null
              type: str

          = name  Blackbox module name
            type: str

- blackbox_exporter_description  Description for the exporter systemd
                                  service
          default: null
          type: str

- blackbox_exporter_extra_flags  Extra flags to run exporter with
          default: null
          type: dict

- blackbox_exporter_file_sd_dir  Directory, on scrape servers, for
                                  the file service discovery target
          default: /etc/prometheus/file_sd/blackbox_exporter
          type: str

- blackbox_exporter_file_sd_probe_dir  Directory, on scrape servers,
                                        for the file service discovery
                                        probe targets
          default: /etc/prometheus/file_sd/blackbox_exporter/probe
          type: str

- blackbox_exporter_flags  List of flags to run exporter with, as
                            string or list
          default: null
          type: raw

- blackbox_exporter_github_checksum_filename  Filename for the
                                               exporter package
                                               checksums file on
                                               github
          default: null
          type: str

- blackbox_exporter_github_org  Name of organisation for exporter
                                 github repository
          default: prometheus
          type: str

- blackbox_exporter_github_repo  Name of exporter github repository
          default: null
          type: str

- blackbox_exporter_group  Name of the exporter unix group
          default: null
          type: str

- blackbox_exporter_groups  Unix groups added to exporter unix user
          default: null
          elements: str
          type: list

- blackbox_exporter_handler  Name of the exporter handler to notify
          default: null
          type: str

- blackbox_exporter_install  If true, install exporter
          default: true
          type: bool

- blackbox_exporter_labels  Labels added to exporter metrics,
                             overrides prometheus_labels
          default: null
          type: dict

- blackbox_exporter_listen_addresses  Listen address and port
          default: ['localhost:9115']
          elements: str
          type: list

- blackbox_exporter_log_level  Only log messages with the given
                                severity or above
          choices: [debug, info, warn, error]
          default: warn
          type: str

- blackbox_exporter_manage_user  If true, add exporter unix user and
                                  group
          default: true
          type: bool

- blackbox_exporter_modules  Configuration for blackbox modules, as a
                              string or dict.
                              Defaults to a IP address family version
                              of each module defined in
                              blackbox_exporter_default_modules.
                              For more information see
                              https://github.com/prometheus/blackbox_exporter/blob/master/CONFIGURATION.md
          default: null
          type: raw

- blackbox_exporter_modules_address_families  List of IP address
                                               families to configure
                                               modules for
          default: [ip4, ip6]
          elements: str
          type: list

- blackbox_exporter_port  Listen port
          default: 9115
          type: int

- blackbox_exporter_probe_targets  Endpoints for an external blackbox
                                    exporter server to target
          default: null
          elements: dict
          type: list
          options:

          = targets  Targets and labels
            elements: dict
            type: list
            options:

            - labels  Labels added to metrics (defaults to
                       blackbox_exporter_labels)
              default: null
              type: dict

            = targets  Endpoints to target
              elements: str
              type: list

          = type  Probe type or protocol
            type: str

- blackbox_exporter_register  If true, register the exporter with the
                               scrape servers
          default: false
          type: bool

- blackbox_exporter_scrape_servers  List of servers that scrape
                                     exporter metrics from the host,
                                     overrides
                                     prometheus_scrape_servers
          default: null
          elements: str
          type: list

- blackbox_exporter_service  Name of the exporter systemd service
          default: null
          type: str

- blackbox_exporter_service_unit_file  Contents of the systemd unit
                                        file for the exporter
          default: null
          type: str

- blackbox_exporter_src_dir  Directory for the downloaded exporter
                              src archive
          default: null
          type: str

- blackbox_exporter_strip_components  Strip NUMBER leading components
                                       from file names on extraction
          default: 1
          type: int

- blackbox_exporter_target  Scrape target hostname and port
          default: null
          type: str

- blackbox_exporter_user  Name of the exporter unix user
          default: null
          type: str

- blackbox_exporter_version  Version to install (use "latest" for the
                              latest version)
          default: latest
          type: str
```

Installation
------------

This role can either be installed manually with the ansible-galaxy CLI tool:

    ansible-galaxy install git+https://github.com/wandansible/prometheus_exporter,main,wandansible.prometheus_exporter
    ansible-galaxy install git+https://github.com/wandansible/prometheus_exporter.blackbox,main,wandansible.prometheus_exporter.blackbox
     
Or, by adding the following to `requirements.yml`:

    - name: wandansible.prometheus_exporter
      src: https://github.com/wandansible/prometheus_exporter
    - name: wandansible.prometheus_exporter.blackbox
      src: https://github.com/wandansible/prometheus_exporter.blackbox

Roles listed in `requirements.yml` can be installed with the following ansible-galaxy command:

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

    - hosts: blackbox_hosts
      roles:
         - role: wandansible.prometheus_exporter.blackbox
           become: true
