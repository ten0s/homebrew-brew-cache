[Homebrew External Command](https://docs.brew.sh/External-Commands)

Search for locally installed package(s) that own the file pattern, similar to

* dpkg --search PATTERN
* apt-cache search PATTERN
* yum whatprovides PATTERN
* pacman --query --owns PATTERN

## Installation

1. Make **brew-cache** accessible from **PATH**
2. Ensure **brew-cache** is runnable


## Usage

### See help

```
$ brew cache
Usage: brew cache [options]

Query the local Homebrew packages cache

    -u                    Update/build the local packages cache
    -s  [/]pattern[/]     Search for package(s) that own the file
                                   pattern
    -d                    Display any debugging information
    -q                    Make some output more quiet
    -h, --help            Show this message
```

### Update or build the packages cache

```
% brew cache -u
Building cache: fcbb2f2ca6958fa9218c035e8cfef96cd6e92164
Cache: fcbb2f2ca6958fa9218c035e8cfef96cd6e92164 is built
```

```
% brew cache -u
Current cache: fcbb2f2ca6958fa9218c035e8cfef96cd6e92164
Cache: fcbb2f2ca6958fa9218c035e8cfef96cd6e92164 is up to date
```

### Search for a locally installed package that owns the given file

#### Pattern is a simple string

```
% brew cache -s 'lib/libgtk-3.so'
gtk+3
```

#### Pattern is a regular expression

```
% brew cache -s '/lib\/gtk.*/'
at-spi2-atk
gtk+3
```

## License

The project is licensed under the 2-Clause BSD License.<br>
See [LICENSE](LICENSE) or
https://spdx.org/licenses/BSD-2-Clause.html
for full license information.
