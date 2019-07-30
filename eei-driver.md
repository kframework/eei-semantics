EEI Driver
==========

```k
require "eei.k"

module EEI-DRIVER
  imports EEI
```

Since the EEI specification doesn't specify a main cell (with `$PGM` in it), it can be included in other specifications which already have main cells.
However, to build the EEI semantics independently of other semantics, a main cell is needed.
This definition is for building the EEI semantics independently.
It only serves to parse an initial program and put it in the `<eeiK>` cell for execution.

```k
  configuration
    <k> $PGM:EEIMethods </k>
    <eei/>

  rule <k> PGM:EEIMethods => . </k>
       <eeiK> . => PGM </eeiK>

```
endmodule
```
