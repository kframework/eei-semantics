EEI Driver
==========

This definition if for building the EEI semantics independently.
It only serves to parse an initial program and put it in the `<eeiK>` cell for execution.

```k
require "eei.k"

module EEI-DRIVER
  imports EEI

  configuration
    <k> $PGM:EEIMethods </k>
    <eei/>

  rule <k> PGM:EEIMethods => . </k>
       <eeiK> . => PGM </eeiK>

endmodule
```
