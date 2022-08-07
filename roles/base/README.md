# Base role

Sets up the base configuration for each service. This applies to all hosts.

## Steps

- Sets the hostname for the host. This can be configure via `hostname` variable, otherwise it's set to the hosts name in the inventory file (`inventory_hostname`)
- Configures the package manager on Fedora, by enabling `deltarpm`, `fastestmirror` and setting `max_parallel_downloads`
- Updates all packages on the system to latest
- Installs a set of base packages, configurable via the `base_packages` variable, and `dnf_base_packages` / `apt_base_packages` for specific ones
- Sets up `zsh`, using `oh-my-zsh`:
    - Sets the theme based on `zsh_theme`
    - Enables hyphen insensitivity, auto updates, `~/.local/bin` in PATH
    - Downloads and enables `zsh-syntax-highlighting` and `zsh-autocomplete`
    - Creates and sources a `.aliases` file. Custom aliases can be added through `custom_aliases` variable
- Sets up an ssh key on the host, and adds it to github if `github_access_token` is provided. To create a Github access token, follow instructions [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token), and make sure the token has the `admin:public_key` permission
