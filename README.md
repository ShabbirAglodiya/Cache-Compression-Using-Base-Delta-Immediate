# Cache-Compression-Using-Base-Delta-Immediate

Abstract:
Cache compression holds promise for increasing on-chip cache capacity and reducing bandwidth usage. The project implements the BDI (Base Delta Immediate) algorithm in Verilog, offering a simple yet efficient compression technique. BDI observes that many cache lines exhibit low dynamic ranges, allowing them to be represented compactly as a base value plus an array of relative differences called deltas. This project aims to enhance cache performance by effectively compressing common cache data patterns with minimal impact on access latency.

Introduction:
Cache memory, the fastest accessible memory in a CPU, boasts clock speeds comparable to the CPU itself, while RAM and HDD lag behind. With modern multi-core processors adding complexity, cache becomes indispensable. Operating as Static RAM, its typical size ranges from kilobytes to megabytes, balancing cost and usage needs.

Project Idea:
This project explores the Base-Delta-Immediate cache compression method, focusing on compressing cache lines during transfers between cache levels, preferably from L1 to L2.

Base-Delta-Immediate Method:
The compression process involves feeding a 256-bit input to the compressor unit, yielding outputs such as compressed cache lines (CCL) and compressibility factors (CON).

Compression:
Initially, a 32-byte uncompressed cache line (UncompCache) is read and stored. Flag variables (flagX_Y), compressibility factors (CONX), and delta values (delX_Y) are determined. These delta values represent the differences between base and subsequent series in the input data, resulting in a final compressed cache line format {Base, followed by delta values}.

Decompression:
Decompression involves checking the CON condition and applying arithmetic operations based on flag variables to display the original data.
