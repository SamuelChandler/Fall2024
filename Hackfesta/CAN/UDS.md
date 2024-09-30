Unified Diagnostic Services

![[Pasted image 20240929215202.png]]

A protocol used for ECU diagnostics and programming

follows a simple request-answer mechanism: 
- you send a payload to the ECU
- you get a payload as an answer

The first byte of a request represents the Service ID; the rest of the payload represents the parameters for that service. The second byte often (but not always) represents a Sub-Function of a service.

[RAMN UDS Doc](https://ramn.readthedocs.io/en/latest/userguide/diag_tutorial.html#uds-basics)


