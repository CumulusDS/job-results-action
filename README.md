[![Create Release](https://github.com/CumulusDS/job-results-action/actions/workflows/release.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/release.yml)  

[![Import Labels](https://github.com/CumulusDS/job-results-action/actions/workflows/labels_import.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/labels_import.yml)  [![Sync Labels](https://github.com/CumulusDS/job-results-action/actions/workflows/labels_sync.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/labels_sync.yml)  

[![PR AutoLabeler](https://github.com/CumulusDS/job-results-action/actions/workflows/autolabeler.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/autolabeler.yml)  [![Assigner](https://github.com/CumulusDS/job-results-action/actions/workflows/assign.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/assign.yml)  

Returns results of previous jobs in workflow

### Inputs
#### `token`
Required input.  
 
### Outputs
#### ``

### Example usage
```yaml
      - name: cfn-lint principals
        id: jobs
        uses: CumulusDS/job-results-action@master
        with:
          token: ${{  env.TOKEN_WITH_ACCESS }}
```

wip

```yaml
      - name: reprint results
        run: echo "${{ steps.jobs.outputs.XYZ }}" 
```
