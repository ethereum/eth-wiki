<!-- START doctoc generated TOC please keep comment here to allow auto update -->

<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

**Contents**



- [C++](#c)

  - [Import:](#import)

  - [Export:](#export)

- [Go](#go)

  - [Import](#import)

  - [Genesis block:](#genesis-block)

  - [Export](#export)

- [Python](#python)



<!-- END doctoc generated TOC please keep comment here to allow auto update -->



_**Note:** Binary format is concatenated RLP-encoded blocks_



## C++

### Import:

```

eth --import <filename>

```

_Formats supported: binary_



### Export:

```

eth --export Myfile --format binary --from 45 --to latest

```

_Formats supported: hex (newlines separating), binary or JSON_

`--from` and `--to` also support blockhashes



## Go

### Import

```

geth import <filename>

```

_Formats supported: binary_



### Genesis block:

```

geth --genesis <filename> --genesisnonce <nonce>

```

_Formats supported: json_

### Export

```

geth export <filename>

```

_Formats supported: binary_

## Python