Time Series Database :Goku

Goku - PinInterest's inhoue built time series database 

Why do we need this ?

Big companies run analytics and they want to measure everything and data at all points .Basically ,the goal is to measure actions at every instances.

Initially ,they used open tsdb as their main time series database to hold all the time series data they have .They were ingesting a million points every second but open tsdb had lot of garbage collection issues as it was based on Hbase .Also ,there were frequent crashes .

