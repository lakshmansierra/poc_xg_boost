# Stage Probability Predictor
- Uses Regression Algorithm

# Feature Selection
| Column                                               | Notes                                              |
| ---------------------------------------------------- | -------------------------------------------------- |
| `Amount`                                             | Keep as numeric                                    |
| `Sales_Person`                                       | Encode (Label Encoding or One-Hot)                 |
| `Company_Industry`                                   | Encode                                             |
| `State`                                              | Encode                                             |
| `Lead_Source`                                        | Encode                                             |
| `Type`                                               | Encode                                             |
| `Created_Date`, `Close_Date`                         | Derive `days_to_close`, `days_since_created`, etc. |
| `Stage`                                              | Used only for splitting data, not for training     |
| `Description`, `Emails`, `Phone`, `Opportunity_Name` | Drop or do NLP separately                          |

