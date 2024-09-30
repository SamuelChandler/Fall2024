## Configuring for CAN Logging 

Remove less useful columns: 
- Source
- Destination
- Protocol
- Length

Add ‘data.data’ as a column

Make sure ‘information’ column is enabled

![[Pasted image 20240929214803.png]]

## Configure for ISOTP & UDS

[[UDS]] [[ISO-TP]]

- Menu-click packet -> “Decode As” 
- Select ISO 15765 as CAN decoder 
- Add another decoder with ‘+’ button 
- Configure it as ISO 15765 decoder 
- Select UDS as ISO 15765 decoder