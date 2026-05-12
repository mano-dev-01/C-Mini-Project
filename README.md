# Global Minibank System - Enhanced Edition

## Overview
This is an enhanced version of the Transaction Processing System for a bank management application. The program provides secure account management with PIN-based authentication and comprehensive financial operations.

---

## New Feature: Interest Earnings Calculator

### What's New?
A new **Option 7: "Calculate Monthly Interest Earnings"** has been added to the main menu. This feature allows account holders to view detailed interest projections on their current balance.

### Details
- **Annual Interest Rate**: 2% (configurable via `ANNUAL_INTEREST_RATE` macro)
- **Monthly Interest Rate**: 0.1667% (automatically calculated as annual / 12)
- **Requires**: Account number and PIN authentication
- **Shows**:
  - Monthly interest earned
  - Projected balance after 1 month
  - Projected balance after 1 year
  - Current balance and interest rate details

### Example Output
```
--- ACCOUNT INTEREST CALCULATION ---
Account Number: 1
Name: John Doe
Current Balance: $10,000.00
Annual Interest Rate: 2.00%
Monthly Interest Rate: 0.1667%
Monthly Interest Earned: $16.67
Projected Balance (after 1 month): $10,016.67
Projected Balance (after 1 year): $10,200.00
```

---

## Core Features (Unchanged)

1. **Export Accounts** - Save all account info to `accounts.txt`
2. **Deposit/Withdraw** - Update account balance with PIN verification
3. **New Account** - Create account with PIN protection
4. **Delete Account** - Logically delete (close) an account
5. **Transfer Funds** - Move money between accounts with logging
6. **View All Accounts** - Display all active accounts on screen

---

## Technical Improvements

- **Security**: PIN-based authentication for sensitive operations
- **Data Integrity**: Transaction logging to `transactions_log.txt`
- **Memory Optimization**: Efficient struct packing (`#pragma pack`)
- **Error Handling**: Input validation and bounds checking
- **Functional Decomposition**: Modular function design

---

## Compilation & Usage

```bash
gcc -o trans trans.c -Wall -Wextra
./trans
```

### Menu Navigation
Select option 1-7 from the main menu:
- **1-6**: Original features
- **7**: NEW - Calculate interest earnings
- **8**: Exit program

---

## Files Generated

- `credit.dat` - Binary database file (auto-created)
- `accounts.txt` - Text export of active accounts
- `transactions_log.txt` - Audit log of all transactions

---

## Implementation Notes

- Interest calculation is **informational only** (does not auto-apply)
- PIN verification is **required** for interest queries (security best practice)
- Interest rates can be customized by modifying the `ANNUAL_INTEREST_RATE` macro
- Account numbers must be between 1-100