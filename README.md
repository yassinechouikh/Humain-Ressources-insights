# Humain-Ressources-insights

## Problem Statement

This dashboard helps the AtliQ technologie compagny understanding its humain ressoures better.The study focus only on three months from Avril to Juin in 2022, during this period we will try to discover differents aspects and insights throught diffrents ratings, by finding thoses they prefere presence, work from home and sick leave identifiying all aspects and insights can give permission to the society for enhancing and customer its services.
avoiding delay and increasing the emplyoyees eficacity are the primordial goals for CEOs, satisfing and customizing clients need. 
Knowing conforte zone and conditions work for each employe are the key success to make each element leading his work to the top professional level he can.


### Steps followed 
ATTENDANCE KEY	(column_Value)
P	Present 
PL	Paid Leave 
SL	Sick Leave 
HPL	Half day PL 
HSL	Half day SL
WFH	Work from home 
FFL	Floting festival leave 
HFFL	Half Day Floting festival leave 
BL 	Birthday Leave 
LWP	Leave without pay
HLWP	Half day Leave without pay
BRL 	Bereavement Leave
HBRL 	Half Bereavement Leave
HWFH	Half Work From Home
WO	Weekly Off
HO	Holiday Off
ML	Menstrual Leave
HML	Half Day ML


- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column employees Name", "column Date" & "column Value" options.
- Step 3 : It was observed that in none of the columns errors & empty values were present except column named "Arrival Delay".
- Step 4 : Fixing the format type of each column.
- Step 5 : "DateMonth" column was added to the table, notifiying the month, using DAX expression : DateMonth = STARTOFMONTH('combined data'[Date])
- Step 6 : creating another column "SL Count" to calculate the number of sick leaves :
SL count = SWITCH( TRUE(), 
'combined data'[Value]= "SL",1,
'combined data'[Value]= "HSL",0.5,
0
)
- Step 7 : Creating another column for "WFH" to calculte the number of employes working from home, using DAX expression :
wfh count = SWITCH( TRUE(), 
'combined data'[Value]= "WFH",1,
'combined data'[Value]= "HWFH",0.5,
0
)
- Step 8 : Creating "Measures Tables" file for all the measures we are willing to use in the present project.
- Step 9 : Calcuting total working days excluding weeks off and home off.
- Step 10 : Calculating pourcentage of presence : presence % = DIVIDE([PresentDays], [Total working days],0)
- Step 11 : Calculating pourcentage of Sick leave : SL % = DIVIDE([SL count], [Total working days],0)
- Step 12 : Calculating pourcentage of employes working from home :WFH % = DIVIDE([WFH], [PresentDays],0)
- Step 13 : Trying to automate things and make the dashbord more dynamique by applying a function as a parametre


        
Snap of the final Dashbord,

![gag](https://github.com/yassinechouikh/Humain-Ressources-insights/assets/147276905/b49acf56-4c03-4165-b7e0-c3519a045f86)

        
Retrievel insights :

- The trend line of presence porcentage is increasing will sick leave and work from home is decreasing, witch is ogic and push us ask the question: whene precisely employees prefere to be present or work from home.
![P1](https://github.com/yassinechouikh/Humain-Ressources-insights/assets/147276905/7ceedca5-baf1-40ec-ad03-6b5b21330593)
- The highest presence pourcentage is at monday each week.
- The hughest pourcentage of work from home is in Friday.
![presence01](https://github.com/yassinechouikh/Humain-Ressources-insights/assets/147276905/90a8f297-81c8-42b4-945c-a30cc30ad76a)
- Avril2022 represente the highest presence pourcentage.
![P1](https://github.com/yassinechouikh/Humain-Ressources-insights/assets/147276905/5164004b-be4e-4729-b869-8b899ad63eee)
- Mai2022 give the highest work from Home pourcentage and the lowest presence pourcentage.
![P2](https://github.com/yassinechouikh/Humain-Ressources-insights/assets/147276905/0174a984-b55a-4d7d-94ac-5cf1796dc951)








