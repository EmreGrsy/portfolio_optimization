# Risk Parity vs Global Minimum Variance Portfolio

This repository showcases two portfolio construction methods.


## Risk Parity (Inverse Volatility Allocation)
Each day, the top 10 assets with the highest trailing 1-year (252-day) return are selected. Portfolio weights are assigned **proportional to the inverse of their 1-year volatility**, then normalized to sum to 1.

This approach:
- Requires no correlation estimates
- Avoids matrix inversion
- Is simple and robust

## Global Minimum Variance Portfolio
Finds the asset weights that minimize overall portfolio variance using the full covariance matrix. This requires solving a **quadratic optimization problem**

This approach:
- Is theoretically optimal in terms of volatility
- Requires matrix inversion or numerical solvers
- Can be sensitive to estimation noise

---

## ⚖️ Comparison

| Feature                 | Risk Parity                     | GMVP                               |
|------------------------|----------------------------------|------------------------------------|
| Uses correlations?     | ❌ No                            | ✅ Yes                              |
| Requires optimization? | ❌ No                            | ✅ Yes (quadratic programming)      |
| Robust to noise?       | ✅ High                          | ❌ Sensitive                       |
| Output weights         | Intuitive, positive              | Can be extreme or negative         |


---

This project demonstrates both approaches in practice using simulated data.
