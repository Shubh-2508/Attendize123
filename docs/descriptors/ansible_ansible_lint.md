<!-- markdownlint-disable MD033 MD041 -->
<!-- @generated by .automation/build.py, please do not update manually -->
# ansible-lint [![GitHub last commit](https://img.shields.io/github/last-commit/ansible/ansible-lint)](https://github.com/ansible/ansible-lint/commits)

## ansible-lint documentation

- Version in MegaLinter: **6.0.2**
- Visit [Official Web Site](https://ansible-lint.readthedocs.io/en/latest/){target=_blank}
- See [How to configure ansible-lint rules](https://ansible-lint.readthedocs.io/en/latest/configuring.html#configuration-file){target=_blank}
- See [How to disable ansible-lint rules in files](https://ansible-lint.readthedocs.io/en/latest/rules.html#false-positives-skipping-rules){target=_blank}
- See [Index of problems detected by ansible-lint](https://ansible-lint.readthedocs.io/en/latest/default_rules.html){target=_blank}

[![ansible-lint - GitHub](https://gh-card.dev/repos/ansible/ansible-lint.svg?fullname=)](https://github.com/ansible/ansible-lint){target=_blank}

## Configuration in MegaLinter

- Enable ansible-lint by adding `ANSIBLE_ANSIBLE_LINT` in [ENABLE_LINTERS variable](https://oxsecurity.github.io/megalinter/beta/configuration/#activation-and-deactivation)
- Disable ansible-lint by adding `ANSIBLE_ANSIBLE_LINT` in [DISABLE_LINTERS variable](https://oxsecurity.github.io/megalinter/beta/configuration/#activation-and-deactivation)

| Variable                                         | Description                                                                                                                                                                                  | Default value                                   |
|--------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| ANSIBLE_ANSIBLE_LINT_ARGUMENTS                   | User custom arguments to add in linter CLI call<br/>Ex: `-s --foo "bar"`                                                                                                                     |                                                 |
| ANSIBLE_ANSIBLE_LINT_FILE_EXTENSIONS             | Allowed file extensions. `"*"` matches any extension, `""` matches empty extension. Empty list excludes all files<br/>Ex: `[".py", ""]`                                                      | `[".yml", ".yaml"]`                             |
| ANSIBLE_ANSIBLE_LINT_FILE_NAMES_REGEX            | File name regex filters. Regular expression list for filtering files by their base names using regex full match. Empty list includes all files<br/>Ex: `["Dockerfile(-.+)?", "Jenkinsfile"]` | Include every file                              |
| ANSIBLE_ANSIBLE_LINT_PRE_COMMANDS                | List of bash commands to run before the linter                                                                                                                                               | None                                            |
| ANSIBLE_ANSIBLE_LINT_POST_COMMANDS               | List of bash commands to run after the linter                                                                                                                                                | None                                            |
| ANSIBLE_ANSIBLE_LINT_CONFIG_FILE                 | ansible-lint configuration file name</br>Use `LINTER_DEFAULT` to let the linter find it                                                                                                      | `.ansible-lint`                                 |
| ANSIBLE_ANSIBLE_LINT_RULES_PATH                  | Path where to find linter configuration file                                                                                                                                                 | Workspace folder, then MegaLinter default rules |
| ANSIBLE_ANSIBLE_LINT_DISABLE_ERRORS              | Run linter but consider errors as warnings                                                                                                                                                   | `false`                                         |
| ANSIBLE_ANSIBLE_LINT_DISABLE_ERRORS_IF_LESS_THAN | Maximum number of errors allowed                                                                                                                                                             | `0`                                             |
| ANSIBLE_DIRECTORY                                | Directory containing ANSIBLE files                                                                                                                                                           | `ansible`                                       |

## MegaLinter Flavours

This linter is available in the following flavours

|                                                                         <!-- -->                                                                         | Flavor                                                                               | Description                                           | Embedded linters |                                                                                                                                                                                                 Info |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------|:------------------------------------------------------|:----------------:|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/images/mega-linter-square.png" alt="" height="32px" class="megalinter-icon"></a> | [all](https://oxsecurity.github.io/megalinter/beta/supported-linters/)               | Default MegaLinter Flavor                             |       105        |                             ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter) |
|    <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/documentation.ico" alt="" height="32px" class="megalinter-icon"></a>    | [documentation](https://oxsecurity.github.io/megalinter/beta/flavors/documentation/) | MegaLinter for documentation projects                 |        45        | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-documentation/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-documentation) |
|       <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/dotnet.ico" alt="" height="32px" class="megalinter-icon"></a>        | [dotnet](https://oxsecurity.github.io/megalinter/beta/flavors/dotnet/)               | Optimized for C, C++, C# or VB based projects         |        54        |               ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-dotnet/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-dotnet) |
|         <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/go.ico" alt="" height="32px" class="megalinter-icon"></a>          | [go](https://oxsecurity.github.io/megalinter/beta/flavors/go/)                       | Optimized for GO based projects                       |        47        |                       ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-go/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-go) |
|        <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/java.ico" alt="" height="32px" class="megalinter-icon"></a>         | [java](https://oxsecurity.github.io/megalinter/beta/flavors/java/)                   | Optimized for JAVA based projects                     |        47        |                   ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-java/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-java) |
|     <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/javascript.ico" alt="" height="32px" class="megalinter-icon"></a>      | [javascript](https://oxsecurity.github.io/megalinter/beta/flavors/javascript/)       | Optimized for JAVASCRIPT or TYPESCRIPT based projects |        54        |       ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-javascript/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-javascript) |
|         <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/php.ico" alt="" height="32px" class="megalinter-icon"></a>         | [php](https://oxsecurity.github.io/megalinter/beta/flavors/php/)                     | Optimized for PHP based projects                      |        49        |                     ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-php/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-php) |
|       <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/python.ico" alt="" height="32px" class="megalinter-icon"></a>        | [python](https://oxsecurity.github.io/megalinter/beta/flavors/python/)               | Optimized for PYTHON based projects                   |        53        |               ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-python/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-python) |
|        <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/ruby.ico" alt="" height="32px" class="megalinter-icon"></a>         | [ruby](https://oxsecurity.github.io/megalinter/beta/flavors/ruby/)                   | Optimized for RUBY based projects                     |        46        |                   ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-ruby/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-ruby) |
|        <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/rust.ico" alt="" height="32px" class="megalinter-icon"></a>         | [rust](https://oxsecurity.github.io/megalinter/beta/flavors/rust/)                   | Optimized for RUST based projects                     |        46        |                   ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-rust/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-rust) |
|     <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/salesforce.ico" alt="" height="32px" class="megalinter-icon"></a>      | [salesforce](https://oxsecurity.github.io/megalinter/beta/flavors/salesforce/)       | Optimized for Salesforce based projects               |        48        |       ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-salesforce/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-salesforce) |
|      <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/security.ico" alt="" height="32px" class="megalinter-icon"></a>       | [security](https://oxsecurity.github.io/megalinter/beta/flavors/security/)           | Optimized for security                                |        21        |           ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-security/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-security) |
|        <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/swift.ico" alt="" height="32px" class="megalinter-icon"></a>        | [swift](https://oxsecurity.github.io/megalinter/beta/flavors/swift/)                 | Optimized for SWIFT based projects                    |        46        |                 ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-swift/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-swift) |
|      <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/terraform.ico" alt="" height="32px" class="megalinter-icon"></a>      | [terraform](https://oxsecurity.github.io/megalinter/beta/flavors/terraform/)         | Optimized for TERRAFORM based projects                |        51        |         ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-terraform/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-terraform) |

## Behind the scenes

### How are identified applicable files

- Activated only if sub-directory `ansible` is found. (directory name can be overridden with `ANSIBLE_DIRECTORY`)
- File extensions: `.yml`, `.yaml`
- File name do not ends with: `vault.yml`, `vault.yaml`, `galaxy.yml`, `galaxy.yaml`

<!-- markdownlint-disable -->
<!-- /* cSpell:disable */ -->
### How the linting is performed

ansible-lint is called once on the whole project directory (`project` CLI lint mode)

- filtering can not be done using MegaLinter configuration variables,it must be done using ansible-lint configuration or ignore file (if existing)
- `VALIDATE_ALL_CODEBASE: false` does not make ansible-lint analyze only updated files

### Example calls

```shell
ansible-lint -v
```

```shell
ansible-lint -v -c .ansible-lint
```


### Help content

```shell
usage: ansible-lint [-h] [-L]
                    [-f {rich,plain,rst,json,codeclimate,quiet,pep8}] [-q]
                    [-p] [--progressive] [--project-dir PROJECT_DIR]
                    [-r RULESDIR] [-R] [--write] [--show-relpath] [-t TAGS]
                    [-T] [-v] [-x SKIP_LIST] [-w WARN_LIST]
                    [--enable-list ENABLE_LIST] [--nocolor] [--force-color]
                    [--exclude EXCLUDE_PATHS] [-c CONFIG_FILE] [--offline]
                    [--version]
                    [lintables ...]

positional arguments:
  lintables             One or more files or paths. When missing it will
                        enable auto-detection mode.

options:
  -h, --help            show this help message and exit
  -L                    list all the rules
  -f {rich,plain,rst,json,codeclimate,quiet,pep8}
                        stdout formatting, json being an alias for
                        codeclimate. (default: rich)
  -q                    quieter, reduce verbosity, can be specified twice.
  -p                    parseable output, same as '-f pep8'
  --progressive         Return success if it detects a reduction in number of
                        violations compared with previous git commit. This
                        feature works only in git repositories.
  --project-dir PROJECT_DIR
                        Location of project/repository, autodetected based on
                        location of configuration file.
  -r RULESDIR           Specify custom rule directories. Add -R to keep using
                        embedded rules from /usr/local/lib/python3.10/site-
                        packages/ansiblelint/rules
  -R                    Keep default rules when using -r
  --write               Reformat YAML files to standardize spacing, quotes,
                        etc. Future versions will expand this option so it
                        fixes more issues.
  --show-relpath        Display path relative to CWD
  -t TAGS               only check rules whose id/tags match these values
  -T                    list all the tags
  -v                    Increase verbosity level (-vv for more)
  -x SKIP_LIST          only check rules whose id/tags do not match these
                        values
  -w WARN_LIST          only warn about these rules, unless overridden in
                        config file defaults to 'experimental'
  --enable-list ENABLE_LIST
                        activate optional rules by their tag name
  --nocolor             disable colored output, same as NO_COLOR=1
  --force-color         Force colored output, same as FORCE_COLOR=1
  --exclude EXCLUDE_PATHS
                        path to directories or files to skip. This option is
                        repeatable.
  -c CONFIG_FILE        Specify configuration file to use. By default it will
                        look for '.ansible-lint' or '.config/ansible-lint.yml'
  --offline             Disable installation of requirements.yml
  --version
```

### Installation on mega-linter Docker image

- PIP packages (Python):
  - [ansible-lint==6.0.2](https://pypi.org/project/ansible-lint==6.0.2)