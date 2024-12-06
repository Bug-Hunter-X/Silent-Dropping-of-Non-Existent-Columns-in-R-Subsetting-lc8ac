# Silent Dropping of Non-Existent Columns in R Subsetting

This repository demonstrates a subtle but potentially problematic issue in R when subsetting data frames using character vectors.  If the specified column names don't exist, R silently drops them instead of generating an error or warning. This can lead to unexpected results and difficult-to-debug errors.

The `bug.R` file contains code that reproduces this issue.  The `bugSolution.R` file provides a corrected version that addresses the problem.

## Problem Description

When subsetting a data frame using a character vector for column selection in R, if any of the provided column names are not found within the data frame, those columns are simply ignored without producing any warnings or errors. This behavior can be very problematic as it may not be immediately apparent that data is missing.

## Solution

The solution involves checking the existence of the columns before subsetting.  This can be done using `%in%` or `all()`.