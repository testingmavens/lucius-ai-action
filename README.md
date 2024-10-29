# Lucius AI Github Action

This GitHub Action runs the Lucius AI action.

## Inputs

- `test_id`: ID of the test to be run.
- `token`: Your secret token to access Lucius AI.

## Outputs

- `result`: A message that includes information about the status of the run.

## Example Usage

```yaml
name: Run Lucius AI Github Action

on: [push]

jobs:
  my-job:
    runs-on: ubuntu-latest
    steps:
      - name: Run CJ Action
        uses: testingmavens/lucius-ai-action@v1.0.1
        id: run_lucius_ai
        with:
          test_id: 'my-test-id'
          token: ${{ secrets.LUCIUS_AI_TOKEN }}
      
      - name: Print Lucius AI Action result
        run: echo "${{ steps.run_lucius_ai.outputs.result }}"