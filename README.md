# CPython Performance Stats

A weekly history of CPython performance, collected using [`pyperformance`](https://github.com/python/pyperformance).
Each week represents a separate benchmark run on a stable hardware configuration.

## Goal

Track changes in CPython’s speed over time — between weekly builds.

Currently, the repository contains only benchmark results in JSON format.

### Structure

```
results/
├── 2025/
│   ├── W42/
│   │   ├── 39.json      # Results for Python 3.9
│   │   ├── 310.json     # Results for Python 3.10
│   │   └── ...
│   ├── W43/
│   │   ├── 39.json
│   │   ├── 310.json
│   │   └── ...
│   └── ...
```

## Results

* [2025-W42](results/2025/W42/table.md)

## Benchmark Environment

All performance benchmarks were run on the same stable hardware configuration to ensure consistency across results.

### Hardware

| Component | Specification |
| :--- | :--- |
| **CPU** | 8 cores x 5 GHz |
| **RAM** | 32 GB |
| **Disk** | 50 GB NVMe |

### Software

| Component | Version |
| :--- | :--- |
| **OS** | Debian GNU/Linux 13 (trixie) |
| **Kernel** | Linux 6.12.48+deb13-cloud-amd64 |
| **GCC** | 14.2.0 (Debian 14.2.0-19) |
| **Clang** | 19.1.7 (Debian 3+b1) |

### CPython Build Process

CPython was built from source using the following baseline configuration flags to achieve maximum performance:

```bash
./configure --enable-optimizations --with-lto=full
```

Depending on the specific benchmark run, the following experimental flags were also used:

*   `--enable-experimental-jit=yes` for JIT-enabled builds.
*   `--disable-gil` for builds with the Global Interpreter Lock disabled.