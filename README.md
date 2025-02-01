# lfkdev.camino_node

An Ansible Role that installs and configures Camino Node on Linux servers.

### Requirements
None.

### Role Variables
Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
github_api_url: "https://api.github.com/repos/chain4travel/caminogo/releases"
```
The URL of the GitHub API to fetch the latest Camino Node release information.

```yaml
camino_node_dir: "/opt/camino-node"
```
The directory where the Camino Node binary will be installed.

```yaml
camino_node_bin: "{{camino_node_dir}}/caminogo"
```
The full path to the Camino Node binary.

```yaml
camino_config_dir: "/etc/camino-node/configs"
```
The directory where the Camino Node configuration files will be stored.

```yaml
camino_config_file: "{{camino_config_dir}}/node.json"
```
The main configuration file for the Camino Node.

```yaml
camino_node_http_host: "127.0.0.1"
```
The HTTP host address for the Camino Node API.

```yaml
camino_node_network_id: "columbus"
```
The network ID for the Camino Node. Defaults to the testnet.

```yaml
camino_version: ""
```
If not set, the role will fetch the latest release. Otherwise, specify the desired version (e.g., `"v1.1.0"`).

```yaml
camino_user: "root"
```
The system user under which the Camino Node runs.

```yaml
camino_group: "root"
```
The system group under which the Camino Node runs.

```yaml
camin_admin_api_secret: ""
```
If set to any value, the admin API endpoint will be enabled; otherwise, it remains disabled.

For more infos visit [docs](https://docs.camino.network/camino-node/configuration/)
 
### Node Keys
Uncomment the following variables to include tasks for custom keys:

```yaml
# camino_staker_key: |
#             "<staker_key>"

# camino_staker_crt: |
#             "<staker_crt>"

# camino_signer_key: |
#             "<signer_key>"
```

### Dependencies
- Currently, only the Debian family is supported (feel free to submit a PR for RedHat).

### Example Playbook
```yaml
- hosts: servers
  roles:
    - { role: lfkdev.camino_node }
```

### License
MIT
