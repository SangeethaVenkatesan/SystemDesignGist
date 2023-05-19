Time Series Database :Goku

Goku - PinInterest's inhouse built time series database 

Why do we need this ?

Big companies run analytics and they want to measure everything and data at all points .Basically ,the goal is to measure actions at every instances.

Initially ,they used open tsdb as their main time series database to hold all the time series data they have .They were ingesting a million points every second but open tsdb had lot of garbage collection issues as it was based on Hbase .Also ,there were frequent crashes .

Every  time series data will have two parts ,first is the metric that we are tracking such as cpu of every machine 
which may look like tc.proc.stat.cpu.total and second may be tag such as (host =ec2 and service = auth service).This is our key
metric +tag .

<img width="916" alt="Screenshot 2023-05-17 at 11 29 50 PM" src="https://github.com/SangeethaVenkatesan/SystemDesignGist/assets/23241962/e5e01705-3aba-465b-9279-dd17b30a5e1a">
