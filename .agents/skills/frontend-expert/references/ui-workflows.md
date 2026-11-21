# ShipTest URLs and UI workflows

The default local origin is `http://localhost:3000`. Use the current ShipTest tab's origin if it runs on another port or host. If the user names a different ShipTest environment, use that environment. Check the page heading before acting. If redirected to sign-in, follow the available sign-in flow before continuing.

| Task | URL at the default origin | What to look for |
| --- | --- | --- |
| Sign in | http://localhost:3000/login | Email and password form |
| Register | http://localhost:3000/register | Account and contact form |
| Create shipment | http://localhost:3000/ | Create a New Shipment |
| Find shipments | http://localhost:3000/shipments | My Shipments and the Your shipments table |
| View shipment | `http://localhost:3000/shipments/{id}` | Tracking number or draft heading and shipment details |
| Edit draft | `http://localhost:3000/?edit={id}` | Edit Shipment |
| Repeat finalized shipment | `http://localhost:3000/?repeat={id}` | Repeat Shipment |
| Ask about shipping rules | http://localhost:3000/assistant | Shipping Rules Assistant |

Replace `{id}` with the numeric shipment ID. When the user supplies a tracking number, find its row in My Shipments, open `Actions for <tracking number>`, and use the View or Repeat menu item. For a draft, use its row menu. Learn the numeric ID from the actual link when needed. The success query parameter on the list shows a banner and is not needed to find records.

## Fill a shipment

1. Open the create, edit, or repeat URL for the requested operation. Wait for the form and any prefilled data. Review the read-only Sender Information. On edit or repeat, preserve prefilled fields the user did not ask to change.
2. In Receiver Information, select the requested country on `#receiverCountry` by its visible option. Wait for rules to refresh, then fill `#receiverName`, `#receiverPhone`, `#receiverCity`, `#receiverPostalCode`, and `#receiverStreet` as applicable. Check field or route errors before moving on. Use sample data only when the user asks for it or authorizes it.
3. In Package Information, fill `#weight` in kg and `#length`, `#width`, `#height` in cm. Fill `#itemDescription` if visible and required. Wait for eligible service radios to appear. Select the requested service by its name within Service Selection.
4. In Additional Options, use the actual checkbox labels and pickup radio labels. Respect forced values such as locked signature and disabled Home Pickup. Check the Rate section after service or option changes. See [form fields](form-fields.md) and [business behavior](frontend-map.md) for the conditions.
5. If asked only to fill the form, verify the values and leave it open. If asked to save or finalize, use the matching footer action and verify the success banner and resulting row, or report validation errors. To finalize an existing draft, save any requested edits first and use Finalize Shipment from the list or detail page. At the reviewed revision, the edit form footer writes the draft without finalizing it.

## Use the other pages

- **My Shipments:** Filter with Status or Type as needed. Scope actions to the right row. For details, choose View. For repeat, choose Repeat on a finalized row. For draft edits, choose Edit. For finalization, choose Finalize Shipment on a draft. Verify the status and tracking reference after a requested change.
- **Login and registration:** Locate login fields by `#email` and `#password`. Registration uses those plus `#confirmPassword`, `#fullName`, `#phone`, `#country`, `#city`, `#postalCode`, and `#street`. Use user-provided details through the available sign-in flow and verify the result before continuing.
- **Rules Assistant:** Fill the Your question textbox and use Ask, or click a matching sample question. Read the Answer section and source cards when present. For booking form assistance, open the floating assistant from the booking page and review any proposal before applying it.
