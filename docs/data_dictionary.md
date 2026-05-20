# Data Dictionary & Business Definitions

## Pricing & Risk Metrics

| Metric | Definition |
|---|---|
| Frequency | count_claims / exposure |
| Severity | Adjusted claims divided by number of claims |
| Expected Loss | Frequency × Severity |
| Loss Ratio | Claims / Premiums |
| Exposure | Annualized exposure calculated as policy_duration / 365 |

---

## Metrics adjusted by inflation (Adj added to the name)

| Field | Description |
|---|---|
| Claim_Adj | Claim amount adjusted to constant 2017 Ethiopian Birr (ETB) using inflation factors |
| Premium_Adj | Premium adjusted to constant 2017 ETB |

---

## Simulation Metrics

| Metric | Definition |
|---|---|
| Sim_Premium_prev | Simulated premium using previous-year expected loss |
| Sim_Premium_all_prev | Simulated premium using cumulative historical expected loss |
| Promotion Scenario | Scenario preserving policies where premium = 0 |

---

## Vehicle & Policy Information

| Field | Description |
|---|---|
| TYPE_VEHICLE | Vehicle category used for pricing and risk segmentation |
| VEHICLE_USAGE | Vehicle usage classification (private, commercial, transport, etc.) |
| INSURED_VALUE | Declared insured value of the vehicle |
