# Perspective Chrome Benchmark

This repository provides a benchmark comparison between different versions of Perspective, specifically 2.10.1 and the latest release. The goal is to evaluate creation times and memory consumption to identify potential performance regressions.

## Benchmark Overview

The benchmark measures the following metrics:

### Performance Metrics

- Total Duration – Total time taken for all operations.
- Worker Create – Time taken to initialize Perspective workers.
- Table Create – Time taken to create tables within workers.
- Table Update – Time taken to populate tables with data.
- View Create – Time taken to create views from tables.
- View ToJson – Time taken to convert views to JSON.

### Memory Usage Metrics

- jsHeapSizeLimit – Maximum JavaScript heap memory allowed by the engine.
- totalJSHeapSize – Total heap memory allocated.
- usedJSHeapSize – Heap memory currently in use.

How the Benchmark Works 1. A predefined dataset (data.csv) is loaded. 2. A Perspective worker is created. 3. 100 tables are instantiated for each worker. 4. Data is updated into each table. 5. A view is created for each table. 6. The view is converted to JSON. 7. Performance metrics are measured at each step. 8. Memory usage is tracked using the performance.memory API.

## Benchmark Results

The latest version of Perspective exhibits higher memory usage and longer creation times compared to version 2.10.1.

To view the results:

- Latest Version Deployment: [Benchmark Results](https://psp-benchmark-latest.netlify.app/)
- v2.10.1 Version Deployment: [Benchmark Results](https://psp-benchmark-2-10-1.netlify.app/)

## How to Run Locally

To test the benchmark locally:

1. Clone this repository:

```sh
git clone https://github.com/kryaksy/perspective-benchmark.git
cd perspective-benchmark
```

2. Start a simple HTTP server:

```sh
npx serve .
```

3. Open index.html in a browser.

## Discussion

This benchmark highlights a potential performance regression in newer versions of Perspective. Further investigation is needed to determine whether optimizations can be applied to improve memory efficiency and execution times.
