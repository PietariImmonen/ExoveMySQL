# ExoveMySQL
The code for the pre-assignment for the assignment 2B

THE CODE IS THE FOLLOWING

------------

SELECT 
   --concatting the names as name and group-concatting the phone numbers to numbers for showing many phonenumbers in the same row--
   --Using COALESCE for changing null to N/A--
  CONCAT(p.first_name, ' ', p.last_name) AS name,
  COALESCE(GROUP_CONCAT(i.number), 'N/A') AS numbers
FROM 
-- Left joining people and phone with users to display also the one with no phone number--
  people p LEFT JOIN phones i ON p.id = i.user_id
GROUP BY
-- groupping the people with id, first_name and last_name--
  p.id, p.first_name, p.last_name
ORDER BY
--Lastly ordering the result by their last name--
  p.last_name


