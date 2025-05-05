# Data Asset: prd_dw.stage.compute_append_session_update_data.project_cut_session_end_date

## Definition
Timestamp indicating when a project cutting session ended, serving as a critical marker for session boundary determination using a 30-minute inactivity threshold.

## Calculation Method
Directly derived from upstream data without transformation, representing the timestamp when a project cutting session ended. Used to identify distinct cutting sessions based on a 30-minute inactivity threshold.

### Upstream Dependencies
1. **prd_dw.stage.overlap_user_data.project_cut_session_end_date**
   - Provides the direct source timestamp value indicating when a project cutting session ended, including the session boundary determination logic with a 30-minute inactivity threshold

## Usage
Essential for calculating session duration, analyzing user engagement patterns, and tracking machine usage. Propagated through the data pipeline to maintain consistent session end date information across multiple tables.

### Downstream Dependencies
1. **prd_dw.stage.stage_cut_sessions_delta_data.project_cut_session_end_date**
   - Used as a source value in conditional logic that determines the project cut session end date when the flag is not 'GET NEW SESSION AND UPDATE START DATE'

2. **prd_dw.fact.cut_session_image**
   - Provides session end date information for image-related session analytics

3. **prd_dw.stage.stage_cut_session_images**
   - Supplies session end date information for staging image data related to cutting sessions

4. **prd_dw.fact.cut_session_project**
   - Indirectly contributes session end date information for project-related session analytics
