# Rod/Cement Shop Management Wireframe Specification

## 1. Project Overview

This website is a single-shop management system for tracking clients, rod purchases, cement purchases, deposits, miscellaneous expenses, payments made back to clients, inventory stock, cash memos, backup and restore, and logged-in devices.

The system should support daily operational use by a shop owner or staff member who needs to record client activity, manage rod and cement stock, review balances, and print transaction summaries. The final system does not need multi-shop or multi-branch support.

### Requirements

- The shop name, address, phone, and logo must be stored as editable shop profile information.
- The system should support Bengali labels in a future release.
- Sample data must remain visible in the wireframe.
- The application requires internet access.
- The language setting applies to the whole shop.

## 2. Entry And Login Experience

The first screen is the login page. It contains a circular "SM" brand badge, the title "Shop Management", supporting sign-in text, a username field, a password field, and a Login button.

After login, the user enters the dashboard. The login does not need to support separate roles such as owner, manager, or staff.

### Requirements

- Login requires only a username and password.
- The final login screen must include a remember-me option.
- Failed login attempts must show a simple error message.
- The system should support multiple user accounts in a future release.

## 3. Dashboard

The dashboard is the main hub after login. It currently provides access to:

- Client History
- Store House
- Advanced Settings

The dashboard no longer shows a direct New Client button. New clients are created from the Client History page. Store House opens the product store details area. Advanced Settings is available through the settings control near the bottom-right of the dashboard card.

The dashboard should eventually show summary numbers for total due, total deposit, and current stock alerts.

### Requirements

- Dashboard summary numbers must appear above the main buttons.
- Stock alerts must cover both rod and cement.
- The dashboard must include a date filter for summary totals.

## 4. Client History

The Client History page lists all clients in a table. It includes:

- New Client button
- Back button to the dashboard
- Search field
- Sort control
- Client table

The client table should include:

- ID
- Phone
- Name
- Address
- Reference

Selecting a client row opens that client's summary. Client search should support name, phone, address, and reference. The sort control should support ID, name, phone, address, and reference.

### Requirements

- Client IDs must be generated automatically.
- Search must match partial text across all searchable fields at once.
- The client table must show both total due and available deposit directly in the list.
- Deleted or archived clients must not appear in search results.

## 5. New Client

The New Client page allows the user to create a client. It includes:

- Phone
- Name
- Address
- Reference
- Save action
- Clear action
- Back action to Client History

After saving, the user should return to Client History or the new client's summary, depending on the final workflow decision.

### Requirements

- After saving a new client, the user must be taken directly to Client Summary.
- A phone number is required before saving.
- Duplicate phone numbers must be blocked.
- Phone numbers must follow Bangladesh mobile-number validation rules.

## 6. Edit Client

The Edit Client page allows the user to update an existing client's details. It includes:

- Name
- Phone
- Address
- Reference
- Delete action
- Save changes action
- Back action to Client Summary

Delete should require a confirmation step before removing the client.

### Requirements

- Deleting a client must be blocked when the client has transactions.
- Client deletion must archive the client instead of permanently removing it.
- Client profile changes do not require edit history.
- Archived clients cannot be restored.

## 7. Client Summary

The Client Summary page shows the selected client's profile, financial totals, transaction actions, and transaction history. It includes Print, Edit, and Back actions at the top.

Client information should include:

- Client Name
- Phone
- Address
- Reference

Summary totals should include:

- Total deposit
- Total debt
- Total Use

The action area should include:

- New Purchase
- New Deposit
- Misc Payment To Client
- Cash memo date input
- Generate cash-memo

The transaction table should include:

- Date
- Description
- Delivery status
- Taka
- Transaction type
- Edit

Transaction types should include Spend, Rod; Spend, Cement; Spend, Other; Deposit; and Paid to Client. Rod and cement sale rows can show delivery status as Completed or Pending. Financial totals should be calculated automatically from transaction rows.

### Requirements

- Delivery status must be blank for miscellaneous-expense and deposit rows; it applies only to rod and cement rows.
- Print on Client Summary must print the entire summary.

## 8. Product Selection

The Product Selection page starts the new purchase flow from Client Summary. It allows the user to choose:

- Rod
- Cement
- Misc Expense

Rod and Cement purchases should stay separate by product type. Misc Expense represents a client past due expense.

### Requirements

- Product Selection must show the selected client's name.
- The page must prevent users from continuing when no client is selected.
- Misc Expense must be placed in a separate client-adjustment area on Client Summary.
- Transaction descriptions must be generated automatically for rod and cement purchases.

## 9. Rod Purchase Selection

The Rod Selection page collects rod purchase information in one bordered input group. It includes:

- Purchase date
- R-brand
- R-size
- Price/Kg
- Total weight
- Total cost
- Other expense
- Other expense cost
- Delivery Status
- Add More action
- Save action
- Back action to Product Selection

R-brand options are BSRM, KSRM, and AKS. R-size options are 6mm, 8mm, 10mm, 12mm, 16mm, and 20mm.

Total cost should be calculated automatically from Price/Kg and Total weight. The purchase should save back to the Client Summary page. Add More should support multiple rod entries in one rod purchase flow.

### Requirements

- A checked Delivery Status means Completed; unchecked means Pending.
- Other expense cost must be added to the final transaction total.
- Each Add More rod entry must create a separate transaction row.
- The system must prevent saving a Completed rod or cement sale when available stock is insufficient.

## 10. Cement Purchase Selection

The Cement Selection page collects cement purchase information in two bordered input groups. Each group includes:

- Purchase date
- CementBrand
- Price/bag
- Cement category
- Total cement bag
- Total price
- Other expense
- Cost
- Delivery status

Cement category options are BM, AM, and OPC. CementBrand is currently fixed as SevenRings. Total price is fixed/read-only in the wireframe and should be calculated automatically from price/bag and Total cement bag.

The two cement data groups represent two different cement entries in one purchase. The second group includes a Delete action. The page also includes Add More, Save, and Back actions.

### Requirements

- Cement Brand must remain fixed to Seven Rings.
- Each cement group must have its own delivery status and expense cost.
- Deleting a cement group requires confirmation before it is removed from the purchase form.

## 11. Misc Expense

The Misc Expense page records a client's past due or miscellaneous expense. It includes:

- Date
- Description
- Taka
- Save action
- Back action to Product Selection

Misc Expense should not support separate categories such as carrying, labor, transport, or miscellaneous because it represents the client's past due expense.

### Requirements

- This feature must be named Past Due Expense throughout the application.
- The description must always be entered manually.
- Past Due Expense affects only client financial totals and never affects stock.

## 12. New Deposit

The New Deposit page records money received from a client. It includes:

- Date
- Description
- Taka
- Save action
- Back action to Client Summary

Saving a deposit should return the user to Client Summary and update total deposit and available deposit.

### Requirements

- Deposit descriptions must use a fixed list such as Cash, Bank, or Mobile Banking.
- Attachments and reference numbers are deferred to a future release.
- A deposit amount must be greater than zero.

## 13. Misc Payment To Client

The Misc Payment To Client page records money paid back to the client. It includes:

- Date
- Description
- Take
- Save action
- Back action to Client Summary

This creates a Paid to Client transaction type in the Client Summary. Paid to Client should reduce the client's available deposit or otherwise affect the client's balance according to the final accounting rule.

### Requirements

- The amount field must be labeled "Taka."
- Paid to Client is allowed only when the client has sufficient available deposit, and the total deposit must decrease by the amount paid.
- Paid to Client transactions must appear in cash memos.

## 14. Transaction Editing

The system provides editing pages for:

- Deposit
- Rod expense
- Cement expense
- Misc Expense
- Misc Payment To Client

Edit Rod Expense includes purchase date, rod brand, R-size, price/kg, total weight, total cost, other expenses, other expense cost, cost, delivery status, delivery date, Delete, and Save changes.

Edit Cement Expense includes purchase date, cement brand, price/bag, cement category, total cement bag, total price, other expense, other expense cost, cost, delivery status, delivery date, Delete, and Save changes.

Edit Deposit includes date, description, taka, Delete, and Save changes.

Edit Misc Expense includes date, description, taka, Delete, and Save changes.

Edit Misc Payment To Client includes date, description, taka, Delete, and Save changes.

Delete actions should require a confirmation step.

### Requirements

- Editing rod or cement purchases must update inventory stock immediately.
- Delivery-status changes must update stock but not the client balance.
- Transaction edit pages must not show the original creation date separately from the editable transaction date.
- Dates must default to the current date when creating deposits, purchases, payments, stock loads, and edits.
- Users may edit the date of a saved transaction.
- Every delete action requires a standard confirmation dialog.
- The system does not keep an audit log for deleted transactions or stock-load changes.

## 15. Cash Memo

The Cash Memo page opens from Client Summary after pressing Generate cash-memo. It shows:

- Cash memo title
- Print button
- Back button to Client Summary
- Client name
- Address
- Phone
- Date
- Memo table
- Buyer signature area
- Seller signature area

The memo table includes:

- Description
- Amount
- Cost/Unit
- Total Cost

It should include rows for past due, product purchase, total due, deposit, and current due. The cash memo should be printable only.

### Requirements

- A cash memo must include only transactions up to the selected memo date.
- Pending delivery items must appear on the cash memo without showing their delivery status.
- Shop information must appear at the top center of the memo.
- Cash memos are generated on demand and memo history is not stored.
- Cash memo numbers must be generated automatically and reset yearly.
- Printed cash memos must not include the logged-in user's name.

## 16. Product Store Details

The Product Store Details page is the Store House entry page from the dashboard. It allows the user to choose:

- Rod
- Cement

It includes a Back action to the dashboard.

### Requirements

- Store House must show stock alerts before the user chooses Rod or Cement.
- Store House must include a separate printable stock summary.
- Store House supports only rod and cement.
- Stock must decrease only after delivery is marked Completed.

## 17. Rod Store Details

The Rod Store Details page shows rod inventory rows. It includes:

- Load Rod action
- Print action
- Back action to Product Store Details
- Rod inventory table

The rod inventory table includes:

- R-size
- Brand
- Remaining Weight

The table no longer has dropdown fields or an Add rod column. Selecting a row opens the Rod Stock page for that rod size and brand.

### Requirements

- Print on Rod Store Details must include all rod inventory rows.
- Remaining Weight must be displayed only in kilograms.
- The table must support filtering by brand or size.

## 18. Load Rod

The Load Rod page adds rod stock. It includes:

- Load date
- R-size
- Brand
- Load Weight
- Load price
- Cancel action
- Save action

R-size options are 6mm, 8mm, 10mm, 12mm, 16mm, and 20mm. Brand options are BSRM, KSRM, and AKS. Saving should return to Rod Store Details.

### Requirements

- Load Rod accepts only one load entry at a time.
- Load Weight accepts only numeric kilogram values.
- Loading rod must automatically create a stock-history row with the status Load.

## 19. Rod Stock

The Rod Stock page shows stock history for a selected rod size and brand. It includes:

- Selected rod size and brand title
- Total load value
- Total sell value
- Remaining stock value
- Print action
- Back action to Rod Store Details
- Stock history table

The stock history table includes:

- Date
- Status
- Weight
- Edit

Edit buttons appear on both load and sell rows. Load-row Edit buttons open Edit Loaded Rod, while sell-row Edit buttons open the corresponding Edit Rod transaction page. Deleting a loaded rod entry must reduce the Total Load remaining stock immediately.

### Requirements

- Sell rows must open the corresponding Edit Rod transaction page.
- Total Sell includes only completed deliveries.
- The system must warn when remaining stock would become negative and block completion of that rod sale.

## 20. Edit Loaded Rod

The Edit Loaded Rod page allows the user to update or delete a rod load stock history row. It includes:

- Date
- Static status value: load
- Weight
- Load price
- Delete action
- Save action
- Back action to Rod Stock

Delete should require confirmation. Save and Delete should return to Rod Stock.

### Requirements

- The static status label must use "Load."
- Loaded weight may be changed even when later sales depend on that stock.
- The edit page must show the selected rod brand and size.

## 21. Cement Store Details

The Cement Store Details page shows cement inventory rows. It includes:

- Load Cement action
- Print action
- Back action to Product Store Details
- Cement inventory table

The cement inventory table includes:

- Brand-Name
- Categories
- Current amount

The table no longer has dropdown fields or an Add column. Selecting a row opens the Cement Stock page for that brand and category.

### Requirements

- Print on Cement Store Details must include all cement categories.
- Current Amount always represents the bag count.
- The table must support filtering if more cement brands are added later.

## 22. Load Cement

The Load Cement page adds cement stock. It includes:

- Load date
- Brand-name
- Categories
- Load amount
- Load price
- Cancel action
- Save action

The current brand option is Seven-Rings. Category options are BM, AM, and OPC. Saving should return to Cement Store Details.

### Requirements

- Load Cement accepts only one load entry at a time.
- Load Amount accepts only whole bag counts.
- Loading cement must automatically create a stock-history row with the status Load.

## 23. Cement Stock

The Cement Stock page shows stock history for a selected cement brand and category. It includes:

- Selected brand and category title
- Total load value
- Total sell value
- Remaining stock value
- Print action
- Back action to Cement Store Details
- Stock history table

The stock history table includes:

- Date
- Status
- Quantity
- Edit

Edit buttons appear on both load and sell rows. Load-row Edit buttons open Edit Stored Cement, while sell-row Edit buttons open the corresponding Edit Cement transaction page. Cement stock is tracked only by bag count. Deleting stored cement requires checking whether later sales depend on that stock.

### Requirements

- Sell rows must open the corresponding Edit Cement transaction page.
- Total Sell includes only completed deliveries.
- Stock history must use "Quantity" everywhere instead of "Remaining."

## 24. Edit Stored Cement

The Edit Stored Cement page allows the user to update or delete a cement load stock history row. It includes:

- Date
- Static status value: load
- Remaining
- Load price
- Delete action
- Save action
- Back action to Cement Stock

Delete should require confirmation. Save and Delete should return to Cement Stock.

### Requirements

- The editable quantity field must be named Quantity.
- Stored cement quantity may be changed even when later sales depend on that stock.
- The edit page must show the selected cement brand and category.

## 25. Advanced Settings

Advanced Settings is accessible from the dashboard settings control. It includes:

- Logged In Device
- Data Restore
- Data backup
- Logout
- Back action to Dashboard

Logout should ask for confirmation before returning to the login page.

### Requirements

- Logout must not be styled as a destructive action.
- Settings must include shop-profile and brand customization.
- Backup and restore must be grouped under a Data Management heading.

## 26. Logged In Device

The Logged In Device page shows active or previously logged-in devices. It includes:

- Device Name
- Location
- Last Active
- Status
- Remove action
- Back action to Advanced Settings

The final system should allow removing other devices remotely.

### Requirements

- The current device cannot be removed.
- Device location must show the exact location when available, or at minimum the city.
- Removing a device requires confirmation.

## 27. Data Backup

The Data Backup page allows the user to prepare or download a backup of shop data. Backup data may include clients, transactions, stock, and settings.

The preferred backup format is Excel/CSV.

### Requirements

- Backup must create separate CSV files.
- Backup must not include printed memo history.
- Backup filenames must include the backup date.
- Backup and restore must not include archived clients or deleted transaction history.

## 28. Data Restore

The Data Restore page allows the user to choose a backup file and restore shop data. Restore should merge backup data with existing data.

Because restore can affect existing records, the page should clearly warn the user before restoration.

### Requirements

- Restore must overwrite duplicate records.
- Restore must preview the number of clients, transactions, and stock rows before confirmation.
- Restore requires a second confirmation step.

## 29. Navigation Rules

Navigation should stay clear and predictable:

- Login opens Dashboard
- Dashboard opens Client History, Store House, and Advanced Settings
- Client History opens New Client and Client Summary
- Client Summary opens Product Selection, New Deposit, Misc Payment To Client, edit pages, Cash Memo, and Edit Client
- Product Selection opens Rod Selection, Cement Selection, and Misc Expense
- Product Store Details opens Rod Store Details and Cement Store Details
- Rod Store Details opens Load Rod and Rod Stock
- Cement Store Details opens Load Cement and Cement Stock
- Stock pages open edit pages only for load rows
- Settings pages return to Advanced Settings or Dashboard as appropriate

Every page should include a Back, Cancel, or equivalent return action, even if the browser back button is available.

### Requirements

- Cancel and Back remain separate labels with distinct meanings.
- Save actions must navigate to the next logical step in the workflow.
- Print actions must keep the user on the same page after printing.

## 30. Visual And Interaction Guidelines

The interface should follow the current wireframe style:

- Centered card layouts
- Bootstrap-style form controls and buttons
- Clear table-based records
- Simple action buttons
- Bordered boxes for grouped input fields
- Static fields styled like form controls when values should not be edited
- Print actions on summary and stock pages
- Delivery status shown with clear Completed and Pending labels

The design should remain practical and operational rather than decorative. The final system should receive a custom brand style later.

### Requirements

- Custom brand colors are pending a design decision; Bootstrap-style defaults remain in use until then.
- Completed and Pending statuses must use badges.
- Printable pages must use a cleaner, print-specific layout.
- Currency values must always show the Taka symbol.
