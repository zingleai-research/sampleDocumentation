# Data Asset: prd_dw.stage.tbl_transform_material.is_approved

## Definition
A boolean flag indicating whether a material has been approved for use in the system. Combines approval statuses from global materials database (defaulting to TRUE) and custom materials database (defaulting to FALSE).

## Calculation Method
Combines approval statuses from two different sources based on material type. For global materials, uses isapproved from materialsglobals (defaults to TRUE if NULL). For custom materials, uses isapproved from materialcustoms (defaults to FALSE if NULL).

### Upstream Dependencies
1. **data_lake.materials.materialcustoms.isapproved**
   - Provides the approval status for custom materials created by users. Defaults to FALSE when NULL, implementing the business rule that custom materials require explicit approval.

2. **data_lake.materials.materialsglobals.isapproved**
   - Provides the approval status for global materials in the system. Defaults to TRUE when NULL, implementing the business rule that global materials are considered approved by default.

## Usage
Controls which materials are available for use in cutting projects and other system operations. Implements business rules where global materials are typically pre-approved while custom materials require explicit approval.

### Downstream Dependencies
None currently identified.
