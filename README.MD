-- Query 1: Join  

select B.booking_id, U.name as customer_name, V.name as vehicle_name, B.start_date, B.end_date, B.status from Booking as B inner join 
Users as U on B.user_id = U.user_id inner join Vehicles as V on B.vehicle_id = V.vehicle_id 

-- query 2: Exists

select * from Vehicles where status = 'available' OR status = 'maintenance'
-- or 
select * from Vehicles where status IN ('available','maintenance')

-- query 3 : WHERE 

select * from Vehicles where type ='car' and status = 'available'

-- query Group by and having 

SELECT 
  V.name AS vehicle_name,
  COUNT(B.booking_id) AS total_bookings
FROM Booking AS B
INNER JOIN Vehicles AS V
ON B.vehicle_id = V.vehicle_id
GROUP BY V.name
HAVING COUNT(B.booking_id) > 2;
