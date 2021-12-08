<style>
r { color: Red }
o { color: Orange }
g { color: Green }
</style>

# flow-export

Repositório com ferramentas para exportar fluxos de rede em arquivos pcap.

## Timestamps support
- _**YAF**_ : Milliseconds (_decimal separator_).
- _**Argus**_ : Microseconds (_decimal separator_).
- _**CICFlowMeter**_ : Microseconds (_no decimal separator_). Needs coding to dump in microseconds.
- _**Cisco-Joy**_ : Microseconds (_decimal separator_).
- _**Go-Flows**_ : Milliseconds/Microseconds/NanoSeconds (_no decimal separator_).
- _**NFStream**_ : Milliseconds (_no decimal separator_).
