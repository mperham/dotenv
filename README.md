# dotenv

Load the contents of `.env` into child processes. Every other dotenv library
wants you to manually call the setup in your application. I'm not sure
why?

## Installation

```
go get github.com/mperham/dotenv
```

There are no dependencies except the Go toolchain required to build.
If you have GOPATH=$HOME, it will install `dotenv` in $HOME/bin. See
`go help install` for full details.

## Usage

```
> cat .env
# comments are allowed
TF_LOG=1
# substitutations work...
FILENAME=$HOME/somefile.txt
TF_VAR_faktory_version=1.4.0-1

> ruby -e "puts ENV['TF_LOG']"
<empty>
> dotenv ruby -e "puts ENV['FILENAME']"
/Users/mikeperham/somefile.txt
```

I use dotenv to load variables into Terraform, like `dotenv terraform apply`.
Terraform recognizes anything that starts with `TF_VAR_`.

## License

MIT, derived from joho/godotenv
