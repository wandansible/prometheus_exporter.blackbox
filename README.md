Ansible role: Prometheus Exporter - Blackbox
============================================

Install and configure Blackbox Exporter for Prometheus.

Requirements
------------

This role depends on the [base prometheus exporter role](https://github.com/wandansible/prometheus_exporter).


Role Variables
--------------

```
ENTRY POINT: main - Install and configure Blackbox Exporter for Prometheus

OPTIONS (= is mandatory):

- blackbox_exporter_add_extract_dir
        If true, add an extraction directory for the exporter package
        default: false
        type: bool

- blackbox_exporter_arch_map
        Mapping of the possible values of ansible_architecture to the
        exporter package architectures
        default: null
        type: dict

- blackbox_exporter_bin_dir
        Directory for the exporter executable
        default: null
        type: str

- blackbox_exporter_binary
        Filename for the exporter executable
        default: null
        type: str

- blackbox_exporter_checksum
        The exporter package checksum
        default: null
        type: str

- blackbox_exporter_checksum_type
        The exporter package checksum type
        default: null
        type: str

- blackbox_exporter_checksums_file
        Filename for the exporter package checksums
        default: null
        type: str

- blackbox_exporter_checksums_url
        URL for the exporter package checksums
        default: null
        type: str

- blackbox_exporter_config_file
        Path for configuration file
        default: /etc/blackbox_exporter/config.yml
        type: str

- blackbox_exporter_configure_caddy
        If true, configure caddy to add a TLS endpoint for the
        exporter
        default: false
        type: bool

- blackbox_exporter_description
        Description for the exporter systemd service
        default: null
        type: str

- blackbox_exporter_extra_flags
        Extra flags to run exporter with
        default: null
        type: dict

- blackbox_exporter_file_sd_dir
        Directory, on scrape servers, for the file service discovery
        target
        default: /etc/prometheus/file_sd/blackbox_exporter
        type: str

- blackbox_exporter_file_sd_probe_dir
        Directory, on scrape servers, for the file service discovery
        probe targets
        default: /etc/prometheus/file_sd/blackbox_exporter/probe
        type: str

- blackbox_exporter_flags
        Contents or list of flags to run exporter with
        default: null
        type: raw

- blackbox_exporter_git_org
        Name of organisation for exporter git repository
        default: null
        type: str

- blackbox_exporter_git_repo
        Name of exporter git repository
        default: null
        type: str

- blackbox_exporter_group
        Name of the exporter unix group
        default: null
        type: str

- blackbox_exporter_groups
        Unix groups added to exporter unix user
        default: null
        elements: str
        type: list

- blackbox_exporter_install
        If true, install exporter
        default: false
        type: bool

- blackbox_exporter_labels
        Labels added to exporter metrics, overrides prometheus_labels
        default: null
        type: dict

- blackbox_exporter_latest_url
        URL for the latest version
        default: null
        type: str

- blackbox_exporter_listen_addresses
        Listen address and port
        default: ['localhost:9115']
        elements: str
        type: list

- blackbox_exporter_log_level
        Only log messages with the given severity or above
        choices: [debug, info, warn, error]
        default: warn
        type: str

- blackbox_exporter_manage_user
        If true, add exporter unix user and group
        default: true
        type: bool

- blackbox_exporter_modules
        Configuration for modules to enable, see https://github.com/pr
        ometheus/blackbox_exporter/blob/master/CONFIGURATION.md
        default: null
        type: dict

- blackbox_exporter_package
        Filename of the exporter package (without extension)
        default: null
        type: str

- blackbox_exporter_package_dir
        Directory the exporter package is extracted to
        default: null
        type: str

- blackbox_exporter_package_name
        Name of the exporter package
        default: null
        type: str

- blackbox_exporter_package_url
        URL for the exporter package
        default: null
        type: str

- blackbox_exporter_port
        Listen port
        default: 9115
        type: int

- blackbox_exporter_probe_targets
        Endpoints for an external blackbox exporter server to target
        default: null
        elements: dict
        type: list

        OPTIONS:

        = targets
            Targets and labels
            elements: dict
            type: list

            OPTIONS:

            - labels
                Labels added to metrics (defaults to
                blackbox_exporter_labels)
                default: null
                type: dict

            = targets
                Endpoints to target
                elements: str
                type: list

        = type
            Probe type or protocol
            type: str

- blackbox_exporter_register
        If true, register the exporter with the scrape servers
        default: false
        type: bool

- blackbox_exporter_scrape_servers
        List of servers that scrape exporter metrics from the host,
        overrides prometheus_scrape_servers
        default: null
        elements: str
        type: list

- blackbox_exporter_service
        Name of the exporter systemd service
        default: null
        type: str

- blackbox_exporter_src_dir
        Directory for the exporter downloads
        default: null
        type: str

- blackbox_exporter_tag
        Version git tag
        default: null
        type: str

- blackbox_exporter_target
        Scrape target hostname and port
        default: null
        type: str

- blackbox_exporter_user
        Name of the exporter unix user
        default: null
        type: str

- blackbox_exporter_version
        Version to install (use "latest" for the latest version)
        default: latest
        type: str

- blackbox_exporter_version_regex
        Regular expression for capturing the version from the latest
        tag
        default: null
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
