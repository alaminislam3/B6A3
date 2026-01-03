-- Query 1: Join  

select B.booking_id, U.name as customer_name, V.name as vehicle_name, B.start_date, B.end_date, B.status from Booking as B inner join 
Users as U on B.user_id = U.user_id inner join Vehicles as V on B.vehicle_id = V.vehicle_id 