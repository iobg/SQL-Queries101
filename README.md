# SSl-Queries101
1.SELECT Customer.FirstName ||' '|| Customer.LastName, Customer.CustomerId, Customer.Country FROM Customer
WHERE Customer.Country <> "USA"

2.SELECT Customer.FirstName ||' '|| Customer.LastName, Customer.CustomerId, Customer.Country FROM Customer
WHERE Customer.Country = "Brazil"

3.SELECT Customer.FirstName ||' '|| Customer.LastName AS Name, Invoice.InvoiceId,Invoice.BillingCountry FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
WHERE Customer.Country = "Brazil"

4.SELECT * FROM Employee
JOIN Customer ON Customer.SalesRepId = Employee.EmployeeId

5.SELECT Invoice.BillingCountry FROM Invoice
ORDER BY Invoice.BillingCountry

6.SELECT * FROM Invoice
WHERE Invoice.BillingCountry = "Brazil"

7. SELECT Employee.FirstName ||' '|| Employee.LastName as Name, Invoice.*
FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId

8. Employee.FirstName ||' '|| Employee.LastName as Name, SUM(Invoice.Total) as Total, Customer.FirstName,Invoice.BillingCountry
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
