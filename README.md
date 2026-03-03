# Learning - Shopware 6 Project

A Shopware 6.7.8.0 development environment powered by DDEV.

## Requirements

- [DDEV](https://ddev.com/) (v1.24+)
- [Docker](https://www.docker.com/)

## Getting Started

```bash
ddev start
```

Once running, the project is available at:

| Service       | URL                                  |
|---------------|--------------------------------------|
| Storefront    | https://learning.ddev.site           |
| Admin Panel   | https://learning.ddev.site/admin     |
| Mailpit       | https://learning.ddev.site:8026      |

**Default admin credentials:** `admin` / `shopware`

## Stack

| Component  | Version     |
|------------|-------------|
| Shopware   | 6.7.8.0     |
| PHP        | 8.3         |
| MariaDB    | 10.11       |
| Node.js    | 22          |
| Web Server | nginx-fpm   |
| Composer   | 2           |

## Common Commands

```bash
# Start / stop the project
ddev start
ddev stop

# Shopware CLI
ddev exec console <command>

# Composer
ddev composer require <package>

# Rebuild JS assets (admin + storefront)
ddev exec bin/build-js.sh

# Compile storefront theme only
ddev exec console theme:compile

# Clear cache
ddev exec console cache:clear

# SSH into the web container
ddev ssh

# Open MySQL CLI
ddev mysql

# View logs
ddev logs

# Enable Xdebug
ddev xdebug on

# Project info & URLs
ddev describe
```

## Custom Plugins

Place plugins in `custom/plugins/` and install them:

```bash
ddev exec console plugin:refresh
ddev exec console plugin:install --activate <PluginName>
```

## Database Access

| Field    | Value               |
|----------|---------------------|
| Host     | `db`                |
| Port     | `3306`              |
| Database | `db`                |
| User     | `db`                |
| Password | `db`                |
| Root pw  | `root`              |

From the host, use `ddev describe` to find the mapped port for external database tools.
