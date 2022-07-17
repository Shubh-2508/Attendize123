<!-- markdownlint-disable MD033 MD041 -->
<!-- @generated by .automation/build.py, please do not update manually -->
# <a href="https://scalacenter.github.io/scalafix/" target="blank" title="Visit linter Web Site"><img src="https://scalacenter.github.io/scalafix/img/scalacenter2x.png" alt="scalafix" height="100px" class="megalinter-logo"></a>scalafix [![GitHub last commit](https://img.shields.io/github/last-commit/scalacenter/scalafix)](https://github.com/scalacenter/scalafix/commits)

Scalafix lints and fixes scala files

- As there is no prior compilation or semantic db generation, the linting is applied only with [built-in syntactic rules](https://scalacenter.github.io/scalafix/docs/rules/overview.html)
- scalafix arguments related to [semantic options](https://oxsecurity.github.io/megalinter/descriptors/scala_scalafix/#help-content) can not be used

## scalafix documentation

- Version in MegaLinter: **0.10.1**
- Visit [Official Web Site](https://scalacenter.github.io/scalafix/){target=_blank}
- See [How to configure scalafix rules](https://scalacenter.github.io/scalafix/docs/users/configuration.html){target=_blank}
  - If custom `.scalafix.conf` config file is not found, [.scalafix.conf](https://github.com/oxsecurity/megalinter/tree/main/TEMPLATES/.scalafix.conf){target=_blank} will be used
- See [How to disable scalafix rules in files](https://scalacenter.github.io/scalafix/docs/users/suppression.html){target=_blank}
- See [Index of problems detected by scalafix](https://scalacenter.github.io/scalafix/docs/rules/overview.html){target=_blank}

[![scalafix - GitHub](https://gh-card.dev/repos/scalacenter/scalafix.svg?fullname=)](https://github.com/scalacenter/scalafix){target=_blank}

## Configuration in MegaLinter

- Enable scalafix by adding `SCALA_SCALAFIX` in [ENABLE_LINTERS variable](https://oxsecurity.github.io/megalinter/latest/configuration/#activation-and-deactivation)
- Disable scalafix by adding `SCALA_SCALAFIX` in [DISABLE_LINTERS variable](https://oxsecurity.github.io/megalinter/latest/configuration/#activation-and-deactivation)

| Variable                                   | Description                                                                                                                                                                                                         | Default value                                   |
|--------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| SCALA_SCALAFIX_ARGUMENTS                   | User custom arguments to add in linter CLI call<br/>Ex: `-s --foo "bar"`                                                                                                                                            |                                                 |
| SCALA_SCALAFIX_FILTER_REGEX_INCLUDE        | Custom regex including filter<br/>Ex: `(src\|lib)`                                                                                                                                                                  | Include every file                              |
| SCALA_SCALAFIX_FILTER_REGEX_EXCLUDE        | Custom regex excluding filter<br/>Ex: `(test\|examples)`                                                                                                                                                            | Exclude no file                                 |
| SCALA_SCALAFIX_CLI_LINT_MODE               | Override default CLI lint mode<br/>- `file`: Calls the linter for each file<br/>- `list_of_files`: Call the linter with the list of files as argument<br/>- `project`: Call the linter from the root of the project | `file`                                          |
| SCALA_SCALAFIX_FILE_EXTENSIONS             | Allowed file extensions. `"*"` matches any extension, `""` matches empty extension. Empty list excludes all files<br/>Ex: `[".py", ""]`                                                                             | `[".scala"]`                                    |
| SCALA_SCALAFIX_FILE_NAMES_REGEX            | File name regex filters. Regular expression list for filtering files by their base names using regex full match. Empty list includes all files<br/>Ex: `["Dockerfile(-.+)?", "Jenkinsfile"]`                        | Include every file                              |
| SCALA_SCALAFIX_PRE_COMMANDS                | List of bash commands to run before the linter                                                                                                                                                                      | None                                            |
| SCALA_SCALAFIX_POST_COMMANDS               | List of bash commands to run after the linter                                                                                                                                                                       | None                                            |
| SCALA_SCALAFIX_CONFIG_FILE                 | scalafix configuration file name</br>Use `LINTER_DEFAULT` to let the linter find it                                                                                                                                 | `.scalafix.conf`                                |
| SCALA_SCALAFIX_RULES_PATH                  | Path where to find linter configuration file                                                                                                                                                                        | Workspace folder, then MegaLinter default rules |
| SCALA_SCALAFIX_DISABLE_ERRORS              | Run linter but consider errors as warnings                                                                                                                                                                          | `false`                                         |
| SCALA_SCALAFIX_DISABLE_ERRORS_IF_LESS_THAN | Maximum number of errors allowed                                                                                                                                                                                    | `0`                                             |

## MegaLinter Flavours

This linter is available in the following flavours

|                                                                         <!-- -->                                                                         | Flavor                                                                   | Description               | Embedded linters |                                                                                                                                                                     Info |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------|:--------------------------|:----------------:|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/images/mega-linter-square.png" alt="" height="32px" class="megalinter-icon"></a> | [all](https://oxsecurity.github.io/megalinter/latest/supported-linters/) | Default MegaLinter Flavor |       101        | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter/v6) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter) |

## Behind the scenes

### How are identified applicable files

- File extensions: `.scala`

<!-- markdownlint-disable -->
<!-- /* cSpell:disable */ -->
### How the linting is performed

- scalafix is called one time by identified file

### Example calls

```shell
scalafix --check myfile.scala
```

```shell
scalafix --check --config .scalafix.conf myfile.scala
```

```shell
scalafix --config .scalafix.conf myfile.scala
```


### Help content

```shell
Scalafix 0.10.1
Usage: scalafix [options] [<path> ...]

Scalafix is a refactoring and linting tool. Scalafix supports both syntactic and
semantic linter and rewrite rules. Syntactic rules can run on source code
without compilation. Semantic rules can run on source code that has been
compiled with the SemanticDB compiler plugin.

Common options:

  --rules | -r [String ...] (default: [])
    Scalafix rules to run, for example ExplicitResultTypes. The syntax for rules is
    documented in
    https://scalacenter.github.io/scalafix/docs/users/configuration#rules

  --files | -f [<path> ...] (default: [])
    Files or directories (recursively visited) to fix.

  --config <path> (default: null)
    File path to a .scalafix.conf configuration file. Defaults to .scalafix.conf in
    the current working directory, if any.

  --check
    Check that all files have been fixed with scalafix, exiting with non-zero code
    on violations. Won't write to files.

  --stdout
    Print fixed output to stdout instead of writing in-place.

  --diff
    If set, only apply scalafix to added and edited files in git diff against the
    master branch.

  --diff-base String (default: null)
    If set, only apply scalafix to added and edited files in git diff against a
    provided branch, commit or tag.

  --syntactic
    Run only syntactic rules, ignore semantic rules even if they are explicitly
    configured in .scalafix.conf or via --rules

  --triggered
    Overlay the default rules & rule settings in .scalafix.conf with the `triggered`
    section

  --verbose
    Print out additional diagnostics while running scalafix.

  --help | -h
    Print out this help message and exit

  --version | -v
    Print out version number and exit

Semantic options:

  --classpath Classpath (default: "<classpath>")
    Full classpath of the files to fix, required for semantic rules. The source
    files that should be fixed must be compiled with semanticdb-scalac.
    Dependencies are required by rules like ExplicitResultTypes, but the
    dependencies do not need to be compiled with semanticdb-scalac.

  --sourceroot <path> (default: null)
    Absolute path passed to semanticdb with -P:semanticdb:sourceroot:<path>.
    Relative filenames persisted in the Semantic DB are absolutized by the
    sourceroot. Defaults to current working directory if not provided.

  --semanticdb-targetroots [<path> ...] (default: [])
    Absolute paths passed to semanticdb with -P:semanticdb:targetroot:<path>. Used
    to locate semanticdb files. By default, Scalafix will try to locate
    semanticdb files in the classpath

  --auto-classpath
    If set, automatically infer the --classpath flag by scanning for directories
    with META-INF/semanticdb

  --auto-classpath-roots [<path> ...] (default: [])
    Additional directories to scan for --auto-classpath

  --scalac-options [String ...] (default: [])
    The scala compiler options used to compile this --classpath, for example
    -Ywarn-unused-import

  --scala-version ScalaVersion (default: "2.13.8")
    The major or binary Scala version that the provided files are targeting, or the
    full version that was used to compile them when a classpath is provided.

Tab completions:

  --bash
    Print out bash tab completions. To install:
    ```
    # macOS, requires "brew install bash-completion"
    scalafix --bash > /usr/local/etc/bash_completion.d/scalafix
    # Linux
    scalafix --bash > /etc/bash_completion.d/scalafix
    ```

  --zsh
    Print out zsh tab completions. To install:
    ```
    scalafix --zsh > /usr/local/share/zsh/site-functions/_scalafix
    unfunction _scalafix
    autoload -U _scalafix
    ```

Less common options:

  --exclude [<glob> ...] (default: [])
    Unix-style glob for files to exclude from fixing. The glob syntax is defined by
    `nio.FileSystem.getPathMatcher`.

  --tool-classpath URLClassLoader (default: "<classloader>")
    Additional classpath for compiling and classloading custom rules, as a set of
    filesystem paths, separated by ':' on Unix or ';' on Windows.

  --charset Charset (default: "UTF-8")
    The encoding to use for reading/writing files

  --no-sys-exit
    If set, throw exception in the end instead of System.exit

  --no-stale-semanticdb
    Don't error on stale semanticdb files.

  --settings ScalafixConfig (default: {})
    Custom settings to override .scalafix.conf

  --out-from String (default: null)
    Write fixed output to custom location instead of in-place. Regex is passed as
    first argument to file.replaceAll(--out-from, --out-to), requires --out-to.

  --out-to String (default: null)
    Companion of --out-from, string that is passed as second argument to
    fileToFix.replaceAll(--out-from, --out-to)

  --auto-suppress-linter-errors
    Insert /* scalafix:ok */ suppressions instead of reporting linter errors.

  --cwd <path> (default: "/")
    The current working directory

```

### Installation on mega-linter Docker image

- Dockerfile commands :
```dockerfile
# Parent descriptor install
RUN curl -fLo coursier https://git.io/coursier-cli && \
        chmod +x coursier

# Linter install
RUN ./coursier install scalafix --quiet --install-dir /usr/bin
```
