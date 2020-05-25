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
> echo "TF_LOG=1" > .env
> ruby -e "puts ENV['TF_LOG']"
<empty>
> dotenv ruby -e "puts ENV['TF_LOG']"
1
```

## License

MIT, derived from joho/godotenv
