[![Create Release](https://github.com/CumulusDS/job-results-action/actions/workflows/release.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/release.yml)  

[![Import Labels](https://github.com/CumulusDS/job-results-action/actions/workflows/labels_import.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/labels_import.yml)  [![Sync Labels](https://github.com/CumulusDS/job-results-action/actions/workflows/labels_sync.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/labels_sync.yml)  

[![PR AutoLabeler](https://github.com/CumulusDS/job-results-action/actions/workflows/autolabeler.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/autolabeler.yml)  [![Assigner](https://github.com/CumulusDS/job-results-action/actions/workflows/assign.yml/badge.svg)](https://github.com/CumulusDS/job-results-action/actions/workflows/assign.yml)  

Returns results of previous jobs in workflow

### Inputs
#### `token`
Required input.  Token with appropriate access

#### `matrix`
Non-required input.  
Can be an output from a previous step.  Can be used to specify jobs to search for
 
### Outputs
#### ``

### Example usage
```yaml
      - name: cfn-lint principals
        id: jobs
        uses: CumulusDS/job-results-action@master
        with:
          token: ${{ secrets.TOKEN_WITH_ACCESS }}
          matrix: ${{ toJson(needs.unit.outputs.matrix) }}
```

wip

```yaml
      - name: reprint results
        run: echo "${{ steps.jobs.outputs.XYZ }}" 
```
