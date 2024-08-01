# Dynamic Title in KPI

Hey everyone! 🌍🤝 
I hope you are doing great :)

Today, I will present you with a dynamic title at KPI. 

What can a dynamic title be used for?

Suppose we have several kpi on our report page. If there is no slicer with the selection of the year by which we want to sort the data, we will not find out from how many years or months our KPI results are presented.
Besides, if we analyse a given report for a long time, it can be tiresome to keep clicking on the slicer which contains a drop-down list and checking what is happening....

With help comes the DYNAMIC TITLE 🚀 !!!

Let's start with a slicer of the year and KPI with Revenue. 
RESULT :

![image](https://github.com/user-attachments/assets/8eb9e44f-4325-40b7-a66f-c3e0c585c796)

All right, but what next?

First, let's go to the format of our KPI and find the section with the title.

![image](https://github.com/user-attachments/assets/99382cc6-37ff-4b4e-9771-7fd8cf202ba7)

As we can see, next to the title we have FX -> which stands for conditional formatting. 
Let's find out what's in it.

![image](https://github.com/user-attachments/assets/f1805e16-071c-4533-9071-235e02f76ac7)

As we can see, we have two options to choose from. Format style should be set to Field Value by default.
The section "What field should we base this on" allows us to select a measure in DAX language. 

So what is left for us but to write a simple measure that will help us display the range of years in which our report page is currently viewed ? 
Go for it !

RESULT:

![image](https://github.com/user-attachments/assets/5a2bc1fd-7033-4cec-9d7c-d4cf4f5cdfba)

The code is as follows :

Dynamic title = "Data for years ":

This is the beginning of the measure, which creates a text title. We start with the static part of the text: "Data for years ".
min('DimDate'[Year]):

The MIN function finds the smallest value in the Year column of the DimDate table. This means it selects the earliest year from the available data.
& "-" &:

The & operator in DAX is used to concatenate (join) texts. Here, we are concatenating three elements:
The first element is the static text "Data for years ".
The second element is the result of the MIN function, which is the earliest year.
The third element is the static text "-" (a hyphen).

MAX('DimDate'[Year]):

The MAX function finds the largest value in the Year column of the DimDate table. This means it selects the latest year from the available data.
Final Result:

Combining all these parts gives us a title that looks something like this: "Data for years 2015-2023".
This title dynamically changes based on the data available in the DimDate table.

Let's add our measure to the title and see the result !!! ✨✨

![image](https://github.com/user-attachments/assets/be6f6cb8-5581-417e-995b-3054aa01b077)

Let us point out that when we select nothing on the slicer by default, the result will contain information about the whole range of our data !

![image](https://github.com/user-attachments/assets/cb20ac91-4481-44fe-bd60-42ec554024ff)

It's all in this article! ✨
I hope I have helped both your report recipients and yourself:) 

Take care! 🤝 


