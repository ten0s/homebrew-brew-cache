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

##### MacOS

```
% brew cache -s 'gtk'
cairo 1.16.0_5
gettext 0.21.1
gtk+3 3.24.35
meson 0.64.1
```

```
% brew cache -s 'lib/libgtk-3.dylib'
gtk+3 3.24.35
```

##### Linux

```
$ brew cache -s 'gtk'
at-spi2-atk 2.38.0
cairo 1.16.0_5
gettext 0.21.1
gtk+3 3.24.35
libxml2 2.10.3_1
libxslt 1.1.37_1
meson 0.64.1
```

```
% brew cache -s 'lib/libgtk-3.so'
gtk+3 3.24.35
```

#### Pattern is a regular expression

##### MacOS

```
% brew cache -s '/lib\/gtk.*/'
gtk+3 3.24.35
```

##### Linux

```
% brew cache -s '/lib\/gtk.*/'
at-spi2-atk 2.38.0
gtk+3 3.24.35
```

## License

The project is licensed under the 2-Clause BSD License.<br>
See [LICENSE](LICENSE) or
https://spdx.org/licenses/BSD-2-Clause.html
for full license information.
