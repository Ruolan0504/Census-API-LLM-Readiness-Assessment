# Census API Data Readiness Assessment for LLM Applications

https://ruolan0504.github.io/Census-API-LLM-Readiness-Assessment/US-Population-Estimate-Analysis-and-Visualization.html

## Project Overview
This project conducts a system-level evaluation of whether major U.S. Census Bureau datasets accessed through the Census API are suitable for downstream LLM-driven applications.  
The focus is not on building a full system, but on assessing data accessibility, structural consistency, data quality, and practical usability.

## Datasets Reviewed
- American Community Survey (ACS)
- Economic Census
- Population Estimates
- SAHIE
- PSEO

## What Was Done
- Evaluated accessibility and usability of Census datasets via the Census API  
- Cleaned and standardized heterogeneous datasets with inconsistent formats and encodings  
- Identified major data quality issues such as missing state coverage and inconsistent geographic granularity  
- Analyzed how incomplete data may affect downstream analytics and LLM reliability  
- Assessed the feasibility of text-to-API workflows and proposed intermediary translation layers between user queries and Census codes  
- Summarized design requirements for improving Census data readiness for AI-driven applications  

## Demo: Population Estimates Analysis
A downstream analytical demo was developed to validate practical usability of Census API outputs:
- Data cleaning
- Visualization
- Trend analysis

## Tools
R, Census API, Data Cleaning, Visualization
