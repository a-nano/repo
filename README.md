# repo

Common interface for version control systems.

Repo along with Manifest allow you to use source repositories directly as
ASDF-installable packages. Keep it synced with upstream for development
purposes.

## Usage

``` Common-Lisp
(load "repo")

(repo:repo "github:thodg/repo")         ;; Define repository by URI

(repo:repo "thodg/repo")                ;; Find repository by dir/name
(repo:repo "repo")                      ;; Find repository by name

(setf repo:*repo-dir* "/tmp/repo-test") ;; Change installation directory

(repo:install "github:thodg/repo")      ;; Install repository by URI
(repo:install "thodg/repo")             ;; Install repository by dir/name
(repo:install "repo")                   ;; Install repository by name

(repo:update "github:thodg/repo")       ;; Update repository by URI
(repo:update "thodg/repo")              ;; Update repository by dir/name
(repo:update "repo")                    ;; Update repository by name

repo:*repos*                            ;; List of defined repositories

(repo:clear-repos)                      ;; Clear all definitions
```

## Version informations

This version only supports git repositories and relies on SBCL and /bin/sh.
Next releases will support other VCS and drop requirements on SBCL.

## TODO

*   git tags and branches
*   drop dependency on sbcl (run-program)
*   drop dependency on /bin/sh
*   CVS
*   subversion
*   bzr
*   darcs
*   mercurial
