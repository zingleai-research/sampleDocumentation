# Data Asset: prd_dw.fact.cut_session_image.image_id

## Definition
A unique numerical identifier for images used within cutting sessions. Negative values indicate private user-uploaded images, while positive values typically represent official Cricut content.

## Calculation Method
Direct copy of prd_dw.fact.cut_session_master.image_id without transformation, serving as a critical reference key that links cutting session data to specific images being processed.

### Upstream Dependencies
1. **prd_dw.fact.cut_session_master.image_id**
   - Direct source column providing the unique numerical identifier for images within cutting sessions, with negative IDs representing private user-uploaded images and positive IDs representing official Cricut content

## Usage
Critical identifier that distinguishes between private user-uploaded images and official Cricut content, enabling content classification, standardized identifier creation, and analysis of usage patterns.

### Downstream Dependencies
1. **prd_dw.fact.cut_session_project.number_of_images**
   - Used to count the total number of unique images associated with a cutting session project

2. **analytics.image_cuts_user_cohorts.image_id_consolidated**
   - Used to create a standardized image identifier where private images are assigned -1, while preserving original IDs for Cricut content

3. **analytics.image_cuts_user_cohorts.image_name**
   - Used to implement a standardized naming convention where private images receive the generic label 'Private' instead of their actual names

4. **analytics.image_cuts_user_cohorts.image_set_group_id**
   - Used to create a standardized group identifier where private images are assigned -1, while preserving original group IDs for other images

5. **analytics.image_cuts_user_cohorts.m_number_consolidated**
   - Used to create a standardized alphanumeric identifier where private images receive the placeholder '#M00000000', while preserving original m_numbers for other images

6. **analytics.pillar3_kpi_content_cut.contains_cricut_fonts**
   - Used to join with dimension tables to determine content classification, enabling the identification of cutting sessions containing Cricut fonts

7. **analytics.pillar3_kpi_content_cut.contains_cricut_images**
   - Used to join with dimension tables to determine content classification, enabling the identification of cutting sessions containing Cricut-provided images

8. **analytics.pillar3_kpi_content_cut.contains_private_images**
   - Used to join with dimension tables to determine content classification, enabling the identification of cutting sessions containing user-uploaded private images

9. **analytics.pillar3_kpi_content_cut.contains_system_fonts**
   - Used to join with dimension tables to determine content classification, enabling the identification of cutting sessions containing system fonts

10. **analytics.pillar3_kpi_content_cut.is_all_cricut_content**
   - Used to join with dimension tables to determine if a cutting session contains exclusively Cricut-provided content

11. **analytics.pillar3_kpi_content_cut.is_all_font_content**
   - Used to join with dimension tables to determine if a cutting session contains exclusively font content (Cricut or system fonts)

12. **analytics.pillar3_kpi_content_cut.is_all_image_content**
   - Used to join with dimension tables to determine if a cutting session contains exclusively image content (private or Cricut images)

13. **analytics.pillar3_kpi_content_cut.is_all_private_content**
   - Used to join with dimension tables to determine if a cutting session contains exclusively private content (private images and system fonts)

14. **analytics.pillar3_kpi_content_cut.project_content_list**
   - Used to join with dimension tables to create a consolidated, pipe-delimited list of all distinct content types used within a cutting project
