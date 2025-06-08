# Stage Probability Predictor
- Uses Regression Algorithm

# Feature Selection
| Column Name        | Use?         | Reason                                                                                   |
| ------------------ | ------------ | ---------------------------------------------------------------------------------------- |
| `Amount`           | ✅            | Strong indicator of deal size — important for predicting probability.                    |
| `Close_Date`       | ✅            | Use to derive `days_to_close` or temporal trend; convert to a numeric feature.           |
| `Sales_Person`     | ✅            | Useful categorical — model can learn which reps win more often.                          |
| `Company_Industry` | ✅            | Some industries may have better win rates — useful categorical.                          |
| `Contact_Title`    | ✅            | Position of contact person might influence success. Use with caution (limit categories). |
| `Created_Date`     | ✅            | Can derive `deal_age` or seasonality effects.                                            |
| `Type`             | ✅            | `New Business`, `Renewal`, etc. — strong categorical indicator.                          |
| `Lead_Source`      | ✅            | Source like `RFP`, `Conference`, `Web` — meaningful categorical.                         |
| `State`            | ✅            | Geographic patterns could influence win rates.                                           |
| `Zip_Code`         | ✅ (optional) | Use only if you can extract something useful like region clusters.                       |
| `Payment_Terms`    | ✅ (optional) | Could be useful if terms are known to correlate with win rate. Consider label encoding.  |
| `Stage`                                              | Used only for splitting data, not for training     |
| `Description`, `Emails`, `Phone`, `Opportunity_Name` | Drop or do NLP separately                          |