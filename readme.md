# Asynchronous FIFO in Verilog with Testbench

This repository implements a **parameterizable Asynchronous FIFO (First-In, First-Out)** in Verilog HDL, designed to enable reliable data transfer between two independent clock domains. Unlike a synchronous FIFO, the read and write operations are driven by separate clocks, making the design suitable for **Clock Domain Crossing (CDC)** applications commonly found in FPGA and ASIC systems.

To ensure safe synchronization across asynchronous clock domains, the FIFO employs **Gray code pointers**, where only one bit changes between consecutive states, along with **2-stage flip-flop synchronizers** to minimize the risk of metastability. The design also incorporates **Full** and **Empty** flag generation using synchronized pointers, preventing invalid read and write operations while maintaining data integrity.

The implementation follows a **modular and parameterizable architecture**, consisting of dedicated modules for FIFO memory, pointer management, synchronization logic, and status flag generation. A comprehensive Verilog testbench is included to validate the design under various operating conditions, including normal data transfer, FIFO full, and FIFO empty scenarios.

## Key Features

- Parameterizable data width and FIFO depth
- Independent read and write clock domains
- Gray code pointers for reliable Clock Domain Crossing (CDC)
- 2-stage flip-flop synchronizers to reduce metastability
- Dual-port memory supporting simultaneous read and write operations
- Full and Empty flag generation for flow control
- Modular RTL design for easy scalability and reuse
- Comprehensive Verilog testbench covering functional verification
