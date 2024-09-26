# SQL-PROJECT-ON-Agricultural-Production-Data-Analysis

## Acknowledgements

 Thanks to the **University of California** for providing the agricultural data.🌾
 
 Special thanks to coffee for keeping us going through late-night coding sessions. ☕

 ## Project Overview
Welcome to the **Agricultural Production Data Analysis** project, where we turn rows of numbers into insights—because analyzing crop data is the
closest thing to magic farming. 🧙‍♂️

This project gathers data on essential commodities such as cheese, honey, milk, coffee, eggs, and yogurt. It’s perfect for those 
who are passionate about agriculture... or just really, really love cheese. 🧀

Our goal? To create SQL tables so elegant that even your database will want to frame them! 📊

## Technologies Used
This project is powered by a bunch of tools that have nothing to do with actual farming but make analyzing data a whole lot easier:

**SQL**: MICROSOFT SQL SERVER Because Excel just isn’t enough for us data hoarders. 📈

## Usage

So, you’ve made it this far. Congrats! Now let’s get serious (just kidding, still fun). Here’s how you can use this project:

1. **Create the tables**: Fire up your SQL Server and run those table creation scripts like a boss. 💼
   
3. **Insert data**: You can now insert csv files.📚
   
5. **Analyze**: Run some queries, get insights, and maybe impress your boss  with fancy reports. 📊🐱

 ✨ Pro tip: Don’t panic if you get stuck, that’s what they are for. Just make sure you haven’t copied and pasted the wrong script from some random forum post. 😅

## Code
Here lies the code... treat it with care 🤖

CREATE TABLE cheese_production (


Year INT,


Period NVARCHAR(50),


Geo_Level NVARCHAR(50),


State_ANSI INT,


Commodity_ID INT,


Domain NVARCHAR(50),


Value INT
);

CREATE TABLE honey_production (

Year INT,


Geo_Level NVARCHAR(50),


State_ANSI INT,


Commodity_ID INT,


Value INT
);

CREATE TABLE milk_production (

Year INT,


Period NVARCHAR(50),


Geo_Level NVARCHAR(50),


State_ANSI INT,


Commodity_ID INT,


Domain NVARCHAR(50),


Value INT
);

CREATE TABLE coffee_production (

Year INT,


Period NVARCHAR(50),


Geo_Level NVARCHAR(50),


State_ANSI INT,


Commodity_ID INT,


Value INT
);

CREATE TABLE egg_production (

Year INT,


Period NVARCHAR(50),


Geo_Level NVARCHAR(50),


State_ANSI INT,


Commodity_ID INT,


Value INT
);

CREATE TABLE state_lookup (

State NVARCHAR(50),


State_ANSI INT
);

CREATE TABLE yogurt_production (

Year INT,


Period NVARCHAR(50),


Geo_Level NVARCHAR(50),


State_ANSI INT,


Commodity_ID INT,


Domain NVARCHAR(50),


Value INT
);


## The SQL Interrogation Room: Q&A”

**Question1: Find the total milk production for the year 2023.**
Answer:
SELECT SUM(Value) FROM milk_production WHERE Year = 2023;

91812000000


**Question2: Show coffee production data for the year 2015. What is the total value?**

Answer: 6600000


**Question3: Find the average honey production for the year 2022.**

Answer: SELECT AVG(Value) FROM honey_production WHERE Year = 2022;

3133275


**Question4: Get the state names with their corresponding ANSI codes from the state_lookup table. What number is Iowa?**

Answer: SELECT * FROM state_lookup;

19

**Question5:Find the highest yogurt production value for the year 2022.**

Answer: 793256000


**Question6: Find states where both honey and milk were produced in 2022.Did State_ANSI "35" produce both honey and milk in 2022?**

Answer: No


**Question7:Find the total yogurt production for states that also produced cheese in 2022.**

Answer: SELECT SUM(y.Value)

FROM yogurt_production y

WHERE y.Year = 2022 AND y.State_ANSI IN (

    SELECT DISTINCT c.State_ANSI FROM cheese_production c WHERE c.Year = 2022
);


 ## FINAL PROJECT QUESTIONS AND ANSWERS

**Question1:Can you find out the total milk production for 2023? Your manager wants this information for the yearly report.
What is the total milk production for 2023?**

Answers: SELECT SUM(Value) FROM milk_production WHERE Year = 2023;

We got 91812000000


**Question2:Which states had cheese production greater than 100 million in April 2023? The Cheese Department wants to focus their marketing efforts there. 
How many states are there?**

Answers: SELECT State_ANSI FROM cheese_production WHERE Year = 2023 AND Period = 'APR' AND Value > 100000000;

So,2


**Question3:Your manager wants to know how coffee production has changed over the years. What is the total value of coffee production for 2011?**

Answers: SELECT Year, SUM(Value) FROM coffee_production GROUP BY Year;


Thus,7600000


**Question4:The State Relations team wants a list of all states names with their corresponding ANSI codes. Can you generate that list?What is the State_ANSI code for 
Florida?**


Answers: SELECT * FROM state_lookup;


 Therefore,12


**Question5:For a cross-commodity report, can you list all states with their cheese production values, even if they didn't produce any cheese in April of 2023?
What is the total for NEW JERSEY.**

Answer: SELECT s.State, c.Value

FROM state_lookup s

LEFT JOIN cheese_production c ON s.State_ANSI = c.State_ANSI AND c.Year = 2023 AND c.Period = 'APR';


 Hence,4889000


**Question6: Can you find the total yogurt production for states in the year 2022 which also have cheese production data from 2023? 
This will help the Dairy Division in their planning.**

Answer: 1171095000


**Question7: List all states from state_lookup that are missing from milk_production in 2023.How many states are there?**

Answer: 26


**Question8: Find the average coffee production for all years where the honey production exceeded 1 million.**

Answer: 6426666


**Question9: List all states with their cheese production values, including states that didn't produce any cheese in April 2023.
Did Delaware produce any cheese in April 2023?**

Answer: No

## Contributing Encouragement

🙌 **Contributing**: Feel free to contribute, but beware—you may fall in love with my messy code! 💻


## License with a Twist
📜 **License**: You can use this project for whatever you want... unless it’s to hack a farm. 🐄















