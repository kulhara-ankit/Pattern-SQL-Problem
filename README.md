P(R) represents a pattern drawn by Julia in R rows. The following pattern represents P(5):

* * * * * 
* * * * 
* * * 
* * 
*
Write a query to print the pattern P(20).


Solution:


with RECURSIVE number as (
    select 20 as n
    union all 
    select n-1 from number where n>1
)
select repeat("* ", n) as pattern
from number;
