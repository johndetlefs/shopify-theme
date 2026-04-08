## User Story

As a shopper viewing a product page, I want the product images displayed beside the product details and purchase controls, so that I can review the product and make a purchase without excessive scrolling.

## Goal

- Deliver a responsive product detail page layout that places product media in a left column and product details and purchase controls in a right column on larger viewports, while preserving a usable mobile experience and existing purchase behavior.

## Approach

- Keep the current product content and form behavior intact, and change the PDP through minimal markup grouping plus responsive styling.
- Treat the existing product section as the source of truth for title, price, description, variant selection, quantity, add-to-cart, and dynamic checkout behavior.
- Use a balanced two-column layout for desktop and tablet widths so media and purchase content receive similar visual weight.
- Implement the layout incrementally so desktop and tablet placement can be validated before mobile stacking and polish are finalized.

## Phases

### Phase 1

- Changes: Group the current product media and product information into explicit left and right layout regions in the product section, preserving the existing content and form controls.<br>Apply responsive styles so desktop and tablet widths present a stable two-column PDP layout.
- Validation: In theme preview, open a product with multiple images and variants and confirm desktop and tablet widths show images on the left and product details with purchase controls on the right.<br>Confirm variant selection, quantity entry, add-to-cart, and dynamic checkout still render and submit normally.
- Tracker updates: Keep story status at `Analysing` while the plan is under review.<br>When implementation starts, move the story to `In Progress` and Task 1 to `In Progress`.

### Phase 2

- Changes: Add mobile layout behavior so the PDP stacks into a single column without clipped or overlapping content.<br>Adjust spacing and layout rules as needed so the updated structure remains readable and accessible across breakpoints.
- Validation: In theme preview, verify the PDP remains two-column on tablet widths and stacks cleanly on mobile widths.<br>Retest purchase interactions after the responsive changes to confirm no regression.
- Tracker updates: Move the story to `Testing` after preview validation is complete.<br>Only move the story to `Complete` after validation is confirmed and explicitly approved.

## Task List (for IMPLEMENTATION.md)

|  ID | Title                                       | Description                                                                                                                                                                                                      | Acceptance Criteria                                                                                                                                                                                                                                                                                                                                    | User Verification                                                                                                                                                                                                                                                                     | Status |
| --: | ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
|   1 | Add side-by-side PDP layout                 | The product page shows product media in a balanced left region and the existing product details and purchase controls in a balanced right region on larger viewports without changing product purchase behavior. | - Desktop widths show product images on the left and title, price, description, variant selector, quantity, add-to-cart, and dynamic checkout on the right in a balanced two-column layout.<br>- Tablet widths keep the same balanced two-column layout.<br>- Products with multiple images and variants still render correctly in the updated layout. | - Open a product page in theme preview on desktop and tablet widths.<br>- Confirm the image gallery stays on the left and the product information and purchase controls stay on the right with roughly equal visual space.<br>- Select a variant and confirm the form remains usable. | To Do  |
|   2 | Preserve mobile usability and purchase flow | The updated product page remains readable on mobile by stacking into a single column while keeping purchase interactions functional.                                                                             | - Mobile widths stack the product images and product details into a single-column layout.<br>- No product content or controls are clipped, overlapped, or inaccessible on mobile.<br>- Variant selection, quantity entry, add-to-cart, and dynamic checkout continue to work after the responsive changes.                                             | - Open the same product page in a mobile viewport.<br>- Confirm the page stacks into one column and all product content remains visible.<br>- Change the variant, adjust quantity, add the product to cart, and confirm dynamic checkout still appears and works.                     | To Do  |

## Files / Areas Likely to Change

- `sections/product.liquid` for layout grouping and content structure.
- `assets/critical.css` for responsive product page layout styles shared across the storefront.

## Data / RLS / RPC / Migrations

- None. This is a Shopify theme layout change with no database, API contract, or migration work.

## Risks & Mitigations

- Risk: Re-grouping the product section markup could unintentionally affect product form behavior.<br>Mitigation: Keep the existing form fields and submit controls intact and validate the full purchase flow in preview.
- Risk: Image and product-form content may compete for space at intermediate viewport widths.<br>Mitigation: Validate tablet-specific layout behavior explicitly and tune column sizing and spacing before mobile stacking.
- Risk: Responsive changes could introduce clipping or overlap for longer product descriptions or dynamic checkout controls.<br>Mitigation: Test with longer content and confirm vertical stacking on mobile resolves space constraints.

## Notes

- Task: TASK-001
- Title: Basic Product Page layout
- Created: 2026-04-08
