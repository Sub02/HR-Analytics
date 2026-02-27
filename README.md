📊 HR Performance Intelligence Dashboard
Department Benchmarking, Ranking & Tenure Analytics using Power BI
🔎 Project Objective

To analyze department-wise employee performance.

To benchmark department ratings against overall company performance.

To rank departments using DAX-based ranking logic.

To evaluate employee tenure across departments.

To design an executive-ready interactive HR dashboard.

📌 Purpose of HR Analytics

To enable leadership teams to track, compare, and improve departmental performance using structured data modeling and benchmark-driven analysis.

📈 Significance of Examining HR Reports

Identify high-performing and underperforming departments.

Compare department performance against company benchmark.

Understand ranking hierarchy.

Analyze employee service span distribution.

Support data-driven HR strategy decisions.

🧠 What the Dashboard Does

Compares Department Average Rating vs Company Average Rating.

Ranks departments dynamically using RANKX.

Calculates employee service span using DATEDIFF.

Uses CALCULATE + ALL to remove filter context for benchmarking.

Provides interactive slicer-based department analysis.

Displays KPI cards for quick executive interpretation.

🏗️ Data Model Architecture

The project follows a Star Schema Design.

Dimension Table

Department Desc

Department ID

Department Name

Fact Table

EmployeeData

Employee ID

Department ID

Performance Rating

Start Date

End Date

Service Span

Relationship
Department Desc (1)  →  EmployeeData (*)

One-to-Many Cardinality

Single Direction Filtering

Corrected auto-detected relationship configuration

📷 Data Model View

📊 Dashboard Preview

🔬 Key DAX Measures
Company Average Rating
Company Average Rating =
CALCULATE(
    AVERAGE(EmployeeData[PerformanceRating]),
    ALL(EmployeeData)
)
Department Wise Rating
Department Wise Rating =
AVERAGE(EmployeeData[PerformanceRating])
Department Rank
Department Rank =
RANKX(
    ALL('Department Desc'[Department]),
    [Department Wise Rating],
    ,
    DESC,
    DENSE
)
Service Span (Calculated Column)
Service Span(Emp) =
DATEDIFF(
    EmployeeData[StartDate],
    EmployeeData[Updated End Date],
    YEAR
)
🛠 Technical Skills Demonstrated

Star Schema Data Modeling

Relationship Cardinality Management

Filter Context Handling

DAX:

CALCULATE

ALL

RANKX

SWITCH

SELECTEDVALUE

DATEDIFF

KPI Design

Benchmark Comparison Logic

Dashboard UI Structuring

💼 Business Interpretation Skills

Translating performance data into actionable insights.

Benchmark-based performance evaluation.

Identifying improvement opportunities.

Designing executive-level dashboards.

🚀 Key Learning Outcomes

Importance of correct relationship configuration.

Avoiding many-to-many modeling issues.

Controlling filter propagation.

Building decision-support dashboards instead of static reports.

👤 Author

Shubhayan Kundu
Aspiring Data Analyst | Power BI | SQL | Python
