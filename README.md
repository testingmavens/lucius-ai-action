# Lucius AI Github Action

This GitHub Action runs the Lucius AI action.

## Inputs

- `test_id`: ID of the test to be run. Either this or `test_suite_id` should be provided.
- `test_suite_id`: ID of the test suite to be run.
- `service_account_key`: Your service account key to access fore ai Critical Journey.

## Outputs

- `result`: A message that includes information about the status of the run.

## Example Usage for running a single test

```yaml
name: Run Lucius Github Action

on: [push]

jobs:
  my-job:
    runs-on: ubuntu-latest
    steps:
      - name: Run Test
        uses: testingmavens/lucius-ai-action@v1.0.5
        id: run_lucius_ai
        with:
          test_id: 'my-test-id'
          service_account_key: ${{ secrets.LUCIUS_SERVICE_ACCOUNT_KEY }}
      
      - name: Print result
        run: echo "${{ steps.run_lucius_ai.outputs.result }}"
```

## Example Usage for running a test suite

```yaml
name: Run Lucius Github Action

on: [push]

jobs:
  my-job:
    runs-on: ubuntu-latest
    steps:
      - name: Run Test Suite
        uses: testingmavens/lucius-ai-action@v1.0.5
        id: run_lucius_ai
        with:
          test_suite_id: 'my-test-suite-id'
          service_account_key: ${{ secrets.LUCIUS_SERVICE_ACCOUNT_KEY }}
      
      - name: Print result
        run: echo "${{ steps.run_lucius_ai.outputs.result }}"
```