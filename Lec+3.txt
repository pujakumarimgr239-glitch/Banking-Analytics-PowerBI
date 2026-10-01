
SELECT
    t.TransactionID,
    t.AccountID AS Transaction_AccountID,
    t.TransactionDate,
    t.Type AS TransactionType,
    t.Amount,
    t.Description,
    t.Currency,
    a.AccountID AS Account_AccountID,
    a.CustomerID AS Account_CustomerID,
    a.Type AS AccountType,
    a.OpenDate,
    a.Balance,
    c.CustomerID,
    c.Name,
    c.Gender,
    c.DateOfBirth,
    c.Address,
    c.Email,
    c.Phone
INTO CombinedBankingDataset
FROM
    Transactions t
    Left JOIN Accounts a ON t.AccountID = a.AccountID
    Left JOIN Customers c ON a.CustomerID = c.CustomerID


	select * from CombinedBankingDataset


