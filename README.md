
# Fleet Management Dashboard

### https://github.com/sivasundaram2106/Fleet-Management-Dashboard/tree/main

## Customer Retention Strategies Requirement Summary:

Objective:
Implement effective customer retention strategies to enhance customer loyalty and satisfaction, focusing on customers placing multiple orders.

Key Focus Areas:

Customer Segmentation
Personalised Communication
Incentive Programs
Customer Feedback and Concerns
Monitoring and Evaluation

## Fleet Management Dashboard - Driver Dahsboard


### Steps followed 

- Step 1: Creating KPIs in Power BI

Key Performance Indicators (KPIs) in Power BI enable businesses to monitor and measure their success in achieving specific objectives
Total Fix Cost
DAX Measure:
DAX
Copy code
Total Fix Cost = SUM(FactTable_fKMTraveled[Fixed Costs])
Formatted Value: $1.63M (Formatted in Dollars)
![FIX DAX](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/9acee8fc-c810-4f5e-aeaf-bc4cefb53824)

![FIX](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/69c86468-3a03-480e-927e-8236c99a50e8)

- Step 2: Total Driver
DAX Measure:
DAX
Copy code
Total Driver = COUNTROWS(FactTable_fKMTraveled)
Formatted Value: 189

![TOTAL DRIVER](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/5c36774d-0f4d-429b-909b-3238d43dbe76)

- Step 3: Total Fuel Consumed
DAX Measure:
DAX
Copy code
Total Fuel Consumed = SUM(FactTable_fKMTraveled[Fuel Consumed])
Formatted Value: $550.42 (Formatted in Dollars)

![TOTAL FULL CONS](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/f81fc996-0e68-44d7-9e98-9e47f69b0319)

- Step 4: Total KM Travel
DAX Measure:
DAX
Copy code
Total KM Travel = SUM(FactTable_fKMTraveled[KM Traveled])
Formatted Value: 722K (Formatted in Kilometers)

![TOTAL KM TRA](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/3ae3ae67-17b2-4d11-aba7-402d154553ff)

- SStep 5: Total Litre Consumed
DAX Measure:
DAX
Copy code
Total Litre Consumed = SUM(FactTable_fKMTraveled[Litre Consumed])
Formatted Value: 166K (Formatted in Liters)

![LITRE CON](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/87694471-83da-43be-a9bf-46c6c1e8ad3a)

- Step 6: Total Maintenance Cost
DAX Measure:
DAX
Copy code
Total Maintenance Cost = SUM(FactTable_fKMTraveled[Maintenance Cost])
Formatted Value: $171.3K (Formatted in Dollars)

![MAINT](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/19fe7492-97d7-4c15-8091-79a65751d9eb)
m2106/Healthcare-Analytic-Dashboard/assets/141480288/87694471-83da-43be-a9bf-46c6c1e8ad3a)


- Step 7 : Switch Drive Measure:

This is the name of the DAX measure you are creating.
Switch(True(), ...):

The SWITCH function is being used. It evaluates conditions in the provided order until it finds one that is true.
SELECTEDMEASURE():

This function retrieves the name of the currently selected measure.
"Fix Cost", [Fix Cost], ...:

If the currently selected measure is "Fix Cost," the SWITCH statement returns the value of the [Fix Cost] measure.
"Fuel Consumed", [Fuel Consumed], ...:

If the currently selected measure is "Fuel Consumed," the SWITCH statement returns the value of the [Fuel Consumed] measure.
"KM Traveled", [KM Traveled], ...:

If the currently selected measure is "KM Traveled," the SWITCH statement returns the value of the [KM Traveled] measure.
"Litre Consumed", [Total Litre Consumed], ...:

If the currently selected measure is "Litre Consumed," the SWITCH statement returns the value of the [Total Litre Consumed] measure.
"Maintenance Cost", [Maintenance Cost], ...:

If the currently selected measure is "Maintenance Cost," the SWITCH statement returns the value of the [Maintenance Cost] measure.
"Total drives", [Total drives], ...:

If the currently selected measure is "Total drives," the SWITCH statement returns the value of the [Total drives] measure.
BLANK():

If none of the conditions are met, the SWITCH statement returns a blank value.
This DAX measure provides a dynamic filter based on the currently selected measure, allowing for flexibility in your reporting. Adjust the measure names based on your actual measure names in the 'Measure Table'.

![DATE DAX](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/6538afb6-225d-49b1-a58e-df2022cf7561)

![PARAMETER](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/2eaec86e-ac83-4e26-8beb-12c9ef48b075)


![CHART](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/2632b77c-19c9-47a7-8a6a-c4e237a93008)

- Step 8 :Create the Comparison Table
ComparisonTable =

A new table is being created using the SUMMARIZE function.
SUMMARIZE:

Aggregates data based on specified columns.
DriverList:

The table to be summarized is DriverList.
DriverList[DriverName]:

The unique driver names from the DriverList table are included in the new table.
"Total Fix Cost", [Total Fix Cost], ...:

For each driver, the corresponding values for various measures are included in the new table.
Replace [Total Fix Cost], [Total Driver], [Total Fuel Consumed], [Total KM Travel], [Total Litre Consumed], and [Total Maintenance Cost] with your actual measure names.
This DAX formula creates a table (ComparisonTable) that compares the specified measures against the driver list. Adjust it based on your actual data model and measure names.

![TABLE](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/e4addf81-34af-409b-b827-72eac9008193)


- Step 9 : Default View:
Set up your report with the default view you want when the report is opened.
Create a bookmark for this state (e.g., "InitialState").
Step 2: Create Buttons
Create Buttons:
Go to the "Home" tab in Power BI.
Add two buttons (e.g., "Open" and "Close").
Step 3: Configure Bookmarks
Bookmark for Open State:

Adjust filters to show the open state for truck and trailer types.
Create a bookmark for this state (e.g., "OpenState").
Bookmark for Close State:

Adjust filters to show the close state for truck and trailer types.
Create a bookmark for this state (e.g., "CloseState").
Step 4: Add Bookmark Actions
Bookmark Actions:
Link the "Open" button to the "OpenState" bookmark.
Link the "Close" button to the "CloseState" bookmark.
Step 5: Toggle Visibility
Toggle Visibility:
Select visuals (e.g., truck and trailer types) to show/hide.
Set the visibility property using a DAX expression:
DAX
Copy code
IF(SELECTEDVALUE('BookmarkButtons'[CurrentState]) = "Open", TRUE, FALSE)
Replace 'BookmarkButtons' with the actual table name containing the buttons.
Step 6: Test and Adjust
Test the Report:

Click the "Open" and "Close" buttons to test if visuals toggle based on bookmarks.
Adjust as Needed:

Fine-tune the report layout, visuals, and bookmark actions to meet specific requirements.
These steps provide a simplified guide for creating dynamic open and close filtering using bookmarks in Power BI. Adjust details based on your report structure and preferences.

![OPEN FILTER](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/b22687df-8dfd-457e-9b09-1ef8696e0719)

- Step 10 : Create Tooltip Measure:

Develop a DAX measure called DriverTooltip that combines information on [Total Fix Cost], [Total Driver], [Total Fuel Consumed], [Total KM Travel], [Total Litre Consumed], and [Total Maintenance Cost] with appropriate formatting.
Add Tooltip to Table:

Enable the tooltip feature for the desired column or row in your table.
Link the tooltip to the DriverTooltip measure.
Test Tooltip:

Return to the report view and hover over the selected column or row in the table to ensure the tooltip displays the desired information.
Create Visual Interaction (Optional):

Optionally, configure the tooltip to appear on a click instead of hover by adjusting the "Page Information" settings in the "Format" pane.
Adjust Formatting (Optional):

Optionally, fine-tune the formatting within the DriverTooltip measure to suit your visual preferences.
These steps will help you create a dynamic tooltip in Power BI that provides detailed information when interacting with a specific row or column in your table. Adjust as needed based on your actual data model and preferences.

![DRIVEN TOOL](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/5001c222-ab26-4a65-bf63-adeaa5cf4300)
2106/Healthcare-Analytic-Dashboard/assets/141480288/b22687df-8dfd-457e-9b09-1ef8696e0719)


- Step 11 : Step 1: Design the Background in PowerPoint
Open PowerPoint:

Open PowerPoint on your computer.
Design the Background:

Create a new slide and design the background according to your preferences. This can include colors, shapes, logos, and any other design elements you want to include.
Save as Image:

Once you are satisfied with the design, save the PowerPoint slide as an image.
Go to "File" -> "Save As."
Choose the image format (e.g., PNG or JPG) and save the slide as an image file.
Step 2: Use Image as Background in Power BI
Open Power BI:

Open Power BI Desktop on your computer.
Create a New Report:

Create a new report or open an existing one.
Insert Image:

Go to the "Home" tab in Power BI.
Click on "Image" in the External Data group.
Select the Image:

Choose the image file you saved from PowerPoint.
Adjust Image Size:

Adjust the size and position of the image to cover the entire report canvas.
Send Image to Back:

Right-click on the image and choose "Send to Back" to make sure it serves as the background.
Set Transparency (Optional):

If you want the background to be less prominent, you can set transparency.
Select the image, go to the "Format" tab, and adjust the transparency level.
Save and Use:

Save your Power BI report with the background image.
Now, your Power BI report will have a custom background based on the template you designed in PowerPoint. Adjust the elements as needed, and remember to arrange your visuals on top of the background image.

![Presentation2](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/dc725432-4bd0-431f-be14-c8d545a134ea)

## Fleet Management Dashboard - Driver Dahsboard

![PROJECT-1](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/885f7796-836d-4c99-a09e-be7bb658f2ad)


## Fleet Management Dashboard - Revenue Insights


- Step 1: Creating KPIs in Power BI

Key Performance Indicators (KPIs) in Power BI enable businesses to monitor and measure their success in achieving specific objectives

Total Deliver Orders using DISTINCTCOUNT:
In Power BI, navigate to the "Model" view.
Click on "New Measure" in the modeling tab.
Create a measure using the DISTINCTCOUNT function for the unique order count.
DAX
Copy code
Total Deliver Orders = DISTINCTCOUNT(FactTable_Freight[OrderID])
Replace FactTable_Freight[OrderID] with the actual column representing unique order identifiers in your dataset.

If you have 92,000 distinct orders, the measure should display that value.

![image](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/9a54a6d8-aa3e-41e9-836c-d9a1e66001f7)

- Step 2: Total Goods Value:
Create a new measure for the total goods value using the SUM function.
DAX
Copy code
Total Goods Value = SUM(FactTable_Freight[Goods Value])
Replace FactTable_Freight[Goods Value] with the actual column containing the goods value.

If the total goods value is $12 billion, this measure should display that value.

- Step 3: Total Revenue:
Create another measure for the total revenue using the SUM function.
DAX
Copy code
Total Revenue = -SUM(FactTable_Freight[Revenue])
Replace FactTable_Freight[Revenue] with the actual column representing revenue.

If the total revenue is -$485 million (assuming negative indicates a loss), this measure should display that value.

- Step 4: Total Weight (Cubic):
Create a measure for the total cubic weight using the SUM function.
DAX
Copy code
Total Weight (Cubic) = SUM(FactTable_Freight[Cubic Weight])
Replace FactTable_Freight[Cubic Weight] with the actual column for cubic weight.

If the total cubic weight is 447 million, this measure should display that value.

- Step 5: Total Weight (Tons):
Create a measure for the total weight in tons using the SUM function.
DAX
Copy code
Total Weight (Tons) = SUM(FactTable_Freight[Weight in Tons])
Replace FactTable_Freight[Weight in Tons] with the actual column representing weight in tons.

If the total weight in tons is 664,000, this measure should display that value.

After creating these measures, you can use them in your Power BI reports and dashboards to visualize and analyze the key performance indicators based on the provided values.


- Step 6:Customers With Multiple Orders:
Create a Measure:

In Power BI, go to the "Model" view.
Click on "New Measure" in the modeling tab.
Use CALCULATE and COUNT:

Enter the following DAX formula to count the customers with multiple orders:
DAX
Copy code
Customers With Multiple Orders = 
CALCULATE(
    COUNTROWS(FactTable_Freight),
    FactTable_Freight[HasOneOrderOrMultiple] = "Yes"
)
Display the Result:

This measure will count the rows where the column HasOneOrderOrMultiple is set to "Yes" and display the result.
DAX
Copy code
Customers With Multiple Orders = 90,000 (Assuming this is the count)
Customers With One Order:
Create Another Measure:

Click on "New Measure" again in the modeling tab.
Use CALCULATE and COUNT:

- Step 7:Enter the following DAX formula to count the customers with only one order:
DAX
Copy code
Customers With One Order = 
CALCULATE(
    COUNTROWS(FactTable_Freight),
    FactTable_Freight[HasOneOrderOrMultiple] = "No"
)
Display the Result:

This measure will count the rows where the column HasOneOrderOrMultiple is set to "No" and display the result.
DAX
Copy code
Customers With One Order = 1,078 (Assuming this is the count)
Ensure that the column references (FactTable_Freight[HasOneOrderOrMultiple]) match the actual column names in your dataset. After creating these measures, you can use them in your Power BI reports to understand the distribution of customers based on their order count. Adjust the column names and counts as needed for your specific dataset.

- Step 7:YoY Total Deliver Order:
DAX
Copy code
(%)YOY Total Deliver Order = 
VAR _CurrentYearDeliverOrder = [Total Deliver Orders]
VAR _PreviousYearDeliverOrder =
    CALCULATE(
        [Total Deliver Orders],
        SAMEPERIODLASTYEAR(DateTable[Date])
    )
RETURN
    DIVIDE(_CurrentYearDeliverOrder - _PreviousYearDeliverOrder, _PreviousYearDeliverOrder, 0)
Result: (%)YOY Total Deliver Order = 93.34%

![image](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/7cb4bb3d-3e7b-48f9-8d78-52a539aa4399)

YoY Total Goods Value:
DAX
Copy code
(%)YOY Total Goods Value = 82.37%
YoY Total Revenue:
DAX
Copy code
(%)YOY Total Revenue = 91%
YoY Total Weight (Cubic):
DAX
Copy code
(%)YOY Total Weight (Cube) = 68.17%
YoY Total Weight (Ton):
DAX
Copy code
(%)YOY Total Weight (Ton) = 70.82%
Customer Segmentation:
DAX
Copy code
% Of Repeat Customers = 
DIVIDE(
    [Customers With Multiple Orders],
    ([Customers With Multiple Orders] + [Customers With One Orders]),
    0
)
Result: % Of Repeat Customers = 98%

DAX
Copy code
% Of One-Time Customers = 2%

- Step 7:Data Model:

Ensure date-related and revenue tables in the data model.
Create Measure:

Make a measure for total revenue using SUM function.
DAX
Copy code
Total Revenue = SUM('TotalRevenueTable'[Revenue])
Line Chart:

In Power BI, create a line chart.
Use the date field for the X-axis and the Total Revenue measure for the Y-axis.
Format and Enhance:

Format the chart, add title, legend, and trendline.
Apply filters for specific time ranges if needed.
Enhance interactivity with tooltips and drill-through features.
Result:

Visual representation of months vs. total revenue trends.
This streamlined version covers the essential steps for creating a Months vs. Total Revenue chart in Power BI. Adjust as per your dataset and preferences.

![image](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/16d8280a-84de-472d-bccf-44bfc890c669)

- Step 7:Data Model:

Ensure your dataset includes a column with the names of the states and another column with the corresponding data you want to visualize.
Add State Names to Data Model:

If your dataset doesn't have a separate state names column, consider adding one.
Shape Map Visualization:

In Power BI, go to the "Visualizations" pane.

Choose the "Shape Map" visualization.

Add Location and Size Fields:

Drag the state names field to the Location bucket.

Drag the data field you want to visualize to the Size bucket. This determines the size of the shapes on the map.

Adjust Map Visualization:

![image](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/238cbac8-ad40-4e62-acb3-32f195ca7ed8)

The map should automatically recognize the state names and display them.

Adjust the visualization settings, such as colors, legend, and map style, according to your preferences.

Fill and Border Colors:

You can set different fill and border colors for the states based on your data values.
Tooltip:

Customize the tooltip to display relevant information when users hover over each state.
Data Labels (Optional):

If needed, you can add data labels to the states for a clearer representation of the values.
Filters (Optional):

Apply filters to focus on specific states or regions if required.
Interactivity (Optional):

Enable interactivity features like drill-through to allow users to explore more details.
Result:

A Shape Map chart in Power BI displaying your data across different states.

![image](https://github.com/sivasundaram2106/Healthcare-Analytic-Dashboard/assets/141480288/fcdd1700-6554-49b0-9f4b-71faca17fdb0)

## KEY INSIGHTS:

Given the observed customer order distribution (% Of One-Time Customers = 2%, % Of Repeat Customers = 98%), here are some key recommendations and insights, accompanied by relevant strategies and actions:

Customer Retention Strategies:

Insight: The majority of customers are repeat customers.
Recommendation: Implement customer retention strategies.
Strategy: Launch loyalty programs, enhance personalized communication, and ensure exceptional customer service to foster repeat business.
Upselling and Cross-Selling Opportunities:

Insight: Customers with multiple orders present upselling and cross-selling potential.
Recommendation: Leverage order patterns for increased average order value.
Strategy: Analyze purchase patterns, recommend related products, and identify opportunities to enhance the overall shopping experience.
Customer Engagement:

Insight: Regular customer engagement can drive repeat purchases.
Recommendation: Keep customers informed about promotions and updates.
Strategy: Implement regular email campaigns, newsletters, and social media engagement to maintain customer interest.
Feedback and Reviews:

Insight: Positive reviews can boost customer loyalty.
Recommendation: Encourage customer feedback and reviews.
Strategy: Create a system to collect and showcase customer reviews, fostering trust and attracting new customers.
Targeted Marketing:

Insight: Segmenting customers based on behavior is effective.
Recommendation: Implement targeted marketing campaigns.
Strategy: Use customer segmentation to tailor promotions and incentives, enhancing the likelihood of repeat purchases.
Customer Journey Analysis:

Insight: Understanding the customer journey is crucial.
Recommendation: Analyze the customer journey for improvements.
Strategy: Identify and address any issues or pain points in the customer journey to enhance overall satisfaction.
Customer Support:

Insight: Satisfied customers are more likely to return.
Recommendation: Provide excellent customer support.
Strategy: Address customer issues promptly and efficiently, ensuring a positive experience.
Referral Programs:

Insight: Satisfied customers can be advocates for your business.
Recommendation: Encourage referrals with incentives.
Strategy: Implement referral programs to harness the power of word-of-mouth marketing.
Competitor Analysis:

Insight: Understanding why customers choose your business is key.
Recommendation: Regularly assess and analyze competitors.
Strategy: Use competitor insights to refine and enhance your offerings.
Conclusion: By capitalizing on customer retention, optimizing the customer journey, and strategically engaging customers, businesses can leverage a loyal customer base for sustained growth and increased order volume.

Note: The effectiveness of these strategies can be further measured and refined through ongoing analysis and monitoring of key performance indicators (KPIs).













