# Data Asset: prd_dw.stage.tbl_transform_image_cut_daily.image_classification_subscribed_image_cut_count

## Definition
Daily count of unique images cut by users with active subscriptions (trial or paid), grouped by cut date and image source classification. Tracks which types of images are being utilized by subscribed users.

## Calculation Method
Counts distinct images cut by users with active subscriptions on a given day, segmented by image source classification. Uses previous day's subscription status (trial or paid) to identify eligible users. Each image is counted only once per day and classification category.

### Upstream Dependencies
1. **<default>.tbl_temp_distinct_cuts.currently_subscribed**
   - Provides the subscription status filter that determines which users' image cuts should be included in the count. Only images cut by users with an active subscription are counted.

2. **<default>.tbl_temp_distinct_cuts.image_id**
   - Provides the unique identifier for each image, enabling the calculation to count distinct images rather than total cuts per day and classification.

## Usage
Serves as a key performance indicator for analyzing user engagement patterns, subscription value, and content utilization across different image sources. Valuable for product analytics, subscription performance reporting, and understanding which image classifications drive engagement among paying customers.

### Downstream Dependencies
None currently identified.
