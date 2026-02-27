📊 HR Performance Intelligence Dashboard
Department Benchmarking, Ranking & Tenure Analytics using Power BI

🔎 Project Objective
1.Analyze department-wise employee performance
2.Benchmark department ratings against overall company performance
3.Rank departments using DAX-based ranking logic
4.Evaluate employee tenure across departments
5.Design an executive-ready interactive HR dashboard

📌 Purpose of HR Analytics
To enable leadership teams to track, compare, and improve departmental performance using structured data modeling and benchmark-driven analysis.

📈 Significance of Examining HR Reports
1.Identify high-performing and underperforming departments
2.Compare department performance against company benchmark
3.Understand ranking hierarchy
4.Analyze employee service span distribution
5.Support data-driven HR strategy decisions

🧠 What the Dashboard Does
1.Compares Department Average Rating vs Company Average Rating
2.Ranks departments dynamically using RANKX
3.Calculates employee service span using DATEDIFF
4.Uses CALCULATE + ALL to remove filter context for benchmarking
5.Provides interactive slicer-based department analysis
6.Displays KPI cards for quick executive interpretation

🏗 Data Model Architecture

The project follows a Star Schema Design.

🔹 Dimension Table

Department Desc

Department ID

Department Name

🔹 Fact Table

EmployeeData

Employee ID

Department ID

Performance Rating

Start Date

End Date

Service Span

🔹 Relationship

Department Desc (1) → EmployeeData (*)

One-to-Many Cardinality

Single Direction Filtering

Corrected auto-detected relationship configuration


🔬 Key DAX Measures

Company Average Rating:
*Company Average Rating =
CALCULATE(
    AVERAGE(EmployeeData[PerformanceRating]),
    ALL(EmployeeData)
)*

Department Wise Rating:
*Department Wise Rating =
AVERAGE(EmployeeData[PerformanceRating])*

Department Rank:
*Department Rank =
RANKX(
    ALL('Department Desc'[Department]),
    [Department Wise Rating],
    ,
    DESC,
    DENSE
)*

Service Span (Calculated Column):
*Service Span(Emp) =
DATEDIFF(
    EmployeeData[StartDate],
    EmployeeData[Updated End Date],
    YEAR
)*


🛠 Technical Skills Demonstrated

1.**Star Schema Data Modeling**

2.Relationship Cardinality Management

3.Filter Context Handling

4.DAX:

>CALCULATE

>ALL

>RANKX

>SWITCH

>SELECTEDVALUE

>DATEDIFF

>KPI Design

>Benchmark Comparison Logic

>Dashboard UI Structuring


💼 Business Interpretation Skills

1.Translating performance data into actionable insights
2.Benchmark-based performance evaluation
3.Identifying improvement opportunities
4.Designing executive-level dashboards

🚀 Key Learning Outcomes

1.Importance of correct relationship configuration
2.Avoiding many-to-many modeling issues
3.Controlling filter propagation
4.Building decision-support dashboards instead of static reports


👤 Author
Shubhayan Kundu
Aspiring Data Analyst | Power BI | SQL | Python
