
Steps 1

CREATE TABLE grainn_data(
year int,
month int,
scheme VARCHAR(50),
state_code int,
state_name VARCHAR(50),
rice_allocated_qty_mt float,
wheat_allocated_qty_mt float,
rice_distributed_qty_mt float,
wheat_distributed_qty_mt float,
coarsegrain_allocated_qty_mt float,
coarsegrain_distributed_qty_mt float

);

step 2

copy temp_data(year,
month,
scheme,
state_code,
state_name,
rice_allocated_qty_mt,
wheat_allocated_qty_mt,
rice_distributed_qty_mt,
wheat_distributed_qty_mt,
coarsegrain_allocated_qty_mt,
coarsegrain_distributed_qty_mt)
from 'E:\Desktop\grain_data.csv'
DELIMITER ‘,’
CSV HEADER;

task 1 
 select rice_distributed_qty_mt,wheat_distributed_qty_mt,
coarsegrain_distributed_qty_mt from grain_data where
 state_name = 'BIHAR' and month >=8;

task 2
select rice_distributed_qty_mt,wheat_distributed_qty_mt,
coarsegrain_distributed_qty_mt from grain_data where
 state_name = 'MAHARASHTRA' and month >=8;

task 3
select rice_allocated_qty_mt,rice_distributed_qty_mt from
 grain_data where month =9;

task 4

temp_data=# select wheat_allocated_qty_mt,wheat_distributed_qty_mt,
state_name 
from grain_data where month >=7;
