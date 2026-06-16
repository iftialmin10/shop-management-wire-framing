# Rod/Cement Management Website Specification

## 1. Project Overview

The website is a shop management system for tracking clients, rod purchases, cement purchases, deposits, other expenses, inventory stock, cash memos, and administrative settings. The experience begins with a simple login screen branded as "Shop Management" and continues into a dashboard where the user can choose core workflows.

The system should support daily operational use by a shop owner or staff member who needs to record client activity, manage rod and cement stock, review customer balances, and generate cash memo summaries.

Open question 1: Should this website be designed for a single shop only, or should it support multiple branches/shops in the future?

## 2. Entry And Login Experience

The first screen is the login page. It contains the shop brand mark, the title "Shop Management", a username field, a password field, and a Login button. After login, the user enters the dashboard.

The login screen should feel simple and direct. It should not include extra navigation or complex setup actions. The purpose is only to identify the user and open the management dashboard.

Open question 2: Do you want the login to support different roles, such as owner, manager, and staff?

## 3. Dashboard

The dashboard is the main hub after login. It should provide access to:

- New Client
- Client History
- Product Details
- Settings

The settings control should appear as a gear/settings control near the bottom-right area of the dashboard. Logout should be available from the settings area rather than the main dashboard.

Open question 3: Should the dashboard show summary numbers, such as total due, total deposit, or current stock alerts?

## 4. Client Management

The client workflow should allow the user to create a new client, view client history, edit client information, and open a client summary page. Client records should include:

- Client name
- Phone
- Address
- Reference

The Client History page should show clients in a table. The table should include ID, phone, name, address, and reference. Selecting a client row should open that client's summary.

Open question 4: Should client search support only name and phone, or should it also search by address and reference?

## 5. Client Summary

The Client Summary page should show the selected client's profile information, financial totals, action buttons, and a transaction table.

The top client information should include:

- Client Name
- Phone
- Address
- Reference

The summary totals should include:

- Total deposit
- Total debt
- Total use

The action area should include:

- New Purchase
- New Deposit
- Cash memo date text
- Generate cash-memo

The transaction table should include date, description, taka, transaction type, and edit action. Transaction type should clearly identify the source of spending:

- Spend, Rod
- Spend, Cement
- Spend, Other
- Deposit

Only "Spend," should be red. Rod should be blue, Cement should be green, and Other should be yellow.

Open question 5: Should the financial totals be calculated from the transaction rows automatically, or entered manually for now?

## 6. Purchases

The New Purchase flow should start from Product Selection. The user should choose one of:

- Rod
- Cement
- Other Expense

Rod and Cement purchases should use separate selection pages. Other Expense should use a simpler expense entry page.

Open question 6: Should a single purchase be allowed to include both rod and cement together, or should each purchase stay separate by product type?

## 7. Rod Purchase Selection

The Rod Selection page should collect rod purchase details in one bordered input group. Required fields include:

- R-brand
- R-size
- Price/Kg
- Total weight
- Total cost
- Other expense
- Other expense cost

R-brand should be a dropdown with:

- BSRM
- KSRM
- AKS

R-size should be a dropdown with:

- 6mm
- 8mm
- 10mm
- 12mm
- 16mm
- 20mm

Total cost should be static and not editable. The page should include Add More and Save actions at the bottom.

Open question 7: Should total cost be automatically calculated from Price/Kg and Total weight?

## 8. Cement Purchase Selection

The Cement Selection page should collect cement purchase details in two bordered data groups. Each group should include:

- CementBrand
- price/bag
- Cement category
- Total cement bag
- Total price
- other expense
- cost

Cement category should be a dropdown with:

- BM
- AM
- OPC

CementBrand and Total price should be fixed and not editable. The page should include Add More, Delete, and Save actions.

Open question 8: Should the two cement data groups represent two different cement entries in one purchase?

## 9. Other Expense

The Other Expense page should collect:

- Date
- Description
- Taka

Default sample values should include:

- Date: 12/12/25
- Description: Other expense
- Taka: 5000

The page should include Save and Back actions. It should not include a Delete button.

Open question 9: Should Other Expense support categories such as carrying, labor, transport, or miscellaneous?

## 10. Transaction Editing

The system should provide editing pages for:

- Deposit
- Rod expense
- Cement expense
- Other expense

Edit Rod Expense should include rod brand, R-size, price/kg, total weight, total cost, other expenses, other expense cost, and cost. Rod brand and R-size should be dropdowns. Total cost and Cost should be fixed and not editable.

Edit Cement Expense should include cement brand, price/bag, cement category, total cement bag, total price, other expense, other expense cost, and cost. Cement category should be a dropdown. Cement brand, total price, and cost should be fixed and not editable.

Edit Other Expense should include date, description, and taka. Default sample values should include Date 12/12/25, Description Other Expense, and Taka 5000.

Open question 10: Should edit pages allow deleting saved records, or should delete actions require a confirmation step?

## 11. Cash Memo

The Cash Memo page should be opened from the Client Summary page after pressing Generate cash-memo. It should show client information at the top:

- Name
- Address
- Phone
- Date

The memo table should show:

- Description
- Amount
- Cost/Unit
- Total Cost

It should include rows for past due, product purchase, total due, deposit, and current due. The page should also include buyer and seller signature areas and a Print button before the table section.

Open question 11: Should the cash memo be printable only, or should it also be downloadable as a PDF?

## 12. Product Store Details

The Product Details page should allow the user to choose between Rod and Cement store details.

Rod Store Details should show rod inventory rows with:

- R-size
- Brand
- Remaining Weight
- Add rod

R-size and Brand should be dropdowns. Selecting a row should open Rod Stock. Add should open the Add Rod Store page.

Cement Store Details should show cement inventory rows with:

- Brand-Name
- Categories
- Current amount
- Add

Categories should be a dropdown. Selecting a row should open Cement Stock. Add should open the Add Cement Store page.

Open question 12: Should changing dropdown values in these tables update the stock item, or are they only visual placeholders for the wireframe?

## 13. Rod Stock

The Rod Stock page should show rod history for a selected rod size and brand. It should include a history label, remaining stock summary, and a stock history table.

The table should include:

- Date
- Status
- Weight
- Edit

Edit buttons should appear only for load rows, not sell rows. Pressing Edit on a load row should open the Edit Loaded Rod Date and Weight page.

Open question 13: Should sell rows link back to the client transaction that created the sale?

## 14. Edit Loaded Rod

The Edit Loaded Rod Date and Weight page should include:

- Date input
- Status static value: load
- Weight input

It should include Back, Delete, and Save actions. Back, Delete, and Save should return to the Rod Stock page.

Open question 14: Should deleting a loaded rod entry reduce the remaining stock immediately?

## 15. Cement Stock

The Cement Stock page should show cement history for a selected brand and category. It should include the label "BM(SevenRings) History", remaining amount summary, and a stock history table.

The table should include:

- Date
- Status
- Remaining
- Edit

Edit buttons should appear only for load rows, not sell rows. Pressing Edit on a load row should open the Edit Stored Cement page.

Open question 15: Should cement stock be tracked by bag count only, or should it also track purchase price by batch?

## 16. Edit Stored Cement

The Edit Stored Cement page should include:

- Date input
- Status static value: load
- Remaining input

It should include Back, Delete, and Save actions. Back, Delete, and Save should return to the Cement Stock page.

Open question 16: Should deleting stored cement require checking whether any later sales depend on that stock?

## 17. Add Rod Store

The Add Rod page should allow the user to add rod stock information. It should include fields for rod brand, rod size, and rod weight. It should include Delete and Save actions. Delete and Save should return to Rod Store Details.

Open question 17: Should Add Rod support adding multiple rod entries at once?

## 18. Add Cement Store

The Add Cement Store page should allow the user to add cement stock information. Brand-Name and Categories should be fixed/static. Amount should be editable. The page should include Delete and Save actions. Delete and Save should return to Cement Store Details.

Open question 18: Should Add Cement Store automatically use the selected brand/category from the Cement Store Details row?

## 19. Advanced Settings

Advanced Settings should be accessible from the dashboard settings control. The page should include:

- Logged In Device
- Data Restore
- Data backup
- Logout

Each option should open its related page or perform its related action. Back should return to the dashboard.

Open question 19: Should Logout ask for confirmation before returning to the login page?

## 20. Logged In Device

The Logged In Device page should show a table of active or previously logged-in devices. Each row should include device details and a Remove button. The Remove button should only be shown as a button in the wireframe and should not remove any device yet.

Open question 20: Should the final system allow removing other devices remotely?

## 21. Data Backup

The Data Backup page should allow the user to prepare or download a backup of shop data. The page should communicate that backup data may include clients, transactions, stock, and settings.

Open question 21: What backup format do you prefer: Excel/CSV, JSON, or database file?

## 22. Data Restore

The Data Restore page should allow the user to choose a backup file and restore previous shop data. Because restore can replace current records, the page should clearly warn the user before restoration.

Open question 22: Should restore replace all current data, or merge backup data with existing data?

## 23. Navigation Rules

Navigation should stay clear and predictable:

- Login opens Dashboard
- Dashboard opens client, product, and settings areas
- Client History opens Client Summary
- Client Summary opens purchases, deposit, edit pages, and cash memo
- Product Details opens rod and cement store areas
- Stock pages return to their store details pages
- Edit stock pages return to their stock pages
- Settings pages return to Advanced Settings or Dashboard as appropriate

Open question 23: Should every page include a Back button, even if the browser back button is available?

## 24. Visual And Interaction Guidelines

The interface should follow the existing wireframe style:

- Centered card layouts
- Bootstrap-style form controls and buttons
- Clear table-based records
- Simple action buttons
- Bordered boxes for grouped input fields
- Static fields styled like form controls when values should not be edited

The design should remain practical and operational rather than decorative.

Open question 24: Do you want the final design to stay close to Bootstrap defaults, or should it receive a custom brand style later?
