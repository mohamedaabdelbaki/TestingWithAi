# ShipTest route map and business behavior

Baseline source revision [447c72c](https://github.com/mohamedaabdelbaki/ship-app/tree/447c72c4b4eca87f1b4906052eecb4fdd8bd6373). The [source inventory](elements.md) indexes rendered markup and conditional blocks across every route and shared UI component. The [form field catalog](form-fields.md) includes generated control IDs, labels and rule defaults.

| Route or mode | Location, sections and behavior |
| --- | --- |
| Shared layout | Signed-in sidebar has QAcart home branding, account initials/name/email, Main navigation with Create Shipment and My Shipments, and Log Out. Exactly matching nav links receive aria-current. Login/register use the public layout. The floating assistant appears on the root route including edit/repeat. |
| /login | Email and password, submit and register link. Required inputs, pending button state, error alert. Successful login returns to shipment creation. |
| /register | Email, password, confirmation, full name, phone, country, city, postal code and street, submit and sign-in link. Password confirmation must match. Registration requires a street and has its own phone validation. Successful registration signs the user in. |
| / | Create a New Shipment. Sender and Receiver on the left. Package follows contacts. Service Selection, Additional Options and Rate are in the second column at wide widths. Save as Draft and Finalize Shipment are footer buttons. |
| /?edit={id} | Reuses the booking form with an existing shipment. Draft changes go through PUT. At this revision the edit form's Finalize Shipment handler also takes the PUT path. Use list or detail finalization for the existing draft transition. |
| /?repeat={id} | Reuses the create form, prefills data from an existing record and creates a separate shipment when submitted. |
| /shipments | Dashboard and My Shipments heading, + Create Shipment link, optional success/error notices, Total Shipments/Draft/Finalized counters, Status and Type filters, empty state or Your shipments table, transient row menu, delete confirmation and conditionally shown promotional dialog. |
| /shipments/{id} | Back link, heading/reference and status, sender, receiver, package, service/options and cost sections. Draft actions include edit and finalization. Finalized actions include Repeat. Delete opens a confirmation. Loader scopes records to the signed-in owner. |
| /assistant | Shipping Rules Assistant page. Question input, Ask, sample question buttons, loading/error, Answer region and conditional source cards. Separate from the form chat. Blank question disables Ask. |

## Booking conditions

| Area | Location and rules |
| --- | --- |
| Sender Information | Read-only summary. New shipments prefill the signed-in account. Edit and repeat hydrate the stored sender. Completion of required sender values enables Receiver. |
| Receiver Information | Text inputs and Country select are generated from receiver rules. Receiver completion checks required values and route errors, while blur checks lengths, patterns and numeric ranges as applicable. Gulf destinations require street. Gulf origin to Iraq raises a route error and blocks the next step. |
| Package Information | Enabled after receiver completion. Same country is Domestic (50 kg), two different Gulf countries are IntraGulf (30 kg), others International (25 kg). Positive numbers are required to progress. Form field bounds are 0.1 kg minimum and 1–200 cm per dimension. Item Description appears and becomes required from outside the Gulf into the Gulf. Finalization validation differs from blur validation, so check both paths when answering. |
| Service Selection | Enabled after package completion. Each available service is a radio card with name, description, maximum weight, estimate and price. Options depend on route type and weight. A previously selected service is cleared if removed by refreshed rules. |
| Additional Options | Enabled after package completion, even before service selection. Egypt or Jordan destination forces signature on and locks it. Home pickup defaults on, but above 17 kg it is disabled and postal-office drop-off is forced unless the origin is Iraq. Liquid, insurance and packaging remain selectable. |
| Rate | Selecting a service triggers quote. Weight, countries, pickup and flags reprice. Base = service start + weight × rate + pickup. Signature 5, liquid 10, insurance 15, packaging 8 USD when applicable. Finalization recalculates. Stored shipment totals can include liquid even when the returned separate liquid line is zero. |
| Footer and errors | Save as Draft tolerates incomplete details. Finalize checks selected service and business rules. Both are disabled while submitting. Field errors are associated with fields and general submission errors appear above the form. Successful writes go to /shipments?success=true. |

## Table and interactive states

- Use `getByRole('table', {name:'Your shipments'})`. Actual columns are Actions, Tracking Number, Sender, Receiver, Destination, Type and Status. Price and weight are available in details. Draft rows show a dash in the tracking column.
- Select a finalized row by its tracking-number row header or the exact button name `Actions for <tracking number>`. Draft button name is `Actions for draft shipment <numeric ID>`. The menu shares the button label. Scope menuitems to the open menu. View and Delete are common. Edit and Finalize Shipment are draft-only. Repeat is for finalized rows. Escape or an outside click closes the menu.
- Use `getByRole('combobox', {name:'Status'})` or Type. Filters are reflected in the URL. The loader returns up to 100 matching owned shipments ordered newest-first. The counters derive from the loaded rows.
- The Delete Shipment dialog has Cancel and confirmation. The action removes the record. The promotional dialog is informational and the displayed offer does not change the rate calculator.
- The floating chat opens via the Open assistant button. It shows a conversation, loading and error feedback, tool labels, optional proposal and Apply control. The user must apply a proposal to alter the form. The booking process remains available independently of the assistant.

## Locator examples

| Control | Locator |
| --- | --- |
| Receiver country | `page.locator('#receiverCountry')` |
| Package weight | `page.locator('#weight')` |
| Save as Draft | `page.getByRole('button', {name:'Save as Draft', exact:true})` |
| Finalized shipment actions | `page.getByRole('button', {name:'Actions for ' + tracking, exact:true})` |
| Details from opened row menu | `page.getByRole('menu').getByRole('menuitem', {name:'View', exact:true})` |
| Rules Assistant question | `page.getByRole('textbox', {name:'Your question'})` |

The app deliberately avoids data-testid attributes. Dynamic required labels can include “(required)” in accessible names. Use stable field IDs where labels include extra text, and treat component source, translations and live markup as complementary evidence.

## Live verification

The signed-in browser showed the shipment list and finalized row menu, create form, populated Repeat form, shipment details and Rules Assistant. The Jordan repeat form showed signature checked and disabled, and exposed the package fields, service radios and option controls. Login and registration redirected to create while signed in. Their forms, draft-only states, destructive confirmations and assistant response states are documented from source. No shipment was submitted or modified during inspection.
