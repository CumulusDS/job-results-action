[![Create Release](https://github.com/CumulusDS/action-job-results/actions/workflows/release.yml/badge.svg)](https://github.com/CumulusDS/action-job-results/actions/workflows/release.yml)  

[![Import Labels](https://github.com/CumulusDS/action-job-results/actions/workflows/labels_import.yml/badge.svg)](https://github.com/CumulusDS/action-job-results/actions/workflows/labels_import.yml)  [![Sync Labels](https://github.com/CumulusDS/action-job-results/actions/workflows/labels_sync.yml/badge.svg)](https://github.com/CumulusDS/action-job-results/actions/workflows/labels_sync.yml)  

[![PR AutoLabeler](https://github.com/CumulusDS/action-job-results/actions/workflows/autolabeler.yml/badge.svg)](https://github.com/CumulusDS/action-job-results/actions/workflows/autolabeler.yml)  [![Assigner](https://github.com/CumulusDS/action-job-results/actions/workflows/assign.yml/badge.svg)](https://github.com/CumulusDS/action-job-results/actions/workflows/assign.yml)  

Runs cfn-lint with scan results as output

### Inputs
#### `args`
Additional cli arguments to pass in to cfn-lint.  Can include specific file and additional arguments if desired.  
Required input.  
 
### Outputs
#### `results`
Results of the scan.

### Example usage
```yaml
      - name: cfn-lint principals
        id: scan-principals
        uses: CumulusDS/action-job-results@v0.0.1
        with:
          path: templates/principals.yml -I
      - name: cfn-lint packaged template
        id: scan-packaged
        uses: CumulusDS/action-job-results@v0.0.1
        with:
          path: .serverless/*.json
```

The results can be later referenced again for use in a separate step if desired using the `results` output from the step.  
In order to reference the `result` output, you must assign and `id` to the step for future referencing.

```yaml
      - name: reprint results
        run: echo "${{ steps.scan-packaged.outputs.results }}" 
```
