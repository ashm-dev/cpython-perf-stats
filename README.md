# CPython Performance Stats

A weekly history of CPython performance, collected using [`pyperformance`](https://github.com/python/pyperformance).
Each week represents a separate benchmark run on a stable hardware configuration.

## Goal

Track changes in CPython’s speed over time — between weeks builds.

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
