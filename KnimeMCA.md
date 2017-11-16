This procedure is used for dimentionality reduction in preparation for decision tree usage. 
The primary usage for this code is the pre-post CANS scores which result in (NoNeed, PresUnresolved, PresResolved and Discovered)
The One-to-Many node creates 4 dummy variables (one for each result) for each CANS item. 
In addition you may want to use the Low Vairance Filter node to eliminate columns with little variance.

**Assumptions:**
Wihtin Knime the variables have been transormed into dummy variables using the One-to-Many node. 

**Possible Errors:**
-Error: argument to 'which' is not logical - This error can occur if there are some items with little variance. 
  Running the Low Variance Filter and eliminating items with low variance can solve this issue.