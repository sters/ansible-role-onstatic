# ansible-role-onstatic

Installs [sters/onstatic](https://github.com/sters/onstatic) on RedHat/CentOS servers.

## How it works

```text
+- main.yml
    +- Call install_onstatic.yml
        +- This yaml checks onstatic is installed.
        +- If not, install latest onstatic from Github Release.
    +- Install to systemd
    +- Call register_repositories.yml
        +- This yaml call `register` API for onstatic.
        +- With role variable of onstatic_register_repositories.
```

## Role variables

|key                           |default          |note                        |
|------------------------------|-----------------|----------------------------|
|onstatic_dirpath              |/var/www/onstatic|onstatic install path       |
|onstatic_backend_port         |18888            |onstatic listen port        |
|onstatic_salt                 |onstatic         |salt for calculate name     |
|onstatic_http_header_key      |onstatic         |expects for `X-ONSTATIC-KEY`|
|onstatic_register_repositories|[]               |pre-register repositories   |
|onstatic_force_install        |false            |force install onstatic bin  |
