```
-- Number of crimes committed in Baltimore each year?
select
	extract(year from crimedate) as year,
	count(1) as total_number
from 
	baltimore_crime_data
group by 1
order by 2 desc

-- Where are the most crimes committed?
select
	distinct district,
	count(1) as total_number
from 
	baltimore_crime_data
group by 1
order by 2 desc

-- What are the most crimes committed?
select
	description as crime_committed,
	count(1) as total_number
from 
	baltimore_crime_data
group by 1
order by 2 desc

-- Were the crimes mostly indoor or outdoor?
select
	case 
		when inside_outside = 'I' then 'Indoor'
		else 'Outdoor'
	end as inside_outside,
	count(1) as total_number
from 
	baltimore_crime_data
where inside_outside != 'Unknown'
group by 1
order by 2 desc

-- What type of weapons were used to committed these crimes?
-- How many were used inside/outside
select
	weapon,
	case 
		when inside_outside = 'I' then 'Indoor'
		else 'Outdoor'
	end as inside_outside,
	count(1) as total_number
from 
	baltimore_crime_data
group by 1, 2
order by 3 desc

-- What time of the were crimes most committed?
select
	crimetime,
	count(1) as total_number
from 
	baltimore_crime_data
group by 1
order by 2 desc
limit 5
```