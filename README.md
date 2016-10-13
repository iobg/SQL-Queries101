# SSl-Queries101
1. SELECT Customer.FirstName ||' '|| Customer.LastName, Customer.CustomerId, Customer.Country FROM Customer
WHERE Customer.Country <> "USA"

2. SELECT Customer.FirstName ||' '|| Customer.LastName, Customer.CustomerId, Customer.Country FROM Customer
WHERE Customer.Country = "Brazil"

3. SELECT Customer.FirstName ||' '|| Customer.LastName AS Name, Invoice.InvoiceId,Invoice.BillingCountry FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
WHERE Customer.Country = "Brazil"

4. SELECT * FROM Employee
JOIN Customer ON Customer.SalesRepId = Employee.EmployeeId

5. SELECT Invoice.BillingCountry FROM Invoice
ORDER BY Invoice.BillingCountry

6. SELECT * FROM Invoice
WHERE Invoice.BillingCountry = "Brazil"

7. SELECT Employee.FirstName ||' '|| Employee.LastName as Name, Invoice.*
FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId

8. SELECT Employee.FirstName ||' '|| Employee.LastName as Name, SUM(Invoice.Total) as Total, Customer.FirstName,Invoice.BillingCountry
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId

9.	a. SELECT Invoice.*, SUM(Invoice.Total) AS 'Year Total' FROM Invoice
	WHERE InvoiceDate > '2009-01-01 00:00:00' AND InvoiceDate < '2010-01-01 00:00:00'
	b. SELECT Invoice.*, SUM(Invoice.Total) AS 'Year Total' FROM Invoice
	WHERE InvoiceDate > '2010-01-01 00:00:00' AND InvoiceDate < '2011-01-01 00:00:00'
	c. SELECT Invoice.*, SUM(Invoice.Total) AS 'Year Total' FROM Invoice
	WHERE InvoiceDate > '2011-01-01 00:00:00' AND InvoiceDate < '2012-01-01 00:00:00'

10. SELECT Invoice.*, COUNT(InvoiceLine.InvoiceId)  FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
WHERE Invoice.InvoiceId = 37


11. SELECT Invoice.*, COUNT(InvoiceLine.InvoiceId)  FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
GROUP BY Invoice.InvoiceId

12. SELECT InvoiceLine.*, Track.Name FROM InvoiceLine
JOIN Track ON InvoiceLine.TrackId= Track.TrackId

13. SELECT InvoiceLine.*, Track.Name, Track.Composer FROM InvoiceLine
JOIN Track ON InvoiceLine.TrackId= Track.TrackId

14. SELECT BillingCountry, COUNT(BillingCountry) AS 'InvoicesPerCountry' FROM Invoice
GROUP BY BillingCountry

15. SELECT PlayList.Name, COUNT(Track.TrackId) FROM Playlist
JOIN PlaylistTrack ON Playlist.PlaylistId = PlayListTrack.PlayListId
JOIN Track ON PlayListTrack.TrackId = Track.TrackId
GROUP BY PlayList.Name

16. SELECT Track.Name, Album.Title AS 'Album Name', MediaType.Name AS 'Media Type', Genre.Name AS 'Genre' FROM Track
JOIN Album ON Track.AlbumId = Album.AlbumId
JOIN MediaType ON Track.MediaTypeId = MediaType.MediaTypeId
JOIN Genre ON Track.GenreId = Genre.GenreId

17. SELECT Invoice.*, COUNT(InvoiceLine.InvoiceId) AS 'Invoice Line'  FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
GROUP BY Invoice.InvoiceId

18. SELECT  Employee.FirstName ||' '|| Employee.LastName AS 'Name',SUM(Invoice.total) AS 'Total Sales' FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
GROUP BY Name

19. SELECT  Employee.FirstName ||' '|| Employee.LastName AS 'Name',SUM(Invoice.total) AS 'Total Sales' FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
WHERE InvoiceDate > '2009-01-01 00:00:00' AND InvoiceDate < '2010-01-01 00:00:00'
GROUP BY Name
Answer:Steve Johnson



20. SELECT  Employee.FirstName ||' '|| Employee.LastName AS 'Name',SUM(Invoice.total) AS 'Total Sales' FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
WHERE InvoiceDate > '2010-01-01 00:00:00' AND InvoiceDate < '2011-01-01 00:00:00'
GROUP BY Name
Answer:Jane Peacock


21. SELECT  Employee.FirstName ||' '|| Employee.LastName AS 'Name',SUM(Invoice.total) AS 'Total Sales' FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
GROUP BY Name
Answer:Jane Peacock



22. SELECT  Employee.FirstName ||' '|| Employee.LastName AS 'Name',COUNT(Customer.CustomerId) AS 'Customers' FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
GROUP BY Name

23. SELECT  Invoice.BillingCountry,SUM(Invoice.Total) AS 'Sales' FROM Invoice
JOIN Customer ON Invoice.CustomerId = Customer.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
GROUP BY Invoice.BillingCountry
Answer:USA



24. SELECT Track.Name,Count(Track.TrackId) AS 'TracksSold' FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
WHERE InvoiceDate > '2013-01-01 00:00:00' AND InvoiceDate < '2014-01-01 00:00:00'
GROUP BY Track.Name
ORDER BY TracksSold DESC LIMIT 1

25. SELECT Track.Name,Count(Track.TrackId) AS 'TracksSold' FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
GROUP BY Track.Name
ORDER BY TracksSold DESC LIMIT 5

26. SELECT Artist.Name,Count(Artist.ArtistId) AS 'Sales' FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
JOIN Album ON Track.AlbumId = Album.AlbumId
JOIN Artist ON Album.ArtistId = Artist.ArtistId
GROUP BY Artist.Name
ORDER BY Sales DESC LIMIT 3

27. SELECT MediaType.Name,Count(MediaType.MediaTypeId) AS 'Sales' FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
JOIN MediaType ON Track.MediaTypeId = MediaType.MediaTypeId
GROUP BY MediaType.Name
ORDER BY Sales DESC LIMIT 1



