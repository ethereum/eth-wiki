# Blockchain import and export instructions

_**Note:** Binary format is concatenated RLP-encoded blocks_

## C++

### Import:

```shell
eth --import <filename>
```

_Formats supported: binary_

### Export:

```shell
eth --export Myfile --format binary --from 45 --to latest
```

_Formats supported: hex (newlines separating), binary or JSON_
`--from` and `--to` also support blockhashes

## Go

### Import

```shell
geth import <filename>
```

_Formats supported: binary_

### Genesis block:

```shell
geth --genesis <filename> --genesisnonce <nonce>
```

_Formats supported: json_

### Export

```shell
geth export <filename>
```

_Formats supported: binary_

## Python
