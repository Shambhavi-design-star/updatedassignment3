DOCKYARD SHIPPING BILL:
#include <stdio.h>

int main() 
{
    // Define variables
    float berthingFeePerDay, cargoHandlingFeePerTon, repairCosts;
    int numberOfDays, tonsOfCargo;
    float totalBill;
    char name[50];  // Array to store the name
    long phone, accno, mb, cheque, upi;     // Use long for phone number
    int method;
    char bank[50];  // Array to store bank name

    // Personal information
    printf(" --- PERSONAL INFORMATION ---\n");
    printf("ENTER CUSTOMER NAME: ");
    scanf("%[^\n]",name);  // Read a line including spaces
    printf("ENTER VALID PHONE NUMBER: ");
    scanf("%ld", &phone); // Correct format specifier for long
    getchar();  // Consume the newline left by scanf

    // Input berthing fee per day
    printf("\n --- BILL DETAILS ---\n");
    printf("Enter the berthing fee per day: ");
    scanf("%f", &berthingFeePerDay);

    // Input number of days the ship is docked
    printf("Enter the number of days the ship is docked: ");
    scanf("%d", &numberOfDays);

    // Input cargo handling fee per ton
    printf("Enter the cargo handling fee per ton: ");
    scanf("%f", &cargoHandlingFeePerTon);

    // Input tons of cargo
    printf("Enter the tons of cargo: ");
    scanf("%d", &tonsOfCargo);

    // Input repair costs
    printf("Enter the repair costs: ");
    scanf("%f", &repairCosts);

    // Calculate the total bill
    float berthingFeeTotal = berthingFeePerDay * numberOfDays;
    float cargoHandlingTotal = cargoHandlingFeePerTon * tonsOfCargo;

    totalBill = berthingFeeTotal + cargoHandlingTotal + repairCosts;

    // Display the total bill
    printf("\n--- Dockyard Ship Bill ---\n");
    printf("Customer Name: %s", name);
    printf("Phone Number: %ld\n", phone);
    printf("Berthing Fee: $%.2f\n", berthingFeeTotal);
    printf("Cargo Handling Fee: $%.2f\n", cargoHandlingTotal);
    printf("Repair Costs: $%.2f\n", repairCosts);
    printf("Total Bill: $%.2f\n", totalBill);
    
    printf("\n--- BILL PAYMENT METHOD ---\n");
    printf("1. BANK TRANSFER\n");
    printf("2. ONLINE PHONE PAYMENT\n");
    printf("3. CHEQUE\n");
    printf("SELECT PAYMENT METHOD: ");
    scanf("%d", &method);
    
    switch(method)
    {
        case 1:
            getchar();  // Consume the newline left by scanf
            printf("ENTER BANK NAME: ");
            scanf("%[^\n]",&bank);
            printf("ENTER ACCOUNT NUMBER: ");
            scanf("%ld", &accno);
            break;
        case 2:
            printf("ENTER MOBILE NUMBER FOR MONEY TRANSFER: ");
            scanf("%ld", &mb);
            printf("ENTER UPI ID: ");
            scanf("%ld", &upi);
            break;
        case 3:
            getchar();  // Consume the newline left by scanf
            printf("ENTER THE BANK NAME: ");
            fgets(bank, sizeof(bank), stdin);
            printf("ENTER CHEQUE NUMBER: ");
            scanf("%ld", &cheque);
            break;
        default:
            printf("INVALID PAYMENT METHOD\n");
    }

    printf("--- THANK YOU FOR YOUR COOPERATION ---\n");
    return 0;
}

