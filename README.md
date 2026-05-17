# homebrew-chatgpt64

Homebrew tap for [`chatgpt64`](https://github.com/Manne990/chatgpt64), a local retro-computer terminal bridge to OpenAI.

## Install

```sh
brew tap Manne990/chatgpt64
brew install chatgpt64
```

Then configure and start the bridge:

```sh
chatgpt64 setup
chatgpt64 start --terminal c64 --port 6464
```

For VICE/CCGMS modem emulation, run this in a second terminal:

```sh
chatgpt64 tcpser
```

Start VICE in a third terminal:

```sh
chatgpt64 vice
```

In CCGMS, dial:

```text
ATDT6464
```

## Upgrade

```sh
brew update
brew upgrade chatgpt64
```

## Uninstall

```sh
brew uninstall chatgpt64
brew untap Manne990/chatgpt64
```

## Maintainer Notes

Update `Formula/chatgpt64.rb` when a new `chatgpt64` release is tagged:

```sh
VERSION=0.1.2
curl -L -o /tmp/chatgpt64-$VERSION.tar.gz \
  "https://github.com/Manne990/chatgpt64/archive/refs/tags/v$VERSION.tar.gz"
shasum -a 256 /tmp/chatgpt64-$VERSION.tar.gz
```

Replace the formula `url` and `sha256`, then test locally:

```sh
brew reinstall --build-from-source ./Formula/chatgpt64.rb
brew test ./Formula/chatgpt64.rb
```
