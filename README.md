# composite-action

This is a sample composite action that will generate statistics about the changes in a git repository and give you a list of all the contributors.

## Inputs

- `fromDate`: The start date for the statistics.

## Usage

```yaml
name: "Compile statistics"

on:
  workflow_dispatch:

jobs:
  compile_stats:
    runs-on: ubuntu-latest
    name: Repository statistics
    steps:
      - uses: actions/checkout@v4
      
      - uses: LearningGHActions/composite-action@main
        id: stats_results
        with:
          from-date: '2024-01-01'
```