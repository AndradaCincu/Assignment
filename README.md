## Overview
This project is about combining several datasets to create one complete and accurate dataset that includes information about companies from different sources. The goal is to handle data conflicts and keep the most useful information.

## Objectives

- **Join datasets** using a common identifier.
- **Fix data conflicts** by choosing the best information.
- **Keep important details** from each dataset to improve data quality.

 ## Key Decisions and Strategies

### 1. Joining Columns

- **Column Used:** `company_name`
- **Normalization:** I've converted `company_name` to lowercase and remove extra spaces to ensure they match correctly across datasets.

### 2. Conflict Resolution

- **Approach:** Try to resolve any conflicts that come up when merging.
- **Prioritization:** If there are conflicting details (like different addresses), we can keep the most reliable one. For example, if there’s an `address`, we use that instead of `raw_address`.

### 3. Handling Similar Data

- **Selective Column Retention:** I've kept the relevant columns (like `categories`, `address`, `city`, and `phone`) during the merge.
- **Combining Data:** If we have similar information, such as both `categories` and `s_category`, we can combine them to make sure we don’t lose any valuable information.

## Implementation

 The merging process:

1. **Load Data:** Read the datasets into DataFrames.
2. **Normalize `company_name`:** Prepare the `company_name` for merging.
3. **Merge Datasets:** Join the DataFrames using `company_name`.
4. **Resolve Conflicts:** Handle any data conflicts that arise during the merge.
5. **Keep Relevant Information:** Make sure only the most useful details are included in the final dataset.

## Summary

This project provides a clear way to merge datasets while keeping data quality high. By following a structured approach, the final dataset aims to be complete and accurate, using the best information from the original datasets.

![Example](Capture.png)
