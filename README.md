# dotenv

Load contents of .env into child processes. Every other dotenv library
wants you to manually call the setup in your application. I'm not sure
why.

## Installation

```
go install github.com/mperham/dotenv
```

There are no dependencies except the Go toolchain required to build.

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
