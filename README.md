nicer-bash
==========

Things to make `bash` scripting nicer, partially inspired by `ruby`-style
predicates.

Convenient output functions:

```bash
$ info "foo not found" # "INFO: foo not found"
$ error "foo not found" # "ERROR: foo not found"
$ warn "foo not found" # "WARNING: foo not found"
$ fatal "foo not found" # "FATAL: foo not found" and exits with $? 1

# info!, error!, warn!, fatal! use stderr instead
```

(Less) painful dependency/compatibility checking:

```bash
$ installed? jq || (error! "i need jq" && exit 1)
$ require bash4 || (error! "this script only works on bash 4 and above" && exit)
```

(Less) painful file and string checking:

```bash
$ exists? /etc/passwd && info "found /etc/passwd"
$ file? /usr || warn "not a regular file"
$ directory? /bin && info "found /bin"

$ readable? /var/log/syslog
$ writeable? ~/.bashrc
$ executable? /bin/ls

$ empty? "${foo}"
$ nonempty? "${foo}"
```

More to come.

## Installation

```bash
$ git clone https://github.com/woodruffw/nicer-bash
$ # put nicer-bash/nicer somewhere and source it from your .bashrc and/or scripts
```

## Is it a good idea to use `?` and `!` in `bash` functions?

Maybe?

## License

`nicer-bash` is licensed under the MIT License.

For the exact terms, see the [license](LICENSE) file.