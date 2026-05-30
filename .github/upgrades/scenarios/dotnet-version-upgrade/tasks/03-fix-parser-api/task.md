## Objective
Fix API compatibility issues in GH .NET Parser after upgrading to net10.0

## Done when
- Project builds without errors
- No warnings in modified projects
- MetadataLoadContext usage works or has a documented workaround

## Steps
1. Review MetadataLoadContext usage and package compatibility
2. Adjust code if needed to newer API surface
3. Validate by parsing a sample assembly
