# Z80Disassembler.js

## Javascript version of Z80 processor's machine code disassembler

How to use:

```javascript
function read_mem(address){
    return zx_spectrum_memory_65536_bytes_array[address & 0xffff] & 0xff;
}

var disassembler = new Z80Disassembler(read_mem);
var address = 0x0000;
while(address < 0x4000) {
    var result = disassembler.process(address);
    console.log(address, result.mnemonic, result.comment);
    address += result.bytesLength;
}
```