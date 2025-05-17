# Codebook

## Identifiers & Target

| Variable         | Description                                                       |
|------------------|-------------------------------------------------------------------|
| `fyear`          | Fiscal year                                                       |
| `gvkey`          | Global Company Key (unique firm ID from Compustat)               |
| `misstate`       | Fraud indicator (1 = fraud, 0 = non-fraud)                        |

---

## Raw Accounting Variables

| Variable   | Description                                          |
|------------|------------------------------------------------------|
| `act`      | Current Assets, Total                                |
| `ap`       | Account Payable, Trade                               |
| `at`       | Assets, Total                                        |
| `ceq`      | Common/Ordinary Equity, Total                        |
| `che`      | Cash and Short-Term Investments                      |
| `cogs`     | Cost of Goods Sold                                   |
| `csho`     | Common Shares Outstanding                            |
| `dlc`      | Debt in Current Liabilities, Total                   |
| `dltis`    | Long-Term Debt Issuance                              |
| `dltt`     | Long-Term Debt, Total                                |
| `dp`       | Depreciation and Amortization                        |
| `ib`       | Income Before Extraordinary Items                    |
| `invt`     | Inventories, Total                                   |
| `ivao`     | Investment and Advances, Other                       |
| `ivst`     | Short-Term Investments, Total                        |
| `lct`      | Current Liabilities, Total                           |
| `lt`       | Liabilities, Total                                   |
| `ni`       | Net Income (Loss)                                    |
| `ppegt`    | Property, Plant and Equipment, Total                 |
| `pstk`     | Preferred/Preference Stock (Capital), Total          |
| `re`       | Retained Earnings                                    |
| `rect`     | Receivables, Total                                   |
| `sale`     | Sales/Turnover (Net)                                 |
| `sstk`     | Sale of Common and Preferred Stock                   |
| `txp`      | Income Taxes Payable                                 |
| `txt`      | Income Taxes, Total                                  |
| `xint`     | Interest and Related Expense, Total                  |
| `prcc_f`   | Price Close, Annual, Fiscal                          |

---

## Financial Ratio Features

| Variable        | Description                                                |
|------------------|------------------------------------------------------------|
| `dch_wc`         | Working Capital Accruals                                   |
| `ch_rsst`        | RSST Accruals                                              |
| `dch_rec`        | Change in Receivables                                      |
| `dch_inv`        | Change in Inventory                                        |
| `soft_assets`    | Percentage of Soft Assets                                  |
| `ch_cs`          | Change in Cash Sales                                       |
| `ch_cm`          | Change in Cash Margin                                      |
| `ch_roa`         | Change in Return on Assets                                 |
| `issue`          | Actual Issuance                                            |
| `bm`             | Book-to-Market                                             |
| `dpi`            | Depreciation Index                                         |
| `reoa`           | Retained Earnings over Total Assets                        |
| `ebit`           | EBIT over Total Assets                                     |
| `ch_fcf`         | Change in Free Cash Flows                                  |

---

## Derived Missingness Indicators

| Variable          | Description                                       |
|-------------------|---------------------------------------------------|
| `ch_cs_missing`   | 1 if `ch_cs` was missing before imputation, else 0 |
| `ch_cm_missing`   | 1 if `ch_cm` was missing before imputation, else 0 |
