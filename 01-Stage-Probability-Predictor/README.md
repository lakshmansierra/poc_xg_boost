# Stage Probability Predictor
- Uses Regression Algorithm

# NOTE
- Closed Lost & Closed Won in train (100 & 0 are unaltered)
- remaining in test

# Feature Selection
| Column Name        | Use?         | Reason                                                                                   |
| ------------------ | ------------ | ---------------------------------------------------------------------------------------- |
| `Sales Order`      | ☑️            | Unique Identifier (not for training)                                                     |
| `Stage`            | ☑️            | Used only for splitting data (not for training)                                          |
| `Amount`           | ✅            | Strong indicator of deal size — important for predicting probability.                    |
| `Close_Date`       | ✅            | Use to derive `days_to_close` or temporal trend; convert to a numeric feature.           |
| `Probability`      | ✅            | Target variable                                                                          |
| `Sales_Person`     | ✅            | Useful categorical — model can learn which reps win more often.                          |
| `Company_Industry` | ✅            | Some industries may have better win rates — useful categorical.                          |
| `Contact_Title`    | ✅            | Position of contact person might influence success. Use with caution (limit categories)  |
| `Created_Date`     | ✅            | Can derive `deal_age` or seasonality effects.                                            |
| `Type`             | ✅            | `New Business`, `Renewal`, etc. — strong categorical indicator.                          |
| `Lead_Source`      | ✅            | Source like `RFP`, `Conference`, `Web` — meaningful categorical.                         |
| `State`            | ✅            | Geographic patterns could influence win rates.                                           |
| `Description`, `Emails`, `Phone`, `Opportunity_Name` | Drop or do NLP separately                                               |
| `Zip_Code`      | Use only if you can extract something useful like region clusters.
| `Payment_Terms` | Could be useful if terms are known to correlate with win rate. Consider label encoding. 

# Feature Engineering
- `days_to_close` = `Close_Date` - `Created_Date` (in days)
- Encode `Sales_Person`, `Company_Industry`, `Contact_Title`, `Type`, `Lead_Source`, `State`
- Drop `Sales Order`, `Stage`, `Close_Date`, `Created_Date`