### Model Marking Scheme Answer

**Pseudocode Answer:**

```plaintext
// Initial population of VehicleType[] and DailyRate[] arrays
VehicleType[1] <- "Sedan"
VehicleType[2] <- "SUV"
VehicleType[3] <- "Sports Car"
VehicleType[4] <- "Minivan"
VehicleType[5] <- "Convertible"
DailyRate[1] <- 45.99
DailyRate[2] <- 55.99
DailyRate[3] <- 75.50
DailyRate[4] <- 65.00
DailyRate[5] <- 85.00

// Insurance fixed cost
InsuranceCost <- 19.99
CurrentClient <- 1

// Main program loop to process client rentals
WHILE TRUE DO
  OUTPUT "Enter the client's name:"
  INPUT Clients[CurrentClient]

  // Input and validate vehicle type
  DO
    OUTPUT "Enter the vehicle type index (1 to 5):"
    INPUT VehicleIndex
  WHILE VehicleIndex < 1 OR VehicleIndex > 5

  // Input and validate rental period
  DO
    OUTPUT "Enter the number of rental days (1 to 30):"
    INPUT RentalDays
  WHILE RentalDays < 1 OR RentalDays > 30

  // Input and validate the start date
  DO
    OUTPUT "Enter the start date of rental (DD-MM-YYYY):"
    INPUT StartDate
  WHILE NOT VALID_DATE(StartDate) // Assuming a function VALID_DATE exists

  // Input insurance option
  OUTPUT "Is insurance needed? (true/false):"
  INPUT InsuranceOption

  // Calculate total cost
  TotalCost <- RentalDays * DailyRate[VehicleIndex]
  IF InsuranceOption = true THEN
    TotalCost <- TotalCost + InsuranceCost
  ENDIF

  // Store rental details
  Rentals[CurrentClient, 1] <- VehicleIndex
  Rentals[CurrentClient, 2] <- RentalDays
  Rentals[CurrentClient, 3] <- StartDate
  Rentals[CurrentClient, 4] <- InsuranceOption
  Rentals[CurrentClient, 5] <- TotalCost

  // Output rental agreement
  OUTPUT "Rental Agreement for " + Clients[CurrentClient] + ":"
  OUTPUT "Vehicle Type: " + VehicleType[VehicleIndex]
  OUTPUT "Rental Period: " + RentalDays + " days"
  OUTPUT "Start Date: " + StartDate
  OUTPUT "Insurance Taken: " + InsuranceOption
  OUTPUT "Total Cost: $" + TotalCost

  // Prepare for the next client
  CurrentClient <- CurrentClient + 1
  // Check if the client count exceeds 50 and reset if necessary
  IF CurrentClient > 50 THEN
    CurrentClient <- 1
  ENDIF
ENDWHILE
```
