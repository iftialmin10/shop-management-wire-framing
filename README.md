# Rod/Cement Shop Management Wireframe Specification

## 1. Project Overview

This website is a single-shop management system for tracking clients, rod purchases, cement purchases, deposits, miscellaneous expenses, payments made back to clients, inventory stock, cash memos, backup and restore, and logged-in devices.

The system should support daily operational use by a shop owner or staff member who needs to record client activity, manage rod and cement stock, review balances, and print transaction summaries. The final system does not need multi-shop or multi-branch support.

Open questions:

Open question 1: Should the shop name, address, phone, and logo be stored as editable shop profile information?

Open Question 1 Answer: The shop name, address, phone, and logo should be stored as editable shop profile information

Open question 2: Should the system support Bengali labels later, or should all screens remain English only?

Open Question 2 Answer: The system should support Bengali labels later.

Open question 3: Should sample data stay visible in the wireframe, or should the final design use empty states instead?

Open Question 3 Answer: Sample data should stay visible in the wireframe.

Open question 4: Should the app require internet access, or should it work offline after login?

Open Question 4 Answer: the app should require internet access.

Open question 5: Should Bengali labels be switchable per user, or should the language setting apply to the whole shop?

Open Question 5 Answer: the language setting should apply to the whole shop

## 2. Entry And Login Experience

The first screen is the login page. It contains a circular "SM" brand badge, the title "Shop Management", supporting sign-in text, a username field, a password field, and a Login button.

After login, the user enters the dashboard. The login does not need to support separate roles such as owner, manager, or staff.

Open questions:

Open question 6: Should login require only username and password, or should phone number login also be supported?

Open Question 6 Answer: login should require only username and password

Open question 7: Should the final login screen include a remember-me option?

Open Question 7 Answer: the final login screen should include a remember-me option.

Open question 8: Should failed login attempts show a simple error message or a more detailed reason?

Open Question 8 Answer: failed login attempts should show a simple error message.

Open question 9: Should the system support multiple user accounts later even if separate owner, manager, and staff roles are not needed now?

Open Question 9 Answer: Yes, later on the system should support multiple user accounts

## 3. Dashboard

The dashboard is the main hub after login. It currently provides access to:

- Client History
- Store House
- Advanced Settings

The dashboard no longer shows a direct New Client button. New clients are created from the Client History page. Store House opens the product store details area. Advanced Settings is available through the settings control near the bottom-right of the dashboard card.

The dashboard should eventually show summary numbers for total due, total deposit, and current stock alerts.

Open questions:

Open question 10: Should dashboard summary numbers appear above the main buttons or in a separate summary row?

Open Question 10 Answer: dashboard summary numbers should appear above the main buttons

Open question 11: Should stock alerts include both rod and cement, or only products below a minimum threshold?

Open Question 11 Answer: stock alerts should include both rod and cement.

Open question 12: Should the dashboard include a date filter for summary totals?

Open Question 12 Answer: the dashboard should include a date filter for summary totals.

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

Open questions:

Open question 13: Should client IDs be generated automatically?

Open Question 13 Answer: yes, client IDs should be generated automatically

Open question 14: Should search match partial text across all searchable fields at once?

Open Question 14 Answer: yes, search should match partial text across all searchable fields at once

Open question 15: Should the client table show total due or available deposit directly in the list?

Open Question 15 Answer: Yes, the client table should show total due and available deposit both directly in the list.

Open question 16: Should deleted or archived clients still appear in search results with an archived label?

Open Question 16 Answer: No, deleted or archived clients shouldn't appear in search results with an archived label.

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

Open questions:

Open question 17: After saving a new client, should the user go to Client History or directly to Client Summary?

Open Question 17 Answer: After saving a new client,the user should go to directly to Client Summary.

Open question 18: Should phone number be required before saving?

Open Question 18 Answer: Yes, phone number should be required before saving.

Open question 19: Should duplicate phone numbers be blocked or only warned about?

Open Question 19 Answer: duplicate phone numbers should be blocked.

Open question 20: Should phone numbers follow a Bangladesh mobile number format validation rule?

Open Question 20 Answer: Yes, phone numbers should follow a Bangladesh mobile number format validation rule

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

Open questions:

Open question 21: Should deleting a client be blocked if the client has transactions?

Open Question 21 Answer: deleting a client should be blocked if the client has transactions.

Open question 22: Should client deletion archive the client instead of permanently removing it?

Open Question 22 Answer: client deletion should archive the client instead of permanently removing it.

Open question 23: Should edit history be tracked for client profile changes?

Open Question 23 Answer: no, edit history should not be tracked for client profile changes.

Open question 24: Should archived clients be restorable later?

Open Question 24 Answer: No, archived clients shouldn't be restorable later

## 7. Client Summary

The Client Summary page shows the selected client's profile, financial totals, transaction actions, and transaction history. It includes Print, Edit, and Back actions at the top.

Client information should include:

- Client Name
- Phone
- Address
- Reference

Summary totals should include:

- Total deposit
- Available Deposit
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

Open questions:

Open question 25: Should Available Deposit mean total deposit minus total use, or should it only count unused cash deposits?

Open Question 25 Answer: Available Deposit should mean total deposit minus total use.

Open question 26: Should delivery status be shown for miscellaneous expense and deposit rows, or left blank as in the current wireframe?

Open Question 26 Answer: delivery status should be left blank as in the current wireframe. Delivery status only applicable for rod and cement rows.

Open question 27: Should Print on Client Summary print the whole summary or only the transaction table?

Open Question 27 Answer: Print on Client Summary should print the whole summary.

Open question 28: Should client balances show negative available deposit as due amount, or should due and available deposit always be displayed separately?

Open Question 28 Answer: due and available deposit should always be displayed separately

## 8. Product Selection

The Product Selection page starts the new purchase flow from Client Summary. It allows the user to choose:

- Rod
- Cement
- Misc Expense

Rod and Cement purchases should stay separate by product type. Misc Expense represents a client past due expense.

Open questions:

Open question 29: Should Product Selection show the selected client name so the user knows who the purchase belongs to?

Open Question 29 Answer: Product Selection should show the selected client name so the user knows who the purchase belongs to.

Open question 30: Should the page prevent continuing if no client is selected?

Open Question 30 Answer: yes, the page should prevent continuing if no client is selected

Open question 31: Should Misc Expense remain in the purchase flow or move to a separate client adjustment area?

Open Question 31 Answer: Misc Expense should move to a separate client adjustment area in client summary page.

Open question 32: Should transaction descriptions be auto-generated for rod and cement purchases, manually editable, or both?

Open Question 32 Answer: transaction descriptions should be auto-generated for rod and cement purchases

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

Open questions:

Open question 33: Should Delivery Status checked mean Completed and unchecked mean Pending?

Open Question 33 Answer: yes, Delivery Status should checked mean Completed and unchecked mean Pending

Open question 34: Should Other expense cost be added to the final transaction total?

Open Question 34 Answer: yes, Other expense cost should be added to the final transaction total.

Open question 35: Should each Add More rod entry create a separate transaction row or one combined transaction row?

Open Question 35 Answer: each Add More rod entry should create a separate transaction row.

Open question 36: Should the system prevent saving rod or cement sales when the delivery status is Completed but available stock is insufficient?

Open Question 36 Answer: Yes, the system should prevent saving rod or cement sales when the delivery status is Completed but available stock is insufficient

## 10. Cement Purchase Selection

The Cement Selection page collects cement purchase information in two bordered input groups. Each group includes:

- Purchase date
- CementBrand
- price/bag
- Cement category
- Total cement bag
- Total price
- other expense
- cost
- Delivery status

Cement category options are BM, AM, and OPC. CementBrand is currently fixed as SevenRings. Total price is fixed/read-only in the wireframe and should be calculated automatically from price/bag and Total cement bag.

The two cement data groups represent two different cement entries in one purchase. The second group includes a Delete action. The page also includes Add More, Save, and Back actions.

Open questions:

Open question 37: Should CementBrand eventually support more brands, or stay fixed to SevenRings?

Open Question 37 Answer: CementBrand eventually should stay fixed to SevenRings.

Open question 38: Should each cement group have its own delivery status and expense cost?

Open Question 38 Answer: each cement group should have its own delivery status and expense cost.

Open question 39: Should deleting a cement group require confirmation before removing it from the purchase form?

Open Question 39 Answer: deleting a cement group should require confirmation before removing it from the purchase form.

## 11. Misc Expense

The Misc Expense page records a client's past due or miscellaneous expense. It includes:

- Date
- Description
- Taka
- Save action
- Back action to Product Selection

Misc Expense should not support separate categories such as carrying, labor, transport, or miscellaneous because it represents the client's past due expense.

Open questions:

Open question 40: Should this feature be renamed to Past Due Expense everywhere for clarity?

Open Question 40 Answer: Yes, This feature should be renamed to Past Due Expense everywhere for clarity.

Open question 41: Should the default description be "Past expense" or should it always be entered manually?

Open Question 41 Answer: the default description should it always be entered manually.

Open question 42: Should Misc Expense affect stock in any way, or only client financial totals?

Open Question 42 Answer: Misc Expense should not affect stock in any way and also its only client financial totals.

## 12. New Deposit

The New Deposit page records money received from a client. It includes:

- Date
- Description
- Taka
- Save action
- Back action to Client Summary

Saving a deposit should return the user to Client Summary and update total deposit and available deposit.

Open questions:

Open question 43: Should deposit descriptions use a fixed list such as Cash, Bank, or Mobile Banking?

Open Question 43 Answer: Yes, deposit descriptions should use a fixed list such as Cash, Bank, or Mobile Banking.

Open question 44: Should deposits support attachment or reference numbers later?

Open Question 44 Answer: Maybe later on feature deposits support attachment or reference numbers, but for now, its ok.

Open question 45: Should a deposit be allowed if the taka amount is zero or negative?

Open Question 45 Answer: No, a deposit shouldn't be allowed if the taka amount is zero or negative

## 13. Misc Payment To Client

The Misc Payment To Client page records money paid back to the client. It includes:

- Date
- Description
- Take
- Save action
- Back action to Client Summary

This creates a Paid to Client transaction type in the Client Summary. Paid to Client should reduce the client's available deposit or otherwise affect the client's balance according to the final accounting rule.

Open questions:

Open question 46: Should the field label be "Take", "Taka", or "Amount Paid"?

Open Question 46 Answer: The field label should be Taka.

Open question 47: Should Paid to Client be allowed only when the client has an available deposit?

Open Question 47 Answer: Yes, Paid to Client should be allowed only when the client has an available deposit and after paid to client Total deposit should be reduce by the same amount.

Open question 48: Should Paid to Client appear in cash memos?

Open Question 48 Answer: Yes, Paid to Client should appear in cash memos.

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

Open questions:

Open question 49: Should editing rod or cement purchases update inventory stock immediately?

Open Question 49 Answer: Yes, editing rod or cement purchases should update inventory stock immediately.

Open question 50: Should delivery status changes update stock, client balance, or both?

Open Question 50 Answer: Delivery status should changes update stock, not client balance.

Open question 51: Should transaction edit pages show the original created date separately from the editable transaction date?

Open Question 51 Answer: No, transaction edit pages should not show the original created date separately from the editable transaction date

Open question 52: Should all dates default to today's date when creating deposits, purchases, payments, stock loads, and edits?

Open Question 52 Answer: all dates should default to today's date when creating deposits, purchases, payments, stock loads, and edits.

Open question 53: Should users be allowed to edit the date of a saved transaction after it has been created?

Open Question 53 Answer: Yes, users should be allowed to edit the date of a saved transaction after it has been created

Open question 54: Should every delete action require typing a confirmation word, or is a normal confirmation dialog enough?

Open Question 54 Answer: every delete action is a normal confirmation dialog enough

Open question 55: Should the system keep an audit log for deleted transactions and stock load changes?

Open Question 55 Answer: No, the system shouldn't keep an audit log for deleted transactions and stock load changes

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

Open questions:

Open question 56: Should cash memo include only transactions up to the selected memo date?

Open Question 56 Answer: Yes, cash memo should include only transactions up to the selected memo date.

Open question 57: Should pending delivery items appear on the cash memo?

Open Question 57 Answer: Yes, pending delivery items should appear on the cash memo, but delivery status should not be mentioned there.

Open question 58: Should the memo show shop information at the top?

Open Question 58 Answer: Yes, the memo should show shop information at the top center.

Open question 59: Should cash memos be saved as records after printing, or generated only when needed without storing memo history?

Open Question 59 Answer: cash memos should be generated only when needed without storing memo history.

Open question 60: Should cash memo numbers be generated automatically?

Open Question 60 Answer: cash memo numbers should be generated automatically

Open question 61: Should cash memo numbers reset yearly, monthly, or never reset?

Open Question 61 Answer: cash memo numbers should reset yearly.

Open question 62: Should printed cash memos include the logged-in user's name as the prepared-by person?

Open Question 62 Answer: No, printed cash memos shouldn't include the logged-in user's name

## 16. Product Store Details

The Product Store Details page is the Store House entry page from the dashboard. It allows the user to choose:

- Rod
- Cement

It includes a Back action to the dashboard.

Open questions:

Open question 63: Should Store House show stock alerts before choosing Rod or Cement?

Open Question 63 Answer: Store House should show stock alerts before choosing Rod or Cement.

Open question 64: Should Store House include a combined printable stock summary?

Open Question 64 Answer: Store House should include a separate printable stock summary.

Open question 65: Should other product categories be supported later, or only rod and cement?

Open Question 65 Answer: It should only support rod and cement.

Open question 66: Should pending rod and cement sales reserve stock, or should stock only reduce after delivery is marked Completed?

Open Question 66 Answer: stock should only reduce after delivery is marked Completed

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

Open questions:

Open question 67: Should Print on Rod Store Details include all rod inventory rows?

Open Question 67 Answer: yes, Print on Rod Store Details should include all rod inventory rows.

Open question 68: Should Remaining Weight be displayed in kg only?

Open Question 68 Answer: yes, Remaining Weight should be displayed in kg only

Open question 69: Should the table support filtering by brand or size?

Open Question 69 Answer: Yes, the table should support filtering by brand or size.

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

Open questions:

Open question 70: Should Load Rod allow multiple load entries at once?

Open Question 70 Answer: No, Load Rod shouldn't allow multiple load entries at once.

Open question 71: Should Load Weight accept only numeric kg values?

Open Question 71 Answer: Yes, Load Weight should accept only numeric kg values.

Open question 72: Should loading rod create a stock history row with status Load automatically?

Open Question 72 Answer: yes, loading rod should create a stock history row with status Load automatically.

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

Edit buttons appear only for load rows, not sell rows. Sell rows should link back to the client transaction that created the sale. Deleting a loaded rod entry should reduce the Total Load remaining stock immediately.

Open questions:

Open question 73: Should sell rows open Client Summary or the specific rod transaction edit page?

Open Question 73 Answer: No, sell rows shouldn't open Client Summary or the specific rod transaction edit page.

Open question 74: Should Total sell include only completed deliveries or all rod sale transactions?

Open Question 74 Answer: Total sell should include only completed deliveries.

Open question 75: Should a warning appear when remaining stock becomes negative?

Open Question 75 Answer: a warning should appear when remaining stock becomes negative and block to complete any rod sell transaction.

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

Open questions:

Open question 76: Should the static status label use "load" or "Load" in the final UI?

Open Question 76 Answer: the static status label should use "Load" in the final UI.

Open question 77: Should changing loaded weight be blocked if later sales depend on that stock?

Open Question 77 Answer: No, changing loaded weight shouldn't be blocked if later sales depend on that stock

Open question 78: Should the edit page show the selected rod brand and size?

Open Question 78 Answer: Yes, the edit page should show the selected rod brand and size.

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

Open questions:

Open question 79: Should Print on Cement Store Details include all cement categories?

Open Question 79 Answer: Print on Cement Store Details should include all cement categories.

Open question 80: Should Current amount always mean bag count?

Open Question 80 Answer: Current amount should always mean bag count.

Open question 81: Should the table support filtering if more cement brands are added later?

Open Question 81 Answer: Yes, if later on more cement brands are added then the table should support filtering.

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

Open questions:

Open question 82: Should Load Cement allow multiple cement load entries at once?

Open Question 82 Answer: No, Load Cement shouldn't allow multiple cement load entries at once.

Open question 83: Should Load amount accept only whole bag counts?

Open Question 83 Answer: yes, Load amount should accept only whole bag counts.

Open question 84: Should loading cement create a stock history row with status Load automatically?

Open Question 84 Answer: Yes, loading cement should create a stock history row with status Load automatically.

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

Edit buttons appear only for load rows, not sell rows. Cement stock should be tracked by bag count only. Deleting stored cement should require checking whether any later sales depend on that stock.

Open questions:

Open question 85: Should sell rows open Client Summary or the specific cement transaction edit page?

Open Question 85 Answer: No, sell rows shouldn't open Client Summary or the specific cement transaction edit page.

Open question 86: Should Total sell include only completed deliveries or all cement sale transactions?

Open Question 86 Answer: Total sell should include only completed deliveries.

Open question 87: Should stock history use "Quantity" everywhere instead of "Remaining"?

Open Question 87 Answer: Yes, stock history should use "Quantity" everywhere instead of "Remaining".

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

Open questions:

Open question 88: Should the editable quantity field be named Remaining, Quantity, or Load amount?

Open Question 88 Answer: the editable quantity field should be named Quantity.

Open question 89: Should changing stored cement be blocked if later sales depend on that stock?

Open Question 89 Answer: No, changing stored cement shouldn't be blocked if later sales depend on that stock.

Open question 90: Should the edit page show the selected cement brand and category?

Open Question 90 Answer: Yes, the edit page should show the selected cement brand and category.

## 25. Advanced Settings

Advanced Settings is accessible from the dashboard settings control. It includes:

- Logged In Device
- Data Restore
- Data backup
- Logout
- Back action to Dashboard

Logout should ask for confirmation before returning to the login page.

Open questions:

Open question 91: Should Logout appear as a destructive action visually?

Open Question 91 Answer: Logout shouldn't appear as a destructive action visually.

Open question 92: Should settings include shop profile or brand customization later?

Open Question 92 Answer: settings should be included shop profile or brand customization.

Open question 93: Should backup and restore be grouped under a Data Management heading?

Open Question 93 Answer: backup and restore should be grouped under a Data Management heading.

## 26. Logged In Device

The Logged In Device page shows active or previously logged-in devices. It includes:

- Device Name
- Location
- Last Active
- Status
- Remove action
- Back action to Advanced Settings

The final system should allow removing other devices remotely.

Open questions:

Open question 94: Should the current device be removable?

Open Question 94 Answer: the current device shouldn't be removable.

Open question 95: Should device location be exact location, city only, or user-entered text?

Open Question 95 Answer: device location should be exact location or minimum city.

Open question 96: Should removing a device require confirmation?

Open Question 96 Answer: removing a device should require confirmation.

## 27. Data Backup

The Data Backup page allows the user to prepare or download a backup of shop data. Backup data may include clients, transactions, stock, and settings.

The preferred backup format is Excel/CSV.

Open questions:

Open question 97: Should backup create one Excel workbook with multiple sheets or separate CSV files?

Open Question 97 Answer: backup should create separate CSV files.

Open question 98: Should backup include printed memo history if that exists later?

Open Question 98 Answer: No, backup shouldn't include printed memo history if that exists later.

Open question 99: Should backup files include the backup date in the filename?

Open Question 99 Answer: yes, backup files should include the backup date in the filename.

Open question 100: Should backup and restore include archived clients and deleted transaction history if audit logs are added later?

Open Question 100 Answer: No, backup and restore shouldn't include archived clients and deleted transaction history

## 28. Data Restore

The Data Restore page allows the user to choose a backup file and restore shop data. Restore should merge backup data with existing data.

Because restore can affect existing records, the page should clearly warn the user before restoration.

Open questions:

Open question 101: When duplicate records are found, should restore skip, overwrite, or create a duplicate copy?

Open Question 101 Answer: When duplicate records are found, it should be overwritten.

Open question 102: Should restore preview the number of clients, transactions, and stock rows before confirming?

Open Question 102 Answer: Yes, restore should preview the number of clients, transactions, and stock rows before confirming.

Open question 103: Should restore require a second confirmation step?

Open Question 103 Answer: restore should require a second confirmation step.

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

Open questions:

Open question 104: Should Cancel and Back be standardized into one label?

Open Question 104 Answer: No, Cancel and Back shouldn't be standardized into one label.

Open question 105: Should Save actions always return to the previous page?

Open Question 105 Answer: Save actions should always follow the next step.

Open question 106: Should Print actions keep the user on the same page after printing?

Open Question 106 Answer: Yes, Print actions should keep the user on the same page after printing

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

Open questions:

Open question 107: What custom brand colors should replace the current Bootstrap-style defaults?

Open Question 107 Answer: Not yet decided.

Open question 108: Should Completed and Pending use text only, badges, or icons?

Open Question 108 Answer: Completed and Pending should be badges.

Open question 109: Should printable pages use a different cleaner print layout than screen pages?

Open Question 109 Answer: yes, printable pages should use a different cleaner print layout than screen pages.

Open question 110: Should currency values always show the Taka symbol, or should they display plain numbers with field labels?

Open Question 110 Answer: currency values should always show the Taka symbol
