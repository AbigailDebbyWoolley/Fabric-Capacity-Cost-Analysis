# Microsoft Fabric Cost Calculation for Brock Group (F64 SKU) - North Central US

## Overview
This notebook calculates the estimated cost of running **Microsoft Fabric** for Brock Group, which operates on the **F64 SKU** in the **North Central US** region. The cost is based on **Capacity Unit (CU) seconds**, which is converted to **hours** for accurate billing.

## Cost Calculation Methodology

### Key Parameters:
- **SKU Tier**: **F64**
- **Region**: **North Central US**
- **Pay-as-you-go Cost per Hour**: **$11.52/hour**
- **Reserved Capacity Cost per Hour**: **$6.853/hour**
- **CU Duration Column**: **"CU s" (Capacity Unit seconds)**
- **Conversion to Hours**: **CU s ÷ 3600**  

### Formulas:
For each row in the dataset:

#### **Convert CU Seconds to Hours**
\[
\text{CU Hours} = \frac{\text{CU s}}{3600}
\]

#### **Compute Costs**
\[
\text{Cost (Pay-as-you-go)} = \frac{\text{CU s}}{3600} \times 11.52
\]

\[
\text{Cost (Reserved Capacity)} = \frac{\text{CU s}}{3600} \times 6.853
\]

## Example Calculation:
If a given row has **CU s = 7200**, the calculations would be:

\[
\text{CU Hours} = \frac{7200}{3600} = 2 \text{ hours}
\]

\[
\text{Cost (Pay-as-you-go)} = 2 \times 11.52 = \mathbf{\$23.04}
\]

\[
\text{Cost (Reserved Capacity)} = 2 \times 6.853 = \mathbf{\$13.71}
\]

## Additional Considerations:
- The **cost is calculated per row**, meaning each execution has an independent cost.
- **Reserved capacity offers a significant discount (~40.2%)** compared to pay-as-you-go.
- **Optimizing CU usage** can lead to cost savings by reducing execution time or leveraging auto-scaling.

## References:
- [Microsoft Fabric Pricing - North Central US](https://azure.microsoft.com/en-us/pricing/details/microsoft-fabric/)
- [Fabric Capacity Units and Billing](https://learn.microsoft.com/en-us/fabric/capacity/capacity-units)

## Next Steps:
1. **Apply this formula to each row** in the dataset to compute costs dynamically.
2. **Analyze cost trends** to determine if reserved capacity is more cost-effective.
3. **Implement optimizations** to minimize unnecessary CU usage.
