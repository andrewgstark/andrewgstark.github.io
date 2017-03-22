---
layout: post
title:  "Analysing Public Data About City of San Jose Salaries and Pensions"
date:   2017-01-25 10:35:39 -0800
categories: jekyll update
---

**To view or download  the code**, <a href="http://nbviewer.jupyter.org/github/andrewgstark/DSI-SF-4-andrewgstark/blob/master/capstone/Finding_Pension_Spikers_Through_Data_Science.ipynb" target="_blank">click here</a>

* TOC
{:toc}

# Problem Statement

Public sector employees in California are eligible for pensions, based on their final earnings and years of service. These pensions are paid for the retiree's lifetime, and can optionally be paid to the retiree's beneficiary for their lifetime. 
Public pension plans have a huge unfunded liability (the promises made to current and future retirees exceeds the pension funds ability to pay for those promises). There are several reasons for this unfunded liability including:

1. Legislation in 1999 (SB 400) that increased benefits and reduced the retirement age

2. Investment returns less than forecast (dot com bust, mortgage crisis, low interest rate)

3. A growing pool of retired employees, and corresponding growing pension obligations

4. Pension spiking, i.e., inappropriate enhancement of the pension benefit, usually when the employer pays an excessive increase of compensation at the end of an employee's career.


![California public pension unfunded liabilities]({{ site.url }}/assets/pension-liabilities-fig1.png)

Figure source:  <a href="http://www.ppic.org/main/publication_show.asp?i=1157" target="_blank">Public Policy Institute of California</a>

This underfunding is causing the pension costs to Cities, Counties and other public sector employers to increase rapidly. 

Pension managers have no control over 1 to 3. But some public pension funds do try to detect pension spiking via audits and getting tips.  

# Business Need and Stakeholders

Pension funds protect themselves again pension spiking by conducting employer audits, reviewing compensation of individual retirees and issuing clear guidelines about what constitutes creditable pay. 

For example, the CA State Teachers Retirement System (CalSTRS) has the following guidelines:

** Not creditable: cash in lieu of fringe benefits, any reimbursable business expense, e.g., housing or auto expenses

** Creditable: pay linked to special certificates, credentials for advanced degrees

** Assignments in addition to regular full-time employment: coaching, summer school, extracurricular activities, etc. earn credit towards a separate benefit (the Defined Benefit Supplement Program (DBS)

** Compensation paid for a specified time period or is a late-career increase inconsistent with the employee's salary history is credited to DBS and not the standard pension.

# Datasets 

Governments around the world are release more data as part of "open data" initiatives, to improve efficiency and increase transparency. Compensation data about public sector employees is considered public information, and is available from several different source:

** <a href="http://publicpay.ca.gov/" target="_blank">Government Compensation in California, State Controller's Office</a>

** <a href="http://transparentcalifornia.com" target="_blank">Transparent California</a>

** Open data portals at government websites: <a href="http://www.ppic.org/main/publication_show.asp?i=1157" target="_blank">City of San Francisco</a>, <a href="http://www.ppic.org/main/publication_show.asp?i=1157" target="_blank">City of San Jose</a>, <a href="http://www.ppic.org/main/publication_show.asp?i=1157" target="_blank">City of Los Angeles</a>

# Exploratory Data Analysis and Visualizations

## When did Pension Recipients Retire?

Spike in people retiring during the 2009-2011 economic downturn, possible due to early retirement packages and employee attrition,

![Year of retiral for recipients of Federated pension]({{ site.url }}/assets/retire_years_federated.png)

There was a larger spike in police and fire retirements after 2010, possibly due to adopting the "3% at 50" retirement plan, first negotiated by the CHP. 

![Year of retiral for the police and fire pension fund]({{ site.url }}/assets/retire_years_policefire.png)

## Correlation Between Pay and Service Years on Pension Payment

For the two pension plans that service City of San Jose employees, the Police and Fire Fund has the more generous pension payment. The trend line for the Police and Fire fund has a steeper slope to reflect this. 

![Correlation between base pay and pension payment]({{ site.url }}/assets/base_vs_pensionpay.png)

![Correlation between length of service and pension payment]({{ site.url }}/assets/service_vs_pensionpay.png)

When considering the current pool of employees, the length of service for police and fire exceeds that of other employees. This is likely due to people dedicating their entire career to the force. This may be since skill sets for Police and Fire don't easily transfer to the private sector. Also, Police and Fire may be more attractive careers considering the high pay and good benefits.

However, the number of years of service for Police and Fire has been steadily decreasing. 

![Years of service when retiring]({{ site.url }}/assets/service_vs_yearofretire.png)

