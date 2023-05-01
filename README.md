# Hotel Management

Hotel Management Data Analysis 

1) Dataset
2) SQL Querys:
  
      with consolidado as (
        select * from dbo.[2018]
        union
        select * from dbo.[2019]
        union
        select * from dbo.[2020])
 

       select
        arrival_date_year,
        hotel,
        round(sum((stays_in_week_nights+stays_in_weekend_nights)*adr), 2) as receita
        from consolidado
        group by arrival_date_year, hotel


        select * from consolidado
        left join dbo.market_segment
        on consolidado.market_segment = market_segment.market_segment
        left join dbo.meal_cost
        on meal_cost.meal = consolidado.meal
        
      
3) PBI Link: https://app.powerbi.com/view?r=eyJrIjoiODgzZmZlYmYtMjVlYS00ZGZhLTliN2YtMTQ3MWI4MWU1MWMxIiwidCI6IjQzZTJhOTE4LThiMDktNDg0Ni1iODljLTE1YWY0OWRjMGJlNCJ9
