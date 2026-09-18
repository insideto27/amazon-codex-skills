# US automotive emissions listing gate

Use for US Amazon listings involving engine controls, OBD devices, ECU/ECM signals, calibrations, DTC/MIL behavior, cylinder deactivation, AFM/DFM/DoD, exhaust or emissions-related parts.

## Hard gate

Classify as `RED-PRODUCT` and choose `BLOCK` or `HOLD` when a product's stated or known principal effect may bypass, defeat, disable, render inoperative or materially alter an OEM emissions-control device or certified element of design, unless a documented reasonable basis covers the exact product and vehicles.

Wording changes do not cure this classification. Do not generate euphemisms such as `mode optimizer`, `engine behavior controller`, `V8 mode keeper` or `driving accessory` to conceal the function.

## Required current sources

Re-open these sources during each review:

- Amazon Automotive Restricted Products: https://sellercentral.amazon.com/help/hub/reference/200164410
- Amazon Restricted Products: https://sellercentral.amazon.com/gp/help/200164330
- EPA Tampering Policy: https://www.epa.gov/enforcement/epa-tampering-policy-epa-enforcement-policy-vehicle-and-engine-tampering-and
- EPA Enforcement Alert: https://www.epa.gov/sites/default/files/2020-12/documents/tamperinganddefeatdevices-enfalert.pdf
- CARB Aftermarket Parts Database: https://ww2.arb.ca.gov/applications/aftermarket-parts-database
- CARB manufacturer guidance: https://ww2.arb.ca.gov/manufacturers-aftermarket-parts

## Evidence hierarchy

Accept a path only after confirming one of these and Amazon's own acceptance:

1. A CARB Executive Order covers the same device, brand or authorized private label, part number/firmware and exact vehicle applications.
2. The modified vehicle meets applicable emissions standards using relevant OEM-certification procedures, supported by qualified independent testing and raw records.
3. A genuine identical-in-design-and-function replacement-part basis applies. Do not use this for an add-on device that changes OEM control behavior.

Supplier statements, competitor listings, CE/RoHS/FCC reports, current-draw measurements, ordinary functional tests and disclaimers are not substitutes.

## High-risk language audit

Treat these as indicators, not a complete banned-word list:

- Direct defeat language: `defeat`, `bypass`, `shut down`, `disable`, `delete`, `render inoperative`, `override malfunction indicator light`.
- Product-specific: `AFM disabler`, `DFM disabler`, `disable Active Fuel Management`, `disable cylinder deactivation`, `full-cylinder operation`, `keep V8/V6 mode`, `DoD delete`, `AFM delete`.
- Control/calibration: `ECU tune`, `reflash`, `programmer`, `calibration`, `controller that changes engine behavior`, `zero trace`, `reversible bypass`.
- Context amplifiers: `OBD2`, `DTC`, `check engine light`, `fault indicator`, `fuel economy`, `engine protection`, `prevent lifter failure`.
- Unsubstantiated compliance: `EPA approved/certified`, `CARB compliant`, `50-state legal`, `street legal`, `no emissions impact`, `will not void warranty`.

Negative constructions such as `not a delete kit` still repeat high-risk terminology and do not change the function.

## AFM/DFM rule

When copy or product facts say a device disables Active/Dynamic Fuel Management, cylinder deactivation or keeps an engine in full-cylinder operation, default to `BLOCK` for Amazon US publish-ready copy until exact emissions evidence and Amazon written acceptance are provided. Do not create a supposedly safe synonym version.

Require: hardware/firmware functional description, signal path, commands sent, effect on ECU/OBD/DTC/MIL, firmware version control, exact fitment matrix, emissions evidence, CARB EO/private-label coverage if applicable, and the Amazon case decision.
