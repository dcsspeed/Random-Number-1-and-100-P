# Random-Number-1-and-100-P
Guessing Game For Powershell Windows CLI
# Generate a random number between 1 and 100
$correctNumber = Get-Random -Minimum 1 -Maximum 101

Write-Host "Welcome to the Guessing Game!"
Write-Host "I've picked a number between 1 and 100. Try to guess it."

# Initialize variables
$guess = 0
$attempts = 0

# Start the game loop
do {
    # Prompt the user for a guess
    $guess = Read-Host "Enter your guess:"

    # Check if the guess is a valid number
    if ($guess -match '^\d+$') {
        $attempts++
        
        # Check if the guess is correct
        if ($guess -eq $correctNumber) {
            Write-Host "Congratulations! You guessed it correctly in $attempts attempts."
            break
        }
        elseif ($guess -lt $correctNumber) {
            Write-Host "Too low. Try again."
        }
        else {
            Write-Host "Too high. Try again."
        }
    }
    else {
        Write-Host "Invalid input. Please enter a valid number."
    }
} while ($true)
