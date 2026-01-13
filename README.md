# Personal-Expense-Dashboard

<img width="2517" height="1294" alt="MyDashboard_screenshot png" src="https://github.com/user-attachments/assets/0f2e06f7-3950-4da0-aa1f-84cf919bb861" />

## The Goal
I built this dashboard for one simple reason: To make better decisions about my money. I wanted to stop guessing where my budget was going and create a system that tracks my daily expenses, visualizes my spending habits, and helps me decide if I can afford that next purchase. This project takes the manual work out of budgeting by automating the math and categorization.

---

## How It Works (The Workflow)
### 1. Data Input (Excel)
- I use a simple Excel sheet as my database with columns for Date, Store, Amount, and Description.

- I load the data into Power BI as a formatted Table (not just the raw Sheet) to avoid importing empty blank cells.

### 2. Data Transformation (Power Query) 
- I use Power BI to clean the messy data so I don't have to fix it manually in Excel every time.

- **Normalization**: I use "Replace Values" to fix inconsistencies (e.g., standardizing "B&B" and "BBW" into a single name).

- **Automated Categorization**: I created a conditional column (AutoCategory) that assigns categories based on the store name (e.g., If Store = Walmart, then Groceries).

- **The "Restaurant" Logic**: To catch new restaurants without writing a new rule for every single one, I simply add the suffix "Restaurant" to the name in Excel (e.g., "Osmows Restaurant"). My logic then checks: If Store contains "Restaurant" -> Category = Restaurant.

- **Order of Operations**: I learned that Power BI processes steps from top to bottom. I specifically organized my "Applied Steps" to ensure that Renaming and Capitalization happen before the Categorization logic runs, ensuring no data gets missed.

### 3. Visualization (The Dashboard)
- **Search Engine**: A slicer set to "Search" mode allows me to instantly find specific transactions (e.g., typing "coffee" or "Uber").

- **Monthly Analysis**: A Date Slicer allows me to filter the view to a specific month (e.g., May) to see if I stayed on budget.

- **Habit Tracking**: A Bar Chart visualizes which categories (Dining vs. Transport) are consuming the most funds.![Uploading my_dashboard_screenshot.png.png…]()


- **The Bottom Line**: A KPI Card displays the exact total spent based on the current filters.

---

### Future Improvements
- **Dynamic High-Spenders**: I plan to update the logic to automatically flag specific stores as their own unique category if I consistently spend over $50/month there for two consecutive months.

- **Sales Analysis**: My next project will apply these same principles to a larger corporate dataset to analyze sales performance and profit margins.
