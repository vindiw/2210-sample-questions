### Model Marking Scheme Answer

**Pseudocode Answer:**

```
// Initial population of FabricType[] and Price[] arrays
FabricType[1] <- "Cotton"
FabricType[2] <- "Silk"
FabricType[3] <- "Linen"
Price[1] <- 12.99
Price[2] <- 18.50
Price[3] <- 15.75

CurrentCustomer <- 1

// Main program loop to process customers
WHILE TRUE DO
  OUTPUT "Enter the customer's name:"
  INPUT Customers[CurrentCustomer]

  // Input and validate fabric length
  DO
    OUTPUT "Enter the length of fabric needed (in meters):"
    INPUT FabricLength
  WHILE FabricLength < 2.0 OR FabricLength > 20.0
  // Repeat until a valid length is entered

  // Input and validate fabric width
  DO
    OUTPUT "Enter the width of fabric needed (in meters):"
    INPUT FabricWidth
  WHILE FabricWidth < 2.0 OR FabricWidth > 20.0
  // Repeat until a valid width is entered

  // Input and validate color code
  DO
    OUTPUT "Enter the color code of the fabric:"
    INPUT ColorCode
  WHILE ColorCode NOT IN [101, 202, 303]
  // Repeat until a valid color code is entered

  // Calculate fabric area and cost
  FabricArea <- FabricLength * FabricWidth
  OUTPUT "Enter the fabric type index (1-Cotton, 2-Silk, 3-Linen):"
  INPUT FabricIndex
  TotalPrice <- ROUND(FabricArea * Price[FabricIndex], 2)

  // Store order details
  Orders[CurrentCustomer, 1] <- FabricLength
  Orders[CurrentCustomer, 2] <- FabricWidth
  Orders[CurrentCustomer, 3] <- ColorCode
  Orders[CurrentCustomer, 4] <- FabricIndex
  Orders[CurrentCustomer, 5] <- TotalPrice

  // Output purchase record
  OUTPUT "Purchase Record for " + Customers[CurrentCustomer] + ":"
  OUTPUT "Fabric Type: " + FabricType[FabricIndex]
  OUTPUT "Color Code: " + ColorCode
  OUTPUT "Total Price: $" + TotalPrice

  // Prepare for the next customer
  CurrentCustomer <- CurrentCustomer + 1
  // Check if the customer count exceeds 100 and reset if necessary
  IF CurrentCustomer > 100 THEN
    CurrentCustomer <- 1
  ENDIF
ENDWHILE
```

**Explanation:**
- The pseudocode starts by initializing the fabric types and prices.
- It enters a loop to process each customer's order by prompting for necessary details.
- It uses `WHILE` loops to validate inputs for fabric dimensions and color codes.
- It calculates the total price by multiplying the area with the fabric's price and rounding the result to two decimal places.
- The order details are stored in the `Orders[]` array corresponding to the `Customers[]` array.
- After processing an order, the pseudocode prints a detailed purchase record.
- The loop prepares for the next customer, ensuring that the index is reset if it exceeds the capacity of 100 customers. 

This approach ensures that your sister will be practicing accurate input validation, correct calculations, and appropriate output formatting, which are essential skills for achieving full marks in this kind of programming task.
