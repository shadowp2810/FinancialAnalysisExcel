# FinancialAnalysisExcel

# 365 Financial Analyst Course 2021

Below are my notes from the course. <br>
From the solved solutions,
some are mine, and some are instructor provided. <br>
Putting these up here for personal reference.

<pre>   
Discounting Cash Flows (DCF approach)
 NPV() or Net Present Value 
 is the sum of discounted cash flows
 minus the initial investment
 -Money earned today is more valuable than money earned tomorrow
 -If buying a given stock,
  we first estimate future cash flows stock would generate,
  then we discount those cash flows,
  then add their present values,
  if amount is greater than initial investment,
  then investment is feasible.
 -Net Present Value = 
   PV(1) + ... + PV(n) - initial investment
   eg: cash flow in year 0 (-500) , year 1 (30) , year 2 (120)
       interest rate is 10%

       PV = (FV at year n) / ((1+i)^n)

       present value is year 0 (-500) , 
       pv of year 1 is 30/((1+0.10)^1) ,
       pv of year 2 is 1200/((1+0.10)^2)
       ...,

       if initial investment < PV(1) + ... + PV(n)
       then project is not feasible.
<br>

Discounting Cash Flows (Excel "NPV" approach)
- =SUM(E8,NPV(C4,F8:J8))
  where E8 is initial investment or year 0, 
  C4 is interest rate,
  F8:J8 is year 1 to year 5 cash flow.
<br> 

Internal Rate of Return or IRR()
 is the discounted rate used
 for measuring the profitability of potential investments.
 - eg =IRR(E8:J8) 
      where E8 is year 0 cash flow and J8 is year 5 cash flow
      giving 5%.
      Can redo PV calculation for each year cash flow,
      using this 5% instead of 10%.
      The rate of return is lower than interest rate
      and so we cannot afford this project.

      if IRR < i then do not invest
      if IRR > i then invest.
<br>

Both NPV and IRR are used to calculate profitability of projects.
<br>

For Loan Scheduled payments
on excel can use PMT payment 
using monthly interest rate(C5), num of periods(C3) and loan amount(C6).
eg =PMT(C5,C3,C6)
We create a table 
   Period, Payment, Interest, Principal, Residual Debt
eg  1 , 
    (monthly payment) , 
    (loan amount * interest rate) ,
    (payment - interest = principal) ,
    (residual debt = previous residual debt - principal)
<br>

-------
Excel Dates
"DAY"
"MONTH"
"YEAR"
Can add or subtract within function for future or past date
"EOMONTH" for last day of month
- eg =EOMONTH(C5,0) for last day of same month
"EDATE" for exact day months before or from now
- eg =EDATE(F5,5)
EDATE is used to calculate maturity or due date,
that fall on same day of month as day of issuance.
<br>

--------

Profit and Loss Statement from Raw Data Extraction


Eg company GENERCO and P&L statement for three years
<br>

To delete irrelevant rows, select entire table and use "FILTER",
then set filter to show 
eg: "total" cell values and delete all those rows
<br>

If no unique code exists to identify, 
use & or concatenate using eg the account number and parent company id.
<br>

You can copy and paste codes from all years on one column,
select the table, go to "Data" then "Remove Duplicates"
<br>

Can then use "VLOOKUP" to full in the rest of 
<br>

We use "SUMIF" for for the revenue and costs of the business.
-eg =SUMIF(range;criteria;[sum_range])
-eg =-SUMIF(code2016shet;allcode;amounts2016)
    revenues are negative by default and costs positive
<br>

alternatively can use index and match
<br>

We classify many sub-ledgers into a single sub-ledger for easier viewing
eg: Typical P&L categories: Revenue, cost of goods sold,
     operating expenses(non-factory personnel, rent, utility expenses,
     marketing and advertising costs, travel expenses, 
     service expenses, legal fees), D&A , interest expenses, 
     Extraordinary items, Taxes
eg: of P&L statement in main column from mapping might be 
     Net Sales + Other Revenues + Recharges = Total revenue , 
     Total revenue - Direct Costs = Gross Margin , 
     other operating expenses , Personal expenses , 
     Leasing , Services , Travel costs, Other Income , 
     Capitalized costs, 
     EBITDA (Earnings before interests, taxes, 
      depreciation and amortization)
     D&A , EBB (Earnings before interests and taxes),
     Financial Items, Extraordinary Items, EBT, Taxes, 
     Net Income
<br>

-----

Slicers in pivot tables can be used
to filter and show only relevant data
<br>

Case Study FMCG modelling
ERP(Enterprise Resource Planning)
- Integrated software solutions used by companies to collect, store
  and manage data from business activities.
- They are data warehouses
<br>

eg titles are Material Number, Material Description, Period, 
   Brand, Size, Pack, Client, Client Type, Volume, Gross Sales, 
   Discounts, Net Sales, Cost of Goods Sold,
   Distribution, Warehousing expenses.
   Distribution is transport expenditure. 
   Warehousing is cost for keeping item in warehouse facility.
"RIGHT" and "LEFT" to create from seperated Period cell values 
the Month and Year. 
<br>

A new sheet can be made to showcase data by year columns.
Volume, (Gross Sales Income, Discounts, Net Sales) ,
(Cost of Goods Sold, Gross Profit) , 
(Distribution, Warehousing, Fill Delivered Margin) 
<br>

Net Sales = Gross Sales Income + Discounts
Gross Profit = Net Sales + Cost of Goods Sold
Full Delivered Margin = Gross Profit + Distribution + Warehousing
<br>

KPI (Key Performance Indicators) 
- Gross Profit %
- FDM %
<br>

A pivot table using original data extracted can be made.
Filters-
Columns- Year , Month
Rows- Brand
Values- Volume, Gross Sales, Discounts, Net Sales, 
        Cost of Goods Sold, Distribution, Warehousing
<br>

Using the Slicers and Filters you can build a story around the data.
Clicking on each brand and find the best and worst performing brands.
Clicking on each brand and each client can find 
problematic client accounts and to find root of problem. 
<br>

-------
Building a financial Model
<br>

Depreciation & Amortization (D&A) represents 
the expenses associated with fixed assets and 
intangible assets that have been capitalized on the Balance Sheet.
<br>

COGS - Cost of Goods Sold
OPEX - Operating Expences
EBITDA - earnings before interest, 
         taxes, depreciation, and amortization
<br>

Gross Profit = Revenue - Cost of Goods Sold
EBITDA = Gross Profit - OPEX
EBIT = EBITDA - D&A 
EBT = EBIT - interest expenses
Net Income = EBT - Taxes
<br>

Assets must be equal to Liability + Equity
Assets = Trade Receivables + Inventory + PP&E + Cash + Other Assets
Liabilities & Equity = Trade Payables + Provisions + 
                       Financial Liabilities + Other Liabilities +
                       Equity
<br>


In adding a forecast period for future years
Scenarios are
Best, Base and Worst case for 
Revenue % growth, Cogs as % of Revenues, OPEX as % of Revenues
<br>

CCC is cash conversion cycle
DSO - Days Sales Outstanding (DSO) is the average number of days taken by a firm to collect payment from their customers after the completion of a sale.
DPO - Days payable outstanding (DPO) computes the average number of days a company needs to pay its bills and obligations
DIO - Days inventory outstanding (DIO) is a working capital management ratio that measures the average number of days that a company holds inventory for before turning it into sales.
<br>

DSO * (Revenues 2017 / 360) = Trade Receivables 2017
DPO * (Cogs 2017 / 360) = Trade Payables 2017
DIO * (Cogs 2017 / 360) = Inventory 2017
<br>

PP&E can be found using Fixed Asset Roll Forward
Property, plant, and equipment (PP&E) are long-term assets vital to 
business operations and not easily converted into cash. Property, 
plant, and equipment are tangible assets, meaning they are physical in 
nature or can be touched.
<br>

Capital expenditures (CapEx) are funds used by a company to acquire, 
upgrade, and maintain physical assets such as property, plants, 
buildings, technology, or equipment. 
<br>

D&A is a cost showing the firm's equipment is less valuable 
after being used for a year.
<br>

Capex increases PP&E as these are new PP&E acquisitions
<br>

Ending PP&E = Beginning PP&E + D&A + Capex
Ending PP&E for 2016 is beginning PP&E for 2017
<br>

Fixed Asset Roll Forward table contains 
Beginning PP&E, D&A, Capex and Ending PP&E 
<br>

Financial Liabilities table contains
Beginning Debt, New Debt, Principal Repayments and Ending Debt
<br>

Ending Debt for 2014 is Beginning Debt for 2015
Ending Debt = Beginning Debt + New Debt + Principal Repayments
<br>

Debt to be Repaid, Interest Rate and Annual payment  go below table.
Annual payment - =PMT(InterestRate, DebtToBeRepaid, EndingDebt)
<br>

For a Period of say 10 years we find
Payment, Interest expense, Debt repayment, Residual Debt
Where Payment stays same as annual payment,
Interest expense = -(Ending Debt * interest rate)
Debt Repayment = -(Interest Expense - Payment)
Residual Debt = Ending Debt - Debt Repayment
<br>

Equity Schedule Table contains 
Beginning Equity, Increase of Capital, Net Income(loss), 
Dividends, Ending Equity
Below table will be Dividends as % of Net Income
<br>

Ending Equity = Beginning Equity + increase in capital +
                new income (loss) + Dividends

<br>

Cash Flow Table contains
EBITDA, Interest Expenses, Taxes, Change in Trade Receivables,
Change in Inventory, Change in Trade Payables, Change in Other Assets,
Change in Other Liabilities, Capex, Operating Cash Flow, Dividends,
Change in Financial liabilities, Change in Provisions, 
Change in Equity, Net Cash Flow
<br>

Asset Increase during Cash Outflow: paid for asset
Asset Decrease during Cash Inflow: sold the asset
Liability Increase during Cash Inflow: receive financing
Liability Decrease during Cash Outflow: repaid financing
<br>

Cash Movement of Assets = 
 -1 * (This year's quantity - Last years's quantity)

<br>

--------

Accounting is an information science that is used to collect and 
organize financial data for organizations and individuals.
<br>

Accounting helps you use the past in order to take action
in the present and change the future.
<br>

Four main areas of Accounting:
-Bookkeeping is the collection of information
-Financial Accounting is prepared for external stakeholders
 (Income Statement, Balance Sheet and Cash Flow)
-Managerial Accounting is 
 the strategic information available to insiders
 (Pricing, competition, marginality, budgeting)
-Tax Accounting is calculation of income taxes
<br>

Bookkeeping is the foundation of Accounting.
<br>

Financial Accounting is for outsiders. Information for the investors
and lenders. eg the amount of sales this year and last year, or
how profitable the business is. Financial reports show what the
company owns and owes. And how much money is available to the company.
Allows outsiders to make reasonable judgement about company's business.
Financial reporting allows to monitor the company performance. 

<br>

US GAAP vs IFRS
<br>

Generally Accepted Accounting Principles (GAAP or US GAAP) are a collection of commonly-followed accounting rules and standards for financial reporting.
The four basic constraints associated with GAAP include objectivity, materiality, consistency and prudence
<br>

IFRS stands for international financial reporting standards. It's a set of accounting rules and standards that determine how accounting events should be reported in your business's financial statements.
<br>

US GAAP - US Generally accepted accounting principles
Every country has its own GAAP 
which makes things complicated so IFRS,
International Financial Reporting Standards,
was formed by the International Accounting Standards Board. 
<br>

All EU public companies use IFRS, 
but small and medium size companies may use local GAAP.
<br>

US companies to report with US GAAP
<br>

Financial Statement 
-Profit&Loss, Balance Sheet and Cash Flow
<br>

Income statement tells us how a company performed 
throughout the period under consideration. 1 year or quarterly.
<br>

P&L tell us if firm generated economic value and 
enables to find trends like revenue growth and
incidence of gross profit on revenues.
<br>

Balance sheet answers what a company own and owe at a certain date. 
Shows the assets a business owns,
the liabilities a business owes,
and the equity that belongs to equity holders. 
assets = liabilities + equity
<br>

Statement of Cash flow answers how much cash did a company make 
under the period of consideration and where it came from.
Measures Liquidity.
<br>

Income Statement contains 
Revenue or net sales.
Usually day to day sales 
or earning money from activities outside of core operations
eg: renting real estate. 
Classify by Revenue or Other Revenue by asking
is this part of core business.
Total Revenues = Revenues + Other Revenues
<br>

Most Common Expenses are
-Cost of goods sold (Cogs) , 
-Selling, General and Administrative Costs (SG&A) ,
-Depreciation and Amortization ,
-Interest Expenses ,
-Taxes
<br>

Cogs also includes the amount paid 
to personnel directly involved with production.
<br>

Gross Profit = Revenue - Cogs
<br>

Selling, General and Administrative Costs =
Operating costs (Advertising, IT, Accounting,
Everything different than production costs)
<br>

Office expenses also part of SG&A
<br>

EBITDA = Gross Profit - SG&A
EBITDA is Earnings before Interest, Tax, Depreciation and Amortization.
EBITDA shows how much is make with inclusion of direct and 
indirect expenses.
D&A reflects the using up of tangible and intangible assets.
Depreciation is for physical Assets (Factory).
Amortization is for intangible Assets (Patents).
<br>

EBIT = EBITDA - D&A
EBIT is Earnings before Interest and Taxes
<br>

Interest Expenses are costs a company bears for receiving financing.
<br>

EBT = EBIT - Interest Expenses
EBT is Earnings before Taxes
<br>

Taxes = Tax Rate * EBT
<br>

Net Income = EBT - Net Income
<br>

In the US a company can be required to pay both 
Federal and State Income Taxes
<br>

Tax calculation are by Federal and State Tax Laws.
<br>

AVG Tax Rate = Income Tax / EBT
<br>

Depreciation is shown as an expense in the Income Statement.
Depreciation can be calculated by Straight Line Depreciation,
or Depreciation based on use.
<br>

eg Straight Line Depreciation
   Initial cost: 30K, Salvage Value: 6K, Depreciated: 24K,
   Useful Life: 8y, Annual Depreciation: 3K

   Activity Based Depreciation
   Initial cost: 30K, Salvage Value: 6K, Depreciated: 24K,
   Useful Life: 200K miles, Depreciation per mile: $0.12,
   Annual Depreciation: 30K * 0.12 = 3.6K
<br>

Intangible Assets: Software Brands, Goodwill, Artistic Assets
Only Intangible Assets with finite life are subject to amortization.
<br>

Balance Sheet
What a company owns (Assets) | What a company owes (L&E)
<br>

Cash Account shows how much of a firm's assets are cash 
or can be easily converted in cash. Company Liquidity.
<br>

Account Receivable or Trade Receivables is
the money owed by customers that is not yet received.
<br>

Inventory is the account that shows the value of
raw material, goods in the process of elaboration,
and finished goods that are ready to be shipped to customers.
Located in warehouse, facilities, factories or stores.
<br>

Property, Plant and Equipment are Tangible Assets such as 
Factories, Machinery, Vehicles, Furniture, Equipment, ETC.
<br>

Assets can be current or non current 
by how easily they can be converted to cash.
Current Assets(Cash, Trade Receivables, Inventory).
Long Term Assets(Property, Plant, & Equipment)
<br>

Balance Sheet
Current Assets   |
Long Term Assets |
<br>

Other Current Assets include 
Available for Sale Investment Securities,
such as bonds, options, futures, 
and company shares bought because of extra liquidity. 
<br>

Deferred Income Taxes are Taxes the company paid now,
but relate to future periods.
Prepaid Expenses are costs paid in advance,
to be sustained in future eg next year rent.
Assets Held for Sale are Assets different from 
investment securities and that company wants to sell.
<br>


On Liabilities side there is
-Accounts Payable include payment owed to suppliers,
 such as raw materials, electricity, IT support.
-Financial Liabilities are external financing that serves for 
 financing a firms's business operations.
 Promise of payment to supplier after 180 days becomes 
 a financial liability as company now owes interest 
 for delayed payment.
-Tax Liabilities are Income Tax, Property Tax, VAT,
 regional or sales tax, owed at different points of time.
-Provisions is money set aside by company for future obligations.
 eg when another company sues this company.
<br>

Other Liabilities include
-Accrued Liabilities which reflect Income Statement expenses
 that have not been paid. eg if Balance sheet period ends on
 last day of year, but rent of past 6 months is due a few days
 after the end of balance sheet period.
-Liabilities held for sale are liabilities of a project or 
 entity held for sale.
-Debt due within one year.
-Long-Term Debt is company's non-current financial borrowings.
-Deferred income taxes are taxes that are due,
 but have not been paid yet.
-Other non-current liabilities are generic category grouping
 several types of liabilities. eg Pension benefits, 
 Other post-retirement benefits, Uncertain tax positions
<br>

Equity eg Dividends contains 
-Paid In Capital or the Firm's starting capital.
-Retained Earnings are the accumulated earnings 
 or profits that have not been distributed as dividends.
 A reinvestment on behalf of the shareholders.
-Net Income or the current profit made in current year.
<br>

Balance Sheet
Assets | Liabilities & Equity
<br>


Accrual Accounting
Accrual accounting is an accounting method where revenue or expenses are recorded when a transaction occurs rather than when payment is received or made. The method follows the matching principle, which says that revenues and expenses should be recognized in the same period.
<br>

The idea that the Revenues and costs should not be registered when 
cash is exchanged but should be registered when revenues are earned 
and when costs are incurred is called accrual accounting.
No firm uses cash accounting.
Income and cash are two different things.
<br>

Revenue Recognition:
-If the work is done
-If the seller company receives a valid promise of payment
<br>

Accounting to IFRS the 5 Revenue Recognition criteria:
-Risks and Rewards have been transferred from the seller to the buyer.
-The seller has no control over the goods sold.
-Collection of payment is reasonably assured.
-The amount of revenue can be reasonably measured.
-Costs of earning the revenue can be reasonably measured.
<br>

eg when a used car without a warranty is bought and 
   buyer leaves with it, then first two points are satisfied.
   That is Risk and Rewards, and Control have been transferred. 

   if there was a 5 year warranty then not all Risks have been 
   transferred and so some portion of unearned revenue is left on
   Liability side of Balance Sheet. 

   if in the third point it is likely the clients will default on
   payment, then cannot register full amount as revenue. 
<br>

Higher Revenues means:
Higher Profits, Higher Valuation, Easier Access To financing,
and More Appealing to Investors.
<br>

Internal and External Auditors oversees the Adherence of 
company financial accounting to IFRS standards.
<br>

eg of Revenue Recognition criteria in practice:

   A business sells orange juice at 5$ for 500ml.
   Risk and rewards transferred. 
   Control has been transferred. 
   Client paid for juice, so collection of payment is assured.
   Payment can be measured. 
   Costs of producing and providing juice can be measured.
   The 5 Rules are satisfied.

   A business sells orange juice and muffins.
   But is out of muffins and instead sells coupon for it.
   Risk and Rewards only partially transferred. 
   Control has not been transferred as muffin not derived yet.
   Client paid for juice and muffin so collection of payment assured.
   Payment can be measured, that is revenue reasonably measured.
   Costs of earning revenue can be measured.
   So here first 2 rules are not satisfied.
   So of 8$ paid for juice and muffin,
   4$ which is price of juice can be recognized as Revenue.
   4$ for muffins are Unearned Revenue. 
<br>

Expenses should be recognized in the same period as
Revenues to which they relate. 
This is the Matching Principle. 
Expenses not easily associated with Revenue generation. 
Account, Admin Personnel and Rent not directly attributable 
to products.
Period Costs- Expenses when sustained. 
<br>

eg: High end restaurant may buy the expensive meat 
    6 months in advance and prepare it to be served in 6 months. 
    Restaurant owners pay monthly rent and accounting costs. 
    Restaurant should register meat as an expense 
    when sold to customers. 
    As rent and accounting costs are not directly related,
    they are period costs and expensed in same period as sustained. 
    Product Costs vs Period Costs. 
<br>

Two P&L Income Statement formats. Single and Multi-Step.
<br>

Single P&L would contain on same table
Merchandise sales + Other Income = Toal Revenue ,
Cost of Goods Sold + D&A + Personnel + Rent 
+ Interest Expense + Utilities + Taxes = Total Expenses,
Toal Revenue - Total Expenses = Net Income. 
Simply subtracts Total Revenue from Total Costs and gives Net income. 
<br>

Multi-Step P&L should more difference in revenues and costs, contains
Merchandise sales + Other Income = Total Revenue , 
Total Revenue - Cost of Goods Sold = Gross Profit ,
Gross Profit - Personnel - Rent - Utilities = EBITDA ,
EBITDA - D&A = EBIT ,
EBIT - Interest Expenses = EBT ,
EBT - Taxes = Net Income.
<br>


Top line of P&L, that is Revenue Recognition from
sales a company makes is a measure of how large its business is 
and how it performed compared to previous periods 
is most important. 
Tells us if the business grew , 
if it grew faster than companies in the industry ,
or if the business is slowing down.
And from it how likely the performance will continue in future.
<br>

Recording revenues earlier will boost income for current year. 
FASB(Financial Accounting Standards Board) and
IASB(International Accounting Standards Board) have 
created a set of rigid rules to ensure proper revenue recognition.
<br>

Revenue is recognized in the Income Statement 
when it is realized and earned. 
<br>

Revenue should be recognized when:
-There is evidence of an arrangement.
-The product has been delivered.
-The price is determinable.
-The seller is reasonably certain of collecting money.
<br>

There is a specific set of rules managing expense recognition. 
Companies cannot decide on their own.
Through the Matching principle companies cannot report on
costs in a future quarter to inflate profit of current quarter. 
<br>

Matching principle states that expenses incurred to generate revenues
are recognized in same period as revenue. 
eg If sales made in 2016, then costs also recorded in 2016
Not all company's expenses can be directly tied to revenues.
Period Costs are expenses in the period when incurred. 
<br>

A Balance Sheet shows what a company owns and 
owes at a specific point in time. 
The Accounting Equation: Assets = Liabilities + Equity
Assets are how the firm used the money it received.
Liabilities and Equity and firms sources of financing. 
Liabilities are external financing.
Equity is own financing. 
<br>

General Ledgers Account is an Account that helps company organize 
the information about a firm's Balance Sheet or Income Statement Items. 
<br>

Assets => PP&E(Property, plant, and equipment), 
          Inventory, Receivables, Cash
<br>

A General Ledger might have subsidiary ledgers,
which contain specific details of those accounts. 
The amount that each customer owes. 
General Ledger: 
Accounts Receivables => Receivables from company A, 
                        Receivables from company B, 
Inventory => Raw Materials, Work-In-Progress,
             Finished Goods
<br>

T-Accounts are one of the most important tools accountants use
when registering a transaction.
<br>

          T-Account
   (increases)|(decreases)

T-Account Tittle can be eg Inventory, Accounts Payable, Revenue
Left side will be information on increases
Right side will be information on decreases
T-Accounts are helpful because they all to 
visualize transactions easier.
<br>

Balance Sheet is essentially a big T-Account
<br>

		        Balance Sheet
	   Assets 		  |	 Liabilities & Equity 
	                  |
        Cash 	      |		Trade Payables
(increase)|(decrease) |	(decrease)|(increase)
	                  |
      Accounts        |	    Financial 
     Receivable 	  |	   Liabilities
(increase)|(decrease) |	(decrease)|(increase)
	                  |
<br>

Debit means "Left".
Credit means "Right".
Assets increase on the Debit side and 
decrease on the Credit side.
Liabilities increase on the Credit side,
decrease on the Debit side. 
Equity increase on the Credit side,
decrease on the Debit side. 
Debit on Left.
Credit on Right.
<br>

Higher a company's Revenue,
higher its profits and equity.
So Revenue behaves like Liability and Equity.
Credited when increases.(Right)
Debited when decreases.(Left)
Costs behave like Assets.
Debited when increases.(Left)
Credited when decreases.(Right)
Revenues is like future Equity. 
<br>

Double Entry states that
every transaction has equal and opposite effects 
in at-lease two accounts. 
<br>

eg a firm owns only one Asset and is 1mil$. 
   suppose the firm is financed entirely by Equity.
   Meaning Asset Cash T-Account is Debited 1mill$ (Left, Right). 
   L&E Equity T-Account is Credited 1mill$ (Right, Left).
<br>

   Suppose the company buys a property for 1mill$. 
   Asset Real Estate T-Account is Debited 1mill$.
   Asset Cash T-Account is now Credited 1mill$.
<br>

   Firm now receives a cash loan of 500K$.
   Asset Cash T-Account is now Debited 500K$.
   L&E Bank Loans T-Account is now Credited 500K$.
<br>

The Double Entry principal helps satisfy 
the accounting equation at all time. 
<br>

Timing has an effect on Revenue. 
Revenue in P&L vs Money in Bank.
The amount of Revenue on income statement
could be different from amount of cash the firm as received. 
A firm realized revenue when it is realized/earned,
no matter when it receives the actual payment. 
From the moment a firm delivers an actual product or
provides a service it should recognize the sale in its revenues. 
The payment for the product can have a different timing. 
Payment can be made before, at or after the sale of product. 
Revenue is recognized with product is transferred 
or service is rendered. 
<br>

eg a company sells office equipment
   it receives an order for 10K$ from a client firm. 
   And delivers good to customer immediately.
   From this it is certain the firm has received Revenue,
   but not certain received cash or payment.
   Could be before, at or after delivery of goods. 
<br>

   This can be represented in 4 T-Accounts. 
   Assets Cash T-Account (Balance Sheet),
   Incomes Revenue T-Account (Income Statement),
   Assets Trade Receivables (Balance Sheet),
   Liability Prepaid Revenue (Balance Sheet).
   If payment was at delivery,
   Cash is Debited 10K, Revenue is Credited 10K.
   If payment is after 60 days,
   Revenue is credited 10K on day of delivery,
   Trade Receivables is debited 10K on day of delivery,
   and after 60 days when payment is received,
   Cash is debited 10k and Trade Receivables is credited 10K,
   also now showing that payment has been made and 
   that other firm does not owe the company anything.
   If payment is made in advance,
   Cash is Debited 10K,
   Prepaid Revenue is credited for 10K,
   and when goods are delivered,
   Revenue is credited 10K,
   and Prepaid Revenue is debited 10K. 
   Revenue is registered when they are earned or delivered. 
   Cash is before, at or after the recognition of Revenues. 
<br>

Accrual Account ensured that a firm records its economic operation
in the period when they have been carried out. 
There are 4 categories of Accruals.
-Unearned Revenue: Revived payment for goods not delivered to client,
which make it a liability. When delivered is erased from liability. 
-Accrued Revenue: When firm as provided goods but not received payment which reflects in Trade Receivables, 
-Prepaid Expenses: Expenses paid ahead of time, 
 eg office rent for 6 months where cash is now credited 
    in balance sheet and Prepaid Expended is debited in BS as Asset. 
-Accrued Expenses: Are expenses incurred but not yet paid. 
 eg sugar for soft drink production is bought but not paid for,
    Accrued Expenses is Credited in BS and 
    Cost of Goods Sold is Debited in Income Statement.
    Later when payment is made, Cash is credited and 
    Accrued Expenses is Credited. 
<br>

Accruals are an accounting entry that is necessary as soon
as product or service is provided, or expenses are incurred,
or cash is exchanged. 
<br>

Profit is not always equal to cash as
Revenue is registered as soon as service is provided,
but Payments could not yet be received. 
This means a business could run out of cash.
eg Company has Net Income of 1mill$, 
   Company owes 500K to bank in 30 days,
   Clients have not paid their bill of 750K,
   Company only has 300K in its bank account. 
   This is a profitable business with Liquidity issues,
   and if unable to pay debt on time makes company Insolvent. 
<br>

Cash Flow generation and liquidity are vital to all businesses.
A company must be able to measure the actual amount of money
it makes and estimate its future capital needs. 
Cash Flow statement identifies how much 
cash is coming in and going out and points out
where it is generated or spent. 
<br>

Cash Flow statement indicates whether enough cash is made 
to service existing debt. Shows the amount of money invested.
And shows if firm can invest in new opportunities when they arise.
<br>

Cash flow changes deriving from Income Statement 
can be considered as operating. 
There are three types of Cash Flows. 
-Operations: cash transactions affecting Net Income
-Investing Activities: investments in Fixed Assets 
  and Other Long-term Investments. 
-Financing Activities: cash transactions affecting 
  firm's capital structure (debt and equity). 
<br>

A company's operating activities may generate cash,
but may pay too much for interest expenses from debt.
<br>

The 3 Cash Flows make up the Net Cash Flow
Beginning Cash Balance + Net Cash Flow = Ending Cash Balance
Ending Cash Balance - Beginning Cash Balance = Net Cash Flow
That is current period - previous period. 
<br>

The Direct Cash Flow Method shows all cash payments that firm
has made throughout a given period (Cash Accounting).
If all transaction are recognized when cash is paid,
then Net Income would be equal to firm's actual Cash Flow. 
The difference between Net Income and Cash Flow is due to 
the accrual principle. Revenue is recognized when it is earned,
not collected. Costs are recognized when incurred not payed. 
<br>

Under the Direct Method
Cash received from customers + Cash paid to suppliers +
Cash paid for operating expenses + Cash paid for interest expenses +
Cash paid for taxes = Cash from Operating Activities
Cash Expenditure + ... = Cash from Investing Activities 
Payments on long term debt + ... = Cash from Financing Activities
<br>

Almost all companies use the Indirect Method.
<br>

Under the Indirect Method, Net Income is converted in cash flow
by making adjustments for transactions that have impact on 
Net income, but do not have an immediate cash effect. 
Elimination of non-cash expenses.
Changes in Balance Sheet accounts deriving from the
application of Accrual Accounting. 
Starting point is either Net Income or EBITDA. 
Some firms categorize Prepaid Expenses as Other Assets
<br>

Indirect Cash Flow Calculation
EBITDA - Interest Expenses - Taxes 
+/- Change in Accounts Receivable
+/- Change in Inventory
+/- Change in Trade Payable
+/- Change in Other Assets
+/- Change in Other Liabilities
= Operating Cash Flow
Investments in financial instruments 
or subsidiary companies and Capex investments 
= Cash Flow from Investing Activities. 
Cash received from Issuing Stock + 
Cash Flow from Repayment of Debt +
Cash Flow from payment of Dividends 
= Cash Flow from Financing Activities 
<br>

Interest Expenses from debt are part of Operating Activities. 
<br>

Cash Flow from Operations +
Cash Flow from Investing Activities +
Cash Flow from Financing Activities = Net Cash Flow
<br>

D&A is omitted as it is a non cash expense.
<br>

If Asset increased there was a Cash outflow,
that is paid in order to buy Asset.
If Asset decreased there was a Cash inflow,
that is received money from selling asset. 
<br>

If Liability increased there was Cash inflow,
that is received financing.
If Liability decreased there was Cash outflow,
that is repaid debt. 
<br>

CAPEX is Capital Expenditure,
eg money spent on Property, Plant and Equipment. 
<br>

Assets Trade Receivables are payments owed by Clients,
for goods or services provided. 
Trade Receivables are a significant investment for companies. 
Clients who purchase continuously will always owe the company money. 
More Sales means more Receivables, 
Selling mostly on Credit means even higher Receivables. 
It is important to think about 
the period of credit given to customers. 
If a company does a poor job of collecting its receivables,
then they will continue to grow. 
<br>

Usually there will be an interest on Accounts Receivables 
of +2% interest for each week of delay in payment. 
If Company fails to pay and is bankrupt,
the services of a debt collector will be used,
but usually the amount just becomes irrecoverable. 
This is shown by crediting Trade Receivables with 
same amount that was initially debited. 
<br>

Revenues - Irrecoverable Debt = Net Sales
Net Sales - Cogs = Gross Profit
<br>

Some Companies make an allowance for bad receivables. 
Usually around 1% of Revenue,
that is a charge of an expense in the current year.
Subtracted from Debited section of Trade Receivables T-Account.
<br>

Companies are recommended to use predictive analytics 
to not do business with unreliable Clients,
and use the services of Debt Collectors who
might have better results in debt collection,
and get paid by their success. 
<br>

Companies are encourages to offer Pay Early Discounts,
to Free Up Capital, like 2% discount.
This would also help the company if it is running out of cash. 
Can be done straight as discount, 
or as a credit note. 
Credit Note can be paid in Cash or 
Compensated against future receivables. 
<br>

Inventory is the portion of Assets 
that are or will be ready to be Sold. 
It determines the speed at which Clients can receive the order. 
Too much inventory can take up space and be expensive. 
A Merchandiser, Wholesaler and Retailer
will only have finished goods. 
Manufacturing Companies will have either
Raw Materials, Work-In-Progress Goods,
and Finished Goods. 
Service based companies like facebook or FedEx
have No Inventory, and such Account would not exist on their BS. 
<br>

Inventory is most related, to COGS. 
COGS = Beginning Inventory + Purchases - Ending Inventory
Ending Inventory = Beginning Inventory + Purchases - COGS
<br>

Inventory can have Product Costs involve Period Costs.
Product Costs =
(Purchase Costs - Trade Discounts - Rebates) +
(Personnel Costs) + (Overhead Expenses like Rent and Electricity ) +
(Other Costs like bringing products to a location)
Period Costs =
(Expenses Related to Abnormal Waste of Material) +
(Storage Costs) + (Admin Costs) + (Selling Expenses)
Period Costs are expensed when incurred and
not directly related to a batch of products currently being sold. 
<br>

Purchasing prices change over time like
Price of Raw Materials, Labor and Other Costs.
<br>

Cost Flow Method is the mechanism used 
to decide the cost of products a firm sells
as it constantly changes. 
By IFRS there is 
- Specific Identification: consists of matching each unit sold,
   with its actual price. Method appropriate for businesses
   where products are not interchangeable. 
- First-in, First-out (FIFO): where the first item purchased 
   is first item sold. 
- Weighted Average Cost: where 
   Weighted Average Cost = 
    (Total Cost of Goods Available for Sale) /
    (Quantity Available For Sale)
    = Unitary COGS
    A value between FIFO and LIFO
- Last-in, First-out (US GAAP has also this 4th method) (LIFO):
   With LIFO Cogs reflects the latest market price available. 
<br>

The three components of working capital are 
Receivables, Inventory and Trade Payables.
<br>


Fixed Assets or Long Lived Assets can be
Tangible Assets(Physical), Intangible Assets(non Physical),
and Financial Assets(Shares of subsidiaries or other shares held).
Financial Assets is usually not a part of Operating Activities. 
<br>

Expenditure on Tangible or Intangible Assets can be
Capitalized or Expensed. 
Costs related to the building up of the Asset or its creation,
should be capitalized and therefore Depreciated or Amortized 
over multiple years. Costs related to Insurance and Maintenance 
can be considered Period Costs and so expensed when incurred.
<br>

There are different implications to Capitalizing vs Expensing. 
When we capitalize the costs we sustain for an Asset,
we are moving these expenses to the Balance Sheet, 
so Assets increase and Net Income for current year will be higher. 
If an Asset is capitalized, its deduction as an expense is postponed,
and therefore higher taxes are paid on corporate income. 
Lower D&A means Higher Taxes. 
If a company prefers to capitalize costs it is 
trying to look more profitable, expecially listed companies. 
If a firm tries to expense the entire account,
then it means it is interested in paying lower income taxes. 
<br>

According to IFRS and US GAAP, 
Interest Expenses can be Capitalized,
which is related to financing obtained 
in-order to bring the Asset to its final condition. 
<br>

Interest Expenses that have been capitalized are not seen
in the firms interest expenses. 
But are depreciated over multiple years,
with the rest of the cost sustained for the Asset. 
<br>

eg If a company borrowed from a bank 100mil$
   in order to build a new production plant. 
   And while constructing the bank it sustained another
   25mill$ in interest expenses. 
   Then once production plant has been completed,
   the firm will be able to capitalize 125mil$ on its BS. 
   If the Plant has a useful life of 10 years,
   the company will start Depreciating 12.5mill$ per year. 
   That is Annual Depreciation is 12.5mill$.
   Interest Expenses are depreciated with rest of costs 
   sustained for the construction of the Plant. 
<br>

Most jurisdictions allow companies to choose how to record assets
on their Balance Sheet, that is historical value or market value. 
eg building bought 20 years ago at 5mill or current value 35mill.
However once method has been chosen, must apply to all assets 
in same category. 
Usually companies hire an appraisal expert to assign 
assets a Fair Value by looking at comparable transaction on market.
Fair Value Accounting cannot be used for all types of Assets. 
It is mostly used fro Real Estate, Brand Value, Trademarks, 
Other Fixed and Intangible Assets, Debts, Pensions, etc.
<br>

Intangible Assets can have a Finite Life or an Infinite Life.
Software Licences, Concessions, Sports Contracts have Finite Life. 
Brand Names, Logos, Websites have an Infinite Life. 
If Intangible Assets have a Finite Life then Costs for Assets
will be Amortized in X Years. If Infinite Life then Costs for Assets
do not Amortize and is instead Tested for Impairment, that is a 
test for if Asset Value decreased or not. 
If the Current Market Value for a Brand is Less than 
its Balance Sheet Amount, there is an Impairment and P&L Loss. 
If actual Current Market Value is less than Balance Sheet Amount,
but through biased testing shows opposite, the loses can build up
until financially the Company goes Bankrupt and hurts all investors. 
Impairment Tests are very Important in critical situations. 
<br>

There is Fair Value Accounting and Account At Cost. 
US GAAP does not allow Fair Value Accounting while IFRS does. 
In IFRS, Companies can choose to opt for Fair Value Accounting 
for their Fixed Assets when there is a clear market for these Assets
and a Valuation Exercise can be carried out. 
If companies choose to use Fair Value Accounting they have 
to apply Revaluation Model. Which consists in appraising the asset 
periodically, usually an annual basis. 
An Appraiser asses and assigns the value. 
The few scenarios are that
-Market Value is greater than Current Carrying Value:
  Here the Fixed Asset value is adjusted on the Balance Sheet. 
  A gain is not reported on P&L. 
  The gain is registered in Equity,
  which is the account tied to Net Income. 
  The rational behind this is to not inflate the firms earnings,
  for an Asset that hasn't even been sold yet. 
  Just that there is a higher ownership claim 
  because asset has appreciated in Value. 
-Market Value is less than the Carrying Value:
  Here the Fixed Asset value is adjusted on Balance Sheet.
  A loss is reported on P&L,
  and Equity is updated to reflect this lower Asset Value. 
  If later on there is an increase in Market Value,
  then P&L Gain can be reported,
  and then Fixed Asset and Equity rise is recorded.
<br>

eg Company X owns a real estate building.
   Depreciation Rate is 0%.
   Carrying Amount is 15mill.
   2 years later in 2017, the building is valued at 17mill.
   P&L statement will not report a profit.
   The Balance Sheet will be updated with Assets now at 17mill.
   Other Comprehensive Income will be given 2mill.
   In 2018 the building is now worth 13mill.
   The Balance Sheet will be updated with Assets now at 13mill.
   P&L will report a loss of 4mill.
   Which means Net Income will be 4mill lower.
   In 2019 the building is now worth 14mill.
   The 1mill will be recognized as profit in P&L.
   Building Asset now at 14mill.
<br>

eg Company X acquires a Tangible Asset for 25K in Beginning 2017.
   The Tangible Asset has a 5 year Useful Life. 
   2 Years later in 2019, the Asset is revalued at 12.5K
   1 Year after in 22020, the Asset is revalued to 12K
   25K/5Years = 5K is Amortized per year. 
   Year 1 end its 20K and Year 2 it's 15K. 
   This means the 15K Carrying Value is Less than
   the 12.5K Fair Value, which makes it 
   a Downward Revaluation of 2.5K. 
   To reflect in Balance Sheet 
   first Accumulated Depreciation is Debited 10K
   and Asset is Credited 10K.
   Revaluation Loss is Debited 2.5K
   and Asset is Credited further 2.5K
   New Depreciation Expense is calculated.
   12.5K/3Years = 4.166K
   This makes Year 3 Carrying Value 8.334K.
   But now in Year 3, the Fair Value is 12K,
   greater than the Carrying Value of 8.334K,
   meaning an Upward Revaluation. 
   Previously a Revaluation loss of 2.5K was registered in P&L.
   The Revaluation Gain this time is 3.666K.
   Only 2.5K can be reported in P&L as that 
   was previous reported loss. 
   The rest of 1.166K will be reported to 
   OCI (Other Comprehensible Income). 
   First in Balance Sheet we Credit 4.166K for Building Assets.
   Accumulated Depreciation is Debited 4.166K.
   Then 3.666K is Debited in Building Assets, 
   2.5K is Credited in Revaluation Gain (P&L),
   and 1.166K is Credited in Revaluation Surplus (BS)
<br>

For Tangible Assets created Internally
we Capitalize all Costs necessary
for the Production and Transformation of the Asset.
Other Costs related to maintenance are expensed directly. 
<br>

For Intangible Assets created Internally,
most Cost is expensed immediately. 
Building an Intangible asset can be divided into
Research and Development. 
Under IFRS, 
Research is Expensed,
and Development is Capitalized. 
Under US GAAP,
Research and Development are Expensed,
as US GAAP does not allow 
the capitalization of cost under both phases,
and all costs must be expensed when incurred. 
Both IFRS and US GAAP
allow the Capitalization of costs when
Technological Feasibility has been established. 
US GAAP allows the Capitalization of cost
only if the product is for internal use only,
not to be sold to third parties. 
<br>

The primary difference between capitalizing and expensing costs 
is that you record capitalized costs on a balance sheet, 
and you record expensed costs on an income statement or 
statement of cash flows. Capitalized costs also display 
as investing cash outflow, while expensed costs display 
as operating cash outflow.
<br>

Trade Payables under Liability is
the money owed to suppliers 
for purchases made 
and not yet paid. 
This is a short term debt representing a liability,
Current Liability.
Typically Trade Payables are paid in 180 days or less. 
But in reality most Venders would not cross the 30 day mark.
Typically companies try to balance 
Trade Receivables and Trade Payables.
Suppliers are cautious when selling on Credit,
and it generally goes the way of whomever has stronger leverage. 
That is Bargaining Power and Availability of Alternatives. 
Important to be weary of interest charges. 
<br>

Accounts Payables and Notes Payable have a subtle difference.
Both items represent a liability owed to a third-party vendor.
Accounts Payable is registered 
when company calls a supplier 
and orders the delivery of a product. 
Once product is delivered a Delivery Receipt is signed. 
An Invoice will state that there are 30 days to make payment.
If the companies sign a contract of amount due and by date,
the amount is registered in Notes Payable. 
Both Accounts Payable and Notes Payable 
are grouped under Trade Payable T-Account under Liability. 
Notes Payable is much more easily enforceable.
<br>

Entirely digitizing the process of sending out 
Invoices and tracking all Invoices has (E-Invoicing)
led to major efficiencies in companies,
and majority of Invoices being paid on time. 
<br>

Process automation systems 
allow companies to achieve
significant efficiencies. 

<br>

Generally there are two types of financing.
Shareholders Money(own) and Third-Party Financing(Liabilities). 
If the Liabilities are interest bearing then
they are considered Financial Liabilities. 
Debt and Equity are different. 
Interest Expenses arising from Debt 
can reduce Net Income. 
Dividend payments to Shareholders 
are the distribution of Earnings 
and have no impact on P&L.
If a financing instrument 
contains an obligation to 
repay money in the future then it is Debt Financing. 
If money is being raised,
and there is no promise of repaying money in future,
but a promise to share firms earnings then it is Equity Financing. 
<br>

Convertible Bonds have the charecteristics
of both Debt and Equity. 
They have the option to be converted to Equity Shares,
but are interest bearing and certain amount is owed 
at maturity if the Bond is not converted. 
<br>

Financial Liabilities are recorded on Balance Sheet
using the Amortized Cost Method. 
This involves measuring Financial Liabilities at Fair Value,
and any transaction costs deriving from the transaction.
Loan and Transaction Costs associated with the Loan 
are put together in Financial Liabilities.
Loans are amortized according to agreed schedule.
<br>

eg If a company takes out a Loan for 400K with fixed interest 8%.
   And Annual Payment is 60K.
   In current year the Firm owes the bank 60K.
   Interest Expense at 32K charged as P&L expense. 
   Which makes the Principal Payment 28K.
   And the Ending Load at Year 1 372K.
   In year 2, the Interest Expense is not 29.8K.
   And the Principal Payment at 30K.
   And the Ending Load at Year 2 at 341.8K.
<br>

Sometimes Financiers want to be able to predetermine
how borrowers would act. 
Which means lower risk and higher changes of getting repaid. 
The contractual mechanism that ensures certain behaviour
by borrowers are called Debt Covenants. 
There are three types of Debt Covenants 
that financiers can enforce on borrowers.
Positive, Negative and Financial. 
Positive Covenants consist of actions the borrower has to do. 
eg Can require borrower to source its supplies 
   from at-least three different suppliers. 
Negative Covenants prohibit the borrowers from certain actions. 
eg The borrower is not allowed to distribute as Dividends 
   more than 50% of Net Income. 
Financial Covenants determine 
a specific financial condition to be satisfied. 
<br>

eg A firm cant have an Interest Coverage Ratio below 15,
   or a company's quick ratio has to be more than 1.5.
   And penalties follow is borrower is not compliant,
   like pay additional interest expenses,
   or even repay a big part of their loan. 
Lenders are concerned about Solvency.
Shareholders are concerned about Profits. 
Covenants are the tools that allow lenders
to define the games rules. 
The less covenants there are the better for a company. 
<br>

An example of a well thought out debt covenants
eg Company A acquired Company B, a foreign competitor. 
   The merger of the two companies 
   produced a combined entity
   with a risk profile greater than 
   Company A's stand alone Risk. 
   Usually a greater risk profile leads to lower Bond Prices. 
   And at that time they were even trading below market value.
   Investors who wanted to exit their investment 
   before the merger would have sustained heavy loses. 
   However the merger of the two companies 
   triggered a Change of Control clause 
   in the Bond Contract. 
   Giving Bong Holders the right and not obligation
   to sell back their bonds to the company,
   if the change of control occurs. 
   Change of ownership is the definition of control. 
   Giving investors the option to sell their bond back to company. 
   And if they did it would have been at 101% of bond values.
   This Change of Control Covenant protected the Bond Investors.
<br>

Leasing is an alternate form of finance with several advantages.
-Downpayment is not required. 
 Meaning the acquirer can have the Asset without making 
 a substantial investment and blocking a significant amount of cash.
-If technology changes rapidly the company would be less exposed. 
-Can be kept off the Balance Sheet 
 when the Leasing is registered as an Operating Lease(OPEX).
 The firm registers an expense in its P&L,
 and has no Financial Liabilities on its Balance Sheet,
 which is advantages to Debt and Interest Ratios 
 monitored by Banks. 
-Are Tax deductible. 
<br>

Leasing Case Study:
Company XYZ Leases an Asset.
Useful Life of 5 Years and Lease Period of 5 Years.
Asset will be returned to Lessor at end of Leasing Period. 
Annual Rent is 14K, Residual Value 0,
Fair Value is 50K and Interest Rate 8%. 
This is a Finance Lease as the Company Leases the Asset
for the rest of its Expected Useful Life.
On Balance Sheet, Leased Asset is Debited 50K,
and Leasing Liability is Credited 50K.
Using Straight Line Depreciation,
50K/5Y is 10K Annual Depreciation.
The Account entry would be Debit D&A (P&L) for 10K,
and Credit Accumulated Depreciation (BS) for 10K.
Year 1, Starting 50K, Interest 4K, Rental 14K and Ending 40K.
Interest Expenses are debited 4K and 
Liabilities Against Lessor are credited 4K.
The Carrying Value of the Asset at End of Year 1 and 
the Lease Liability at End of Year 1 is 40K.
<br>

Companies like external financing. 
Allowing scaling of operations significantly. 
Can be be 4-5x the 1x Equity invested in a project.
Most investors like larger projects 
because they usually lead to a higher reward,
allowing a number of economies of scale and scope to be realized. 
Companies like it because if things go well they go really well,
and if not the risk was shared wit external investors.
<br>

eg a 15mil equality invested project yielding 3mill,
   meaning 20% return.
   vs 
   a 5mill equity and 10mill debt invested project,
   yielding 3mill profit minus 1mill interest,
   leaving 2mill profit or 40% return. 
<br>

Generally Highly Leveraged Business has High Upside,
and is preferred by aggressive investors. 
In most jurisdictions Interest Expenses are tax deductible. 
And is another reason profitable businesses prefer debt financing. 
Investors must feel safe with an investment,
and usually accept even higher risk than usual 
for real estate projects with belief they are stable over time. 
In tech businesses creditors are much less willing 
to offer a low cost of debt and significant amount of money.
Tech companies usually have 0 or very little debt on a balance sheet.
Tech companies rarely use leverage 
and are usually entirely financed with equity. 
<br>

The more Debt a company has on its balance sheet,
the more riskier it is perceived by creditors. 
Creditors look for few things that can guarantee repayment of loan,
the borrower company's Operating Cash Flows, its profitability 
and the borrower company's assets. 
If a firm goes bankrupt the guarantee from its 
Operating Cash Flows are useless. 
Assets tend to be sold at a much lower price when a company defaults,
and some can not even be sold. 
In these cases Equity owners are the first to sustain losses.
The more Debt a company has and the lower its Equity is,
the higher the chases of Debt holder loosing significant amounts,
when a default occurs. 
When Banks expect to sustain losses 
they will raise the Cost of Debt.
<br>

Firms of a similar size,
operating in the same industry,
should have a cost of debt corresponding to their leverage. 
Changes to Cost of Debt can be compared and measured using 
different companies Financial Debt to Liabilities and Equity ratio.
Cost of Debt curve for each industry can be made using this method. 
<br>

Cost of Debt = Interest Expenses / Financial Liabilities
alternatively the yield of a firm's 5-10 year bond can be seen. 

<br>

Retained Earnings are Profits that have not been 
redistributed to shareholders.
Usually kept for reinvestment. 
Both Accumulated Losses (Startups) and
High Retained Earnings (Large Firms) are 
shown within Retained Equity. 
Can receive Tax Exemptions for Accumulated Losses
if it is greater than Rest of Equity Accounts and
can say company is in Technical Default and 
needs to be refinanced by shareholders or will become bankrupt. 
<br>

Treasury Stock is the firm's own stock repurchased from 
Investors and not yet retired. 
This account is shown in negative 
because it reduces stock holders equity. 
<br>

Outstanding Shares =
  Number of Shares Issued
- Number of Shares Reacquired 
<br>

Shareholders Equity is a measure relating 
to the number of shares outstanding. 
<br>

Non-Controlling Interest is a minority shareholder's 
Pro-Rate Ownership of a firm's equity. 
eg Company A owns 80% of Company X.
   When Company A has to prepare a consolidated financial statement,
   including Company X's Assets and Liabilities,
   it will have to show in it's Balance Sheet that it owns only 
   80% of Company X. 
   In practice Company A will show 100% of Company X's Assets
   and Liabilities. And then will also report in its Equity,
   that External Owners have a 20% stake in Company X. 
<br>

Other Comprehensive Income contains Revenues, Costs and other Gains
and Losses that are excluded from Net Income 
according to US GAAP or IFRS. 
Examples of items that will go here are 
-Reversal Gains: deriving from revaluation of Brands or other Assets.
  Can not be shown as this years Profit in the Income Statement. 
  But they still have to go to Equity for the BS to Balance,
  which is why it is included in other comprehensive income. 
<br>

Bootstrapping is Founders of Startups relying on no external funding
and mostly their own Savings. Later Startups receive funds 
from Venture Capital Funds and Business Angels. 
<br>

Venture Capitals are Investment Vehicles that collect money from 
Institutional Investors providing seed and second stage financing
to a number of new or small businesses. 
A few companies will compensate 
for the great number of companies that will fail. 
Business Angels are wealthy private individuals 
who have a similar mindset Venture Capital Funds.
They sometimes also provide mentorship. 
Alternatively companies are able to raise Equity 
if they are Profitable. 
But it is not optimal to wait and 
refinance business with own profits.
Especially early stages when startups needs to grow fast 
and outpace competitors. 
At these stages it is hard to secure Debt financing
as new Businesses have very literal collateral.
With New Equity Investment being the best option. 
Private Equity Funds are larger than Venture Capital Funds. 
Private Equity investors are able to invest a greater amount of money,
and interested in a larger ownership stake. 10-20% vs 30-100%. 
Their Goal is to enter and exit an investment in a 5 year time frame. 
A company that is going public will have to 
increase its administrative and finance staff significantly. 
And prepare an number of financial documents 
not required for private firms. 
<br>

After an IPO there are other ways to raise Equity Cash. 
One way is an SEO (Seasoned Equity Offering).
They are similar to IPOs but much simpler 
as most documentation has already been filed during IPO. 
Valuations are also easier as is already valued by market. 
Another type of Equity post IPO are Private Placements which are 
offerings that are exempt from a large part of the registration 
procedures necessary for an IPO. They are usually offered to 
Institutional Investors who are 
more sophisticated than retail investors and need less documentation
in order to make an informed decision and 
is the quickest way to make capital. 
<br>

Between 2007 and 2017 the S&P 500 outperformed most Hedge Funds.
Berkshire Hathaway outperformed the S&P 500,
but factoring Dividends the S&P 500 reigned supreme. 
<br>

Dividends and Share repurchase are main methods of transferring cash
from company to shareholders. 
Types of Dividends are
-Regular Dividends: periodic payments quarterly or annual.
  Usually adopted by mature companies with stable cash flows.
  Once a pattern of regular dividends is established 
  but then interrupted, the stock will react negatively. 
-Special Dividends: extraordinary dividends paid to shareholders.
  For when business environment is favourable and circumstances 
  allow for an extra payment. 
-Stock Dividends: Not very popular as they dilute a 
  company's ownership issuing new shares 
  and give these shares to existing shareholder
  who end up with same percentage ownership of firm. 
-Liquidating Dividends: Dividends paid at a time when firm ceases
  to exist. Shareholders are entitled to the value of a firms Assets.
<br>

Conceptually when a company pays a cash dividend to its shareholders,
its assets decrease, as Cash is an Asset. Liabilities are unaffected.
So Equity as decreases. Retained earnings represent profits not 
distributed to shareholders. But some will be distributed now,
So the accounting entry would be 
Credit Cash within Assets and 
Debit Retained Earnings within Equity. 
The share price of a stock has to decrease once decrease in Equity
has be taken into consideration. 
eg 50$ per share before Dividend 
   01$ is Dividend
   49$ per share after Divided.
   First there is a Declaration Date,
    A press release that board has approved a payment of 1$.
   Then an Ex-Divided Date which is first day the Stock's Shares,
    reflect the new price of Stock.
   In most days the Ex-Dividend date is 2 days before 
    Holders of Record Date, which is date all shareholders on record,
    receive the Divided. And any investor who buys shares after 
    the record date wont receive the Dividend. Because the owner
    of the stock before him would be the one presumed to have
    received the dividend. 
   The Payment Date the date shareholders receive 
   the check or wire transfer.
<br>

Buying Back Shares can be through Tender Offer of 
'We want to buy shares'
or Private Negotiation or buying Shares on Open Market,
which gives most flexibility on quantity or timing.
Share repurchases can be a signal to the entire market. 
Company can be signalling that their shares are undervalued,
and share prices will likely increase for shareholders
willing to stay with the company long term.
And the shareholders earnings per share 
and dividend might increase too. 
The possible downsides can be signalling of
a lack of investment opportunities, 
and so share prices could go down 
and therefore the overall market cap.
Share repurchasing dries up companies cash reserves.
It is important to use it at the right time.
<br>

Cash flows should be unaffected by stock splits,
and overall market cap will be same as before.
Some Companies prefer to have their stock price 
float between 20-80$ as it is perceived as optimal. 
It can also be seen as a high signal 
for future high expected increase of earnings. 
Stock splits are usually a precursor, to high earnings announcement.
And if their earnings announcement is not as strong as expected,
it reverts back to previous level. 
A lower price for stock can also lead to higher brokerage fees,
given that stock brokers charge more fees for lower price stock.
<br>


Financial Statements show the development of a company's
business throughout the preceding period (quarter, semester or a year)
Larger Firms have to provide a greater level of detail
due to complexity of their operations. 
Financial Statement contains
- Balance Sheet
- Income statement
- Cash Flow
- Management Discussion
- Footnotes (A breakdown of important items in B.S. and I.S.)
   Footnotes can be useful as they allow us to understand what
   stands behind aggregated figures. 
<br>

Smaller companies provide Financial Statements only once a year
while Listed firms have to provide a financial report every 3 months. 
In the United States the Annual report required by the 
Securities and Exchange Commission is called Form 10-K.
Form 10-K report is prepared once per year and shows 
how the firm performed during the past 12 months.
Also includes the history, organization structure, 
executive compensation, equity, and subsidiaries. 
Some companies include their 10-K report within their annual report. 
<br>

eg P&G annual report:
Document stats with Table of Contents. 
Financial Highlights below Table of Contents,
showing breakdown of Sales by Business Segment, Geographic Region,
and Market Maturity. 
Then Letter from Company CEO and Chairman,
explaining the developments related to P&G business,
company's strategic positioning, and other important topics related 
to what company does and what it hopes to achieve in future. 
The next few pages contain information about 
P&G's Operating Segments and Brands.
Such information is not compulsory 
but some companies prefer to share it with investors,
in order to facilitate their understanding of the business. 
Scrolling down you will find the 10-K report. 
<br>

10-K reports have a predetermined structure. 
Report consists of 4 main parts. 
<br>

Part I describes the company's business 
 and some potential risks it might face. 
 Provides information about firm's operating segments, 
 key product categories, key customers, number of employees, 
 business model and more. Useful information to 
 learn more about a business. 
<br>

Part II provides information about 
 the stock market performance of company,
 the dividends it paid, its high and low price,
 and comparison with rest of market. 
 The S&P 500 approximates the rest of the market. 
 Scrolling down will be the Management's view on the business,
 along with companies operational structure, business units,
 recent developments that might have influenced its business,
 and expectation about the future. 
Report of independent accounting firm can be found on the 10-K report
that verifies the quality of the companies financial statements.
Income Statement is shown comparatively for 3 year period,
allowing for comparison of current period with previous 2 periods. 
After P&L statement will be Company's Balance Sheet,
showing Assets are equal to Liabilities and Equity. 
Statement of Shareholders Equity shows 
changes in a company's equity in a very detailed way. 
Cash flow statement gives an idea of the 
cash flow generated by the business. 
Investors are more interested in Cash Flow than Income,
as it gives an immediate idea, of the health of company's business. 
Net Income can be influenced by a number of non cash items. 
Next few pages will be notes to financial statements.
Explanations, descriptions and breakdowns of large accounts from 
main Financial Statements. The notes for Intangible Assets shows
its broken down into Intangible Assets with Determinable Lives
and with Indefinite Lives, and is further broken down.
All Financial Reports of Companies have almost the same structure. 
<br>

Financial Department is responsible for 
preparing Financial Statements.
Financial Statements are prepared according to 
a specific set of rules, local accounting principles
or international accounting standards. 
Investors take comfort from independent assurance.
Audits provide assurance that management has presented
a true and fair view of company's 
financial performance and position. 
The owners of a company, its shareholders,
are not the ones managing the company,
and is why they need auditor's assurance services.
Auditing is when an External Party or Auditor is engaged to examine
the Financial Statements including related disclosures by management. 
Required by law and all Financial Statements include a note 
from Auditor which certifies or doesn't the credibility of figures
within the report. 
The Big 4 Accounting Firms are KPMG, PWC, EY and Deloitte.
<br>

A subtotal is the sum of two or more items. 
Usually summed because they belong to the same category.
Subtotal is summed with other Subtotals and we arrive at total. 
<br>

eg 
Intangible assets + PP&E + Financial Assets = Fixed Assets Subtotal
Inventory + Trade Receivables + Other Assets + Cash and Equivalents
=Non Fixed Assets Subtotal
Fixed Assets Subtotal + Non Fixed Assets Subtotal 
= Total Assets Subtotal
<br>

Year on Year Growth % = (((Value in X + 1) / (Value in X)) - 1)
<br>

There are three main Financial Statements:
Balance Sheet, Income Statement and Cash Flow. 
The Accounting Equation is Assets = Liabilities + Equity.
General Ledger is used to record all of a company's transactions
and its data is used to make Financial Statements.
Double Entry states that every financial transaction has equal and opposite effects in at least two different accounts.
Revenue and Costs (or Expense Recognition) 
are recorded at different times 
depending on when actual cash payments comes in. 
<br>

Financial Statement Analysis is a continuation of Accounting
that uses financial figures in order to provide some less obvious insights into the company's business. 
After the creation of Balance Sheet and Income Statement,
Financial Statement Analysis can be done.
It's main purpose is the assessment of the performance and soundness
of 4 critical dimensions:
-Growth (is company growing?)
-Liquidity (does company have sufficient liquidity in order to 
  repay its short term liabilities?)
-Profitability (is the profit that is being earned satisfactory?)
-Solvency (is the company able to face its liabilities?)
<br>

A good understanding of financial statements is based on deep
understanding of the typical transactions performed by the company. 
Some companies classify certain transactions as operating, 
while others classify the same transactions as 
financial or non-operating, as the two companies 
have different underlying businesses. 
Financial Statement Analysis is based on comparison,
comparing the same entity over time(growth of revenues, expenses, etc.).
Most investors are focused on company's growth potential. 
Another popular type of comparison is peer comparison,
comparing a company with the rest of the firms in its industry.
-Is the company growing faster?
-Is it able to charge higher prices?
-Does the business have superior profitability relatively?
-Is the business more efficient relatively?
Practitioners use both types of analysis.
<br>

Financial Statement Formats helps us Organize The Items
in a Balance Sheet and P&L.
There is no rule regulating 
how to organize Financial Statement Formats. 
eg 
 Format A: 
  Net Sales + Other Revenues = Total Revenues
  Total Revenues - Cost of Goods Sold = Gross Profit
  G.P. - Operating Expenses - Other Expenses = Net Income
 Format B:
  Net Sales + Other Revenues = Total Revenues
  T.R. - C.O.G.S. - Operating Expenses = Operating Profit (or EBIT)
  Operating Profit - Other Expenses = Net Income
The decision on the P&L format is up to company management
and should be taken in a way 
that best represents the underlying business. 
A popular Balance Sheet format is the one 
grouping Assets and Liabilities according to their maturity,
current and non current. 
Analysts often organize the B.S. they are using by separating 
Operating from Non-Operating Assets and Liabilities. 
There are two main types of Analysis that can be performed. 
-Horizontal Analysis (represents the comparison of historical
  financial information over a series of recording periods.
  To see if any numbers are unusually high or low with respect to 
  the information about previous periods. eg how much total revenue
  increased with respect to figure from a year ago. 
  Horizontal Analysis is also called Trend Analysis.
  As it shows the development of a given parameter over time.)
-Vertical Analysis (involves the same accounting period.
  Each item is divided into a specific base or the 100% figure.
  In the Balance Sheet this is usually the value of Total Assets 
  while in the Income Statement this is the Total Revenues figure. 
  For Year X
   Fixed Assets/Total Assets , Working Capital/Total Assets ,
   Gross Profit/Total Revenues , EBIT/Total Revenues ,
   Net Income/Total Revenues,
  Which allow us to understand what percentage of Assets or Revenues 
  they represent. Then can compare these figures with peers
  or with its historical data. Then make observations that are 
  based on the development of its financials.)
<br>

Days methodology is used to represent some balance sheet items. 
The Days Calculation indicates how many days are necessary 
to cash Trade Receivables or pay Trade Payables or 
that an item leaves a warehouse of the firm. 
Trade Receivables (Generated from selling products on credit)
Trade Payables (Generated by the acquisition of Raw Materials 
 from Suppliers)
Inventory (The amount of goods and finished products 
 held by the company)
DSO or Days Sales Outstanding = (Trade Receivables / Revenue) * 360
DPO or Days Payable Outstanding = (Trade Payables / COGS) * 360
DIO or Days Inventory Outstanding = (Inventory / COGS) * 360
DSO is a measure of the average number of days that a company
takes to collect revenue after a sale has been made. 
A low DSO number means a company needs fewer days 
to collect its Accounts Receivable. 
A high DSO number shows that a firm is selling its products 
to its customers on credit and taking longer to collect money. 
DPO is a company average payable period. 
DPO tells us how long it takes for a company to pay its 
invoices from trade creditors such as suppliers. 
DIO is a financial measure of a company's performance,
that gives investors an idea of how long it takes a company 
to turn its inventory into sales. 
<br>

Financial Ratios key goal is to analyze 4 main dimensions. 
-Liquidity (A firm's capability to pay its short term obligations)
-Solvency (A company's ability to meet its long term obligations)
-Profitability (A firm's ability to generate profits)
-Growth (The speed at which a company's financials are growing)
If a company is liquid it means a significant portion of its assets 
are easily convertible in cash. 
Solvency indicates a company's ability 
to meet its long term obligation.
If a company finances a high portion of its Assets with 
financial debt, then it risks having financial difficulties 
due to increasing interest expenses.
Profitability ratios are important for every company 
as it has to produce sufficient profits
that will satisfy its employees and owners. 
Given there can be several drivers that determine 
whether a company is profitable,
it is common practice to break down some of the profitability ratios
into smaller ingredients. 
Growth ratios provide insights into the speed at which 
a company's Revenues, Margins, Profits and Assets are growing. 
Some ratios used to analyze each dimension:
-Liquidity: Current Ratio , Net Trade Cycle
-Solvency: Debt Ratio , Interest Coverage
-Profitability: ROA , ROE
-Growth: Revenue Growth
<br>

Current Ratio = Short Term Assets / Short Term Liabilities
Gives an idea of company's ability to pay its short term Liabilities. 
The recommended value for this 
depends on the industry in which company operates.
Generally a ratio over 2 is good. 
<br>

Net Trade Cycle = DSO + DIO - DPO
Shows how many days it takes for a company to 
convert resources that it uses in the production of its goods
into cash. Also known as Cash Conversion Cycle. 
Measured the amount of time for which each dollar 
is tied up in the production and sales process before 
it is converted into cash through sales to customers. 
Easy to calculate once DSO , DIO , and DPO are know.
Allows us to understand if firm is efficient in its use of capital. 
And peer comparisons help with that. 
<br>

Debt Ratio also known as Leverage and Interest Coverage Ratio
are the main Solvency Ratios. 
<br>

Debt Ratio = Total Liabilities / Total Assets
Shows what portion of company's Assets 
is financed with Debt. 
The lower this is the more sustainable 
is the business under consideration. 
For many industries a value of up-to 0.67 is acceptable. 
Also compare the ratio with the industry average. 
<br>

Interest Coverage = EBIT / Interest Expenses 
When a company's debt increases 
it has to pay higher interest expenses.
Financial Institutions always want to leave a cushion,
which is why the often measure the proportion 
between a company's operating profits or EBIT
and its Interest Expenses. 
If it is higher than 2 then this means 
that the company will be able to pay its interest expenses 
and will likely be able to repay some of principle too. 
Alternatively a ratio below 1 shows a company is unable to pay 
even its interest expenses 
and will produce losses for its shareholders. 
<br>

ROA = EBIT / Total Assets
ROA is Return On Assets. 
This is an indicator of the profitability of the company 
without considering the way in which its activities were financed.
<br>

ROE = Net Income / Total Equity
ROE stands for Return on Equity. 
Shows how much profit was generated by a company 
with the money that shareholder invested in company's activities.
ROE can be broken down,
ROA is a measure of profitability 
that does not consider financial structure. 
Debt to Equity ratio is an indicator 
of company's financial structure,
showing the relationship between external and owned financing. 
The third ratio incorporates the impact of non operating items,
financial items, taxes and extraordinary items 
on company's profitability. 
ROE = ROA * (Total Assets / Equity) * (Net Income / EBIT)
<br>

Revenue Growth = (Revenue(this year) / Revenue(last year)) - 1
Other Growth Ratios are 
Change of Sales Ratio, Growth in Total Assets, etc. 
Revenue growth indicative of how fast a company is growing,
relative to itself and its peers,
and determine how interesting the business will be to investors. 
<br>

Analyzing P&G's 
Income Statement or Consolidated Statement of Earnings
and Consolidated Balance Sheet-
First the Liquidity Ratios:
 Current Ratio = (Current Assets / Current Liabilities)
  in 2014 was 0.94, and 2015 was 1.00
Second its Net Trading Cycle:
 DSO = (Trade Receivables / Sales (for that year)) * 360
  in 2014 was 28.55 days, and 2015 was 22.94 days
 DIO = (Inventory / COGS (for that year)) * 360
  if COGS is given as negative then will need to make positive.
  in 2014 was 59.33 days, and 2015 was 50.51 days
 DPO = (Accounts Payable / COGS (for that year)) * 360
  in 2014 was 74.27 days, and 2015 was 76.46 days
 Net Trading Cycle = DSO + DIO - DPO
  in 2014 was 13.61, 2015 was -3.01
  Showing that P&G was able to 
  reduce its DSO and DIO figures
  while continuing to pay in more than 70 days to suppliers. 
  Showing that P&G is able to operate its business 
  without significant working capital investments. 
  This is proof of a company's strong bargaining power. 
  It's clients pay in every 3-4 weeks 
  while P&G pays its suppliers in more than 10 weeks. 
Third we calculate company's solvency ratios:
 It's ability to pay long term debt,
 and the interest coverage ratio 
 gives an idea of company's ability to pay interest. 
 Debt Ratio = (Total Liabilities / Total Assets)
  in 2014 was 0.51, and 2015 was 0.51 ,
  shows ratio remained flat in both years,
  and is below the threshold of 0.67 which is good. 
 Interest Ratio = (EBIT / Interest Expenses)
  in 2013 was 23.86 , 2014 was 24.20 , 2015 was 24.82 ,
  shows P&G's Operating Income EBIT 
  was approximately 24 times it's Interest Expenses. 
  This is completely reassuring 
  and shows company will not face solvency issues in near future. 
Fourth we find the Profitability Ratios:
 ROA = EBIT / Total Assets
  in 2014 was 10.2 % , 2015 was 9.1 %
  For a reasonable judgement of if this a good or bad figure,
  we need to consider the average figure for P&G's industry.
  Done by looking at Financial Statements of companies like
  Unilever, Kimberly-Clark, Colegate, Palm Olive ,etc. 
 ROE = Net Income / Equity
  in 2014 was 16.8% , 2015 was 14.2%
 ROE = ROA * (Total Assets / Equity) * (Net Income / EBIT)
 EBIT% = EBIT / Revenues
  in 2013 was 17.2%, 2014 was 18.3%, 2015 was 15.5%
 Net Income% = Net Income / Revenues
  in 2013 was 14.2%, 2014 was 14.6%, 2015 was 11.7%
  Showing P&G was not able to convert 
  as much of its Revenues into Profit as previous periods. 
  15.5% of EBIT% is a good for most industries. 
 Revenue Growth = (Revenue(this year) / Revenue(last year)) - 1
  in 2014 was 0.5% , in 2015 was -5.3%
  shows it grew marginally in 2014 and decreased in 2015.
  Looking at the notes, there is a bullet point note specifying
  that the cause of the decrease was 
  negative impact of foreign exchange.
  Low growth figures shouldn't be surprising for a company of P&G's
  size as double digit growth figures are hard to obtain for its size.
<br>

Financial Statement Analysis is about answering questions like:
 How has a company evolved in recent years?
 What is its current outlook?
 Which are the major line items to be considered?
 Is the company able to make money?
 How Liquid is it at the moment?
 Is there any significant danger of solvency issues in the future?
 What is the ratio between operating income and interest expenses?
<br>

In 2017 the main concern about Tesla 
was that it was not financially stable,
and continues to burn cash. 
Analyzing the company's 
Profitability and growth,
Liquidity, Working Capital, and Solvency
would show what to be expected of the future for Tesla. 
<br>

Can usually download Financial Statements 
on a Company website or the SEC.gov site. 
On the Tesla website would be the quarterly Form 10-Q.
The fourth quarterly statement is the annual 10-K form.
<br>

In corporate finance theory,
we define two drivers of value creation for companies.
A company's future value largely depends on two main variables. 
Profitability and Growth.
Profitability tells us how much Revenue is converted to Profit.
That is what portion of the Revenue Cake goes to Shareholders.
That is same size and stronger conversion ratio.
Growth indicates the year on year change on revenues. 
Whether the cake is expanding or shrinking. 
That is bigger size and same conversion ratio.
There are two ways to create value for shareholders. 
Grow the cake or give them a larger portion of it.
Higher future cash flows means higher valuation. 
<br>

Given Tesla is a still a growing company, 
it is expected to see a strong 
double digit revenue increase,
in all years from 2014 to 2017. 
However the company had some issues with profitability. 
Typical of businesses that are expanding and have not reached 
sufficient scale to cover fixed costs. 
First we measure Growth:
 Growth measure is done by takin one periods value,
 dividing it by previous periods value,
 and subtracting by 1. 
 That is year on year growth in percentage.
 Revenue % automation y-o-y 
   2015 was 24%, 2016 was 70%, 2017 was 52%
 Revenue % generation y-o-y 
   2015 was 244%, 2016 was 1153%, 2017 was 515%
 Revenue % services y-o-y 
   2015 was 55%, 2016 was 61%, 2017 was 114%
 In situations like this one when we analyze 
 a company that has more than one business line,
 it is highly recommended to provide 
 y-o-y growth of all three business lines,
 especially if they contribute to Revenue in a materialistic way.
 The results show Tesla has been experiencing 
 strong double digit growth for several years now. 
 All three business lines are expanding rapidly. 
 We should bare in mind that the sharp increase 
 of generation revenues of 2016 and 2017 was 
 significantly influenced by the merger with Solar City. 
 Nonetheless Tesla's revenue growth has been outstanding
 for the timeframe under analysis. 
Second we measure the Profitability:
 Gross Profit Margin (for that year) 
 = (Revenue (for that year) +- COGS (for that year)) 
   / Revenue (for that year)
 To tell us what portion of revenue 
 has been converted to Gross Profit.
 GP% automotive
   2014 was 29%, 2015 was 25%, 2016 was 25%, 2017 was 23%
 GP% energy generation and automotive
   2014 was 05%, 2015 was 15%, 2016 was 02%, 2017 was 22%
 GP% services and other
   2014 was 11%, 2015 was 01%, 2016 was -01%, 2017 was -23%
 Shows that the most stable was automotive,
 Q1 2018 GP% automotive was 20% which is a decline,
 and is probably related to the introduction on Model 3.
 In 2017 and first half of 2018 Tesla was struggling to produce
 the model 3 at scale but still sustained expenses related to
 increased production personnel. Now that production targets
 for model 3 have been met, there will be an expected
 improved GP margin in second half of 2018. 
 The energy generation and services businesses 
 are in their infancy and have a very low gross profit margin. 
 This is a bit concerning as problems at this level
 means that Tesla is selling certain services at a loss. 
 Services and others is a definite business flag.
 Overall GP% = GP / Revenue
   2014 was 28%, 2015 was 23%, 2016 was 23%, 2017 was 19%
 The overall GP% is low because of the other two business lines. 
 Gross Profit takes into consideration the cost of revenues
 but not Operating Expenses such as R&D, 
 SG&A (Selling, General, and Administrative),
 Restructuring and other. 
 The EBIT margin will help us see 
 the company's operating profitability
 including operating costs.
 EBIT % or EBIT margin = EBIT / Revenues
   2014 was -06%, 2015 was -18%, 2016 was -10%, 2017 was -14%
 The results show a negative EBIT margin. 
 Which means the amount of gross profit it generates at the moment,
 is not sufficient to cover its operating expenses. 
 In the time frame under consideration,
 Tesla's EBIT margin ranged between -6% and -18%.
 Net loss % or Net loss Margin = Net Loss / Revenues
   2014 was -09%, 2015 was -22%, 2016 was -10%, 2017 was -17%
 The results are similar to EBIT margin 
 and slightly more negative 
 because we consider interest expenses as well. 
 The final two ratios to consider are ROA and ROE.
 Both ratios will be negative as given 
 company registered Net Loss in all periods under analysis. 
 ROA = Net Loss / Total Assets
   2014 was -05%, 2015 was -11%, 2016 was -03%, 2017 was -07%
 ROE = Net Loss / Equity
   2014 was -32%, 2015 was -82%, 2016 was -14%, 2017 was -46%
Concluding the Profitability and Growth Analysis.
Tesla's business has been growing very fast 
in the period under analysis,
surpassing the 10bill mark in 2017. 
Over the next several years the main challenge under Tesla
will be breaking even and improving its profitability margins. 
Growing Revenues and Achieving Economies of Scale 
will play an important role in this process.
<br>

Now we look at Tesla's Liquidity,
by looking at Liquidity Ratios:
Quick Ratio
 A brutal assessment of how liquid the company is 
 at this very moment. Where we hypothesize 
 the firm will be unable to sell any of its Assets,
 and doesn't receive payments from clients,
 but still needs to cover its short term obligations. 
 Quick Ratio 
 = (Cash + Marketable Securities) / Current liabilities
   2014 was 0.91, 2015 was 0.43, 2016 was 0.60, 2017 was 0.46
   Firm's Quick Ratio decreased significantly 
   during timeframe under analysis. 
Current Ratio
 Shows us what portion of a firm's current liabilities 
 can be covered by funds to be received in the short-term. 
 Current Ratio
 = Current Assets / Current Liabilities
   2014 was 1.51, 2015 was 0.99, 2016 was 1.07, 2017 was 0.86
   Current Ratio below 1 is problematic to most industries. 
   Tesla's current ratio gradually dropped to 0.73 in Q1 2018. 
   Which means company's liquidity needs to be examined further. 
   One way to do that is compare the ratios 
   with other company's in the same industry,
   to see if this is a pattern that is commonly observed. 
   If this isn't the case then one cause of concern 
   when discussing Tesla should be its Liquidity. 
   And that company will have to raise capital 
   in late 2018 or early 2019,
   precisely due to deterioration of Liquidity Ratios seen here. 
DSO
 Day Sales Outstanding
 = (Accounts Receivable / Revenue) * 360
   2014 was 25.51, 2015 was 15.03, 2016 was 25.67, 2017 was 15.78
DIO
 Days Inventory Outstanding
 = (Inventory / Cost Of Goods Sold) * 360
   2014 was 148.20, 2015 was 147.32, 2016 was 137.81, 2017 was 85.45
DPO
 Days Payable Outstanding
 = (Accounts Payable / Cost Of Goods Sold)
   2014 was 120.89, 2015 was 105.62, 2016 was 124.00, 2017 was 90.23
Net Trading Cycle
 Net Trading Cycle
 = DSO + DIO - DPO
   2014 was 52.81, 2015 was 56.73, 2016 was 39.47, 2017 was 11.0
 A company's Net Trading Cycle tells us 
 if company was using its own funds 
 when selling products to clients. 
 If we owe more money to suppliers
 compared to the amount of money we are owed
 and the amount of money we have invested in inventory
 then we are financing our activities
 by using other peoples money. 
 If the opposite is true
 we need to use our cash to finance the business
 and keep operations up and running. 
 Net Trading Cycle terms are highly dependent 
 on a company's bargaining power
 and negotiating position 
 when dealing with clients and suppliers. 
 Tesla decreased it's Net Trading Cycle 
 sharply in 2017 to address liquidity issues temporarily,
 as the first half 2018 figure was slightly higher
 meaning company had to maybe revert back 
 to what normal level observed in 2014-2016.
 And is the reason for significantly low liquidity ratios 
 in first half of 2018. 
 So Tesla will probably have to raise capital 
 at some point to address its liquidity issues
 and be able to sustain its fast growth.
 This is a very subtle moment and is natural 
 for a company that is still in its growth face. 
 The problem is that Tesla is already a listed firm 
 with a significant Market Cap
 and raising additional Capital would be seen as 
 a sign of weakness by financial markets.
<br>

Now we look at Tesla's Solvency Ratios.
Solvency Ratios are used to monitor a firm's
ability to service future debt obligations. 
Not only looking at Short term with Liquidity ratios,
but also interested in the company's ability 
to cover obligations in the long run. 
Debt Ratio
 Debt Ratio = Total Assets / Total Liabilities
 The number must be above 1,
 and much better if ratio is 1.5 or higher. 
   2014 was 1.19, 2015 was 1.16, 2016 was 1.32, 2017 was 1.22
Tesla's Debt ratio stays around the 1.2 range. 
This can be a negative signal. 
The other negative signal is 
it would not make sense to calculate the Interest Coverage Ratio,
given that Tesla's EBIT is negative. 
The Company in 2018 would not be able 
to cover its Interest Expenses with operating profitability. 
As it has not reached Break Even yet. 
Making Tesla a very risky company 
especially for lenders who are lured in 
to the investment by high bond coupons in the range of 
5 to 7 %. It has relatively low liquidity, 
and strong reputation and brand,
and has not reached profitability. 
This is why opinions of the future 
of the firm tend to be polarizing.
<br>

Working capital is given by a company's 
1) Current Assets - Current Liabilities
2) Trade Receivables + Inventory - Trade Payables
Operating Cash that is "2)" can amount to 2y of annual revenues.
If a firm has a lower amount of cash on it's balance sheet
we will consider its entire cash balance as operating cash.
If the cash on it's Balance Sheet is higher,
then according to this methodology, 
we should calculate 2% of revenues,
which will be our operating cash. 
The difference is defined as excess cash. 
Money the company keeps on its balance sheet,
which can be invested elsewhere and 
is not used for the current needs of the business.
<br>

A Company needs Sufficient Working Capital because
it is comparable to a person's cost of living. 
Everyone expects a payment of salary,
which represents Receivables.
And we all have to make payment for utilities or bills,
which represents Payables. 
We keep some food at home or cash in our pockets or bank accounts,
like Inventory.
If the monthly payments we receive are delayed,
and we are unable to pay out bills,
then the electricity company shuts down our bills,
and we would be unable to buy groceries,
after our foods supplies at home are depleted.
A business uses Working Capital in its daily operations.
This is the fuel required to run its 
daily, weekly and monthly operations of the company. 
Insufficient Working Capital risks being unable to run the business.
Current Liabilities could surpass Current Assets,
and create major Liquidity problems,
that can only be solved through some very expensive sell offs
of Assets, or External Financing which is very costly. 
<br>

Working Capital eg of Real Life Case Study
 Cytec Industries is a global company 
 operating in the sector of chemicals and materials.
 A manufacturing business selling products globally. 
 Cytec has been merged into the German Chemical Company Solvay. 
 Solvay paid $5.5 billion in 2015 to acquire Cytec.
 In 2008 Cytec industries management foresaw 
 an economic downturn. The company headquartered in NJ, US,
 experienced several years of strong growth before 2008.
 However management knew Cytec's business 
 is correlated to the economic cycle. 
 They also realized the company's bond financing maturing in 2010
 could be a disaster waiting to happen 
 as this wouldn't be an ordinary crisis. 
 When Banking giants collapse,
 it takes several years for economy to recover
 and for financial markets to function as usual. 
 And would have been very risky 
 to count on improved market conditions for 2010 when bond expires. 
 The firm's bank debt at time involved heavy unfavourable covenants. 
 And Cytec's management was eager to pay off the loan if able.
 Financial Markets are interested in cashflow generation. 
 In those years investors were careful,
 and wanted to be sure that the company they invest in 
 can weather the storm having sufficient cash on its balance sheet.
 Which is not an easy task if the business has been expanding,
 and has an external acquisition. 
 This resulted in growing working capital needs,
 which impacts cash flow generation and availability negatively. 
 In good times management is interested in P&L.
 They are interested in Profitability and if everything goes well,
 the Balance Sheet becomes of secondary importance. 
 But in bad times the Balance Sheet comes first. 
 Sources of financing and efficiencies are in Balance Sheet.
 Cytec's management knew they only thing in their control
 was Working Capital Management, that is 
 Inventory, Trade Receivables, and Trade Payables. 
 A preliminary assessment revealed Inventory
 was the most significant item 
 for working capital reduction opportunities.
 The analysis valued that the company's working capital 
 invested in the business was higher than the competitors. 
 And that the firm has more than 200 million 
 in excess working capital compared to competitors. 
 They recognized the opportunity to tap excess working capital
 to invest in the business that will shape their future. 
 When the economy began to deteriorate in 2008,
 they decided to accelerate the effort. 
 But before starting the initiative,
 Cytec hired a specialized consulting firm,
 REL consultancy company which focused on cash flow optimization. 
 Cytec's management conveyed their two goals which were
 to preserve customer service, and optimize working capital. 
 After meetings, interviews, site visits, segmentation of clients
 and suppliers, REL stated that potential efficiencies exceed 
 the $200 million mark, and they expect Trade Receivables,
 and Trade Payables will soon be the major contributors to that. 
 Management and REL agreed that for it to work in a sustainable way
 it would be up to the employees
 to focus on working capital management in their daily duties. 
 Cytec had said they want their people to understand how 
 their day to day activities affect working capital. 
 That anytime an individual makes a decision, 
 he or she should ask, 
 "What impact will this have on working capital?".
 Cytec and REL came up with three cornerstone points,
 - Standardize collection processes geographically 
   and introduce collection policies 
   for different customer profiles,
   implementing a rigorous escalation process 
   aiming at reducing overdue receivables. 
 - Update inventory re-order levels 
   and implementing a system improving order over quantity. 
 - Negotiate a new payment plan with suppliers,
   allowing a company to pay a little later when possible,
   and applying a payment clock, 
   a mechanism ensuring payments aren't made before they are due. 
 Many suppliers were flexible enough to renegotiate payment terms.
 In addition Uniform Policies and criteria across geographies,
 coupled with a stronger Focus On Collection resulted in 
 an additional Boost For Working Capital. 
 Such quick wins validated the entire project,
 and proved it can succeed across the organization. 
 This ensures Executive Level Support and 
 attracts attention from other employees. 
 There were significant improvement in DSO, DIO, DPO.
 Cytec said they were able to generate some quick wins,
 particularly in the payables and receivables area,
 and once people saw the success, everyone wanted to be involved. 
 And also that the project brought new exposure to the credit group
 and emphasized the importance of its role in facilitating collection
 rather than just managing credit risk. 
 Company executives highlighted that the project succeeded because 
 Cytec and REL created a series of metrics and dashboards,
 that allowed operating units, account managers 
 and top executive to monitor the development of the working 
 capital improvement plan. This is important because 
 it brings a sense of accountability and 
 people are interested in seeing the actual results of their efforts. 
 They had $400 million of Working Capital Efficiencies 
 which allowed them to weather the storm and sail safely 
 when financing was scarce and costly. 
<br>

There are tradeoffs businesses face 
when trying to optimize their working capital. 
Bad working capital management can lead to foreclosures. 
Sometimes if working capital is too thin 
there can be Liquidity problems,
and cannot repay creditors and trade counter-parties. 
A firms working capital provides sufficient cushion for Liquidity. 
Too big of a cushion means too much is invested in working capital,
and are being inefficient as this is money that could have been
invested elsewhere. The money could have been used 
to repay financial liabilities, invest in a new Capex project,
or it could have been redistributed to shareholders. 
So the two conflicting goals are Liquidity and Profitability. 
A high investment in working capital improves Liquidity,
and decreases Profitability. The level of working capital 
a firm maintains isn't in full control 
as it depends on negotiation with external parties,
such as clients and suppliers with current production capabilities. 
Finance managers must make sure two situations can be avoided. 
Overtrading represents firms that have insufficient capital
to maintain its current level of sales.
This is when working capital is too thin and 
Liabilities have grown higher than current Assets,
which is a disaster in terms of Liquidity. 
The opposite case is called Overcapitalization 
which consists of maintaining an excessive level of working capital,
and missing other investment opportunities,
given that our cash is not used and blocked within the business. 
When some aspects of working capital change others will too. 
-If a discounted is offered to customers who pay earlier,
 Trade Receivables falls, Cash goes up,
 but will likely reduce the Profit margin,
 and will entice customers to order other products,
 which will decrease inventory. 
So working capital items are interrelated. 
<br>

Trade Receivables Management
is a delicate and important issue for Financial Managers.
Three main areas
- Pre-Screen Customers, and make preliminary judgment 
  as to whether they are credit worthy, 
  which will prevent the firm from giving credit 
  that will turn into bad debt. And screening must continue
  for existing clients, 
  and monitor and access ability for repayable. 
- Credit Terms Policy, which is adequate 
  and doesn't put firms Liquidity at risk. 
  Firm should define maximum amount of credit 
  that new customers can have. Existing customers too.
  This is a function of a Clients size, and importance to the firm. 
- Collection Of Receivables, that is must make sure 
  that customers are reminded of the amount owed to firm 
  and that it has to be paid soon. And have people who work 
  consistently to decrease the delay of customer payments.
  If a company doesn't try hard to collect its receivables,
  clients will be more than willing to postpose their payment.
  And Receivables will sky rocket and company will experience 
  cash flow problems. 
<br>

There are several steps to follow 
when assessing a customer's creditworthiness. 
- Ask for a Bank Reference. 
  Customer is a Banks Client and 
  Bank has no incentive in providing a disservice to its client. 
  But a failure to provide a Bank Reference is alarming. 
- Obtain a Trade Reference. 
  Much more efficient 
  to contact a company that deals with this client. 
  And if there is an existing relationship with this company
  and out company, the opinion will be less biased. 
- Read the Client's Credit Rating and Related News. 
  The drawback of this information is that 
  it will be available in the news and 
  ideally we should be ahead of the news to make informed decisions.
- Visit a Client's Facilities. 
  Probably the best technique of them all. 
  If the credit given to client is substantial,
  it is worth visiting them on site and forming a first hand opinion. 
  Seasoned managers can form an opinion quickly.
  It does not have to be obvious to the company
  that the visit is for the purpose for evaluating them.
<br>

If a company is considered creditworthy,
then the next step is
Credit Terms And Monitoring Of Receivables. 
Must define clearly
- Frequency of Payments
- Maximum Credit Amount , that can be showed for on credit.
- Penalty for Delayed Payments
Different Clients will have different credit terms 
based on their relationship with firm,
internal credit rating scoring,
and mostly on their importance based on size and profitability. 
Credit limits should be flexible 
if the volumed purchased by clients increases,
and we gain proof that client is serious and trustworthy. 
We must also be cautious because some ill faith companies 
applies the following trick. 
That is start working with a new supplier
and pay for their first few orders as soon as possible. 
And then when supplier allows them to make a larger order on credit,
they stop paying, increasing the firm's receivables. 
Two popular ways of
Monitoring Trade Receivables are 
- Accounts Receivables Analysis ,
  looks at amount owed by each client
  and the number of Days their payment has been outstanding.
  Such analysis shows the average state of receivables,
  and total amount due by company. 
- Credit Utilization ,
  shows us how much of each clients credit limit 
  has been used. Indicating to us if we should talk to clients
  and ask them to reduce the receivables outstanding
  or negotiate increasing their limit
  if the volume of business with that client is increasing. 
The final area that Financial Managers must focus on is
Collection Of Cash
- Must make sure invoices are sent promptly to clients,
  as this is the first time clients are notified of their obligation.
  Any delay in sending out an invoice is our fault. 
- Sending chasing letters or making chasing phone calls,
  that is to solicit clients and remind them money is owed. 
  This can be effective but must be applied with caution
  to preserve relationship with clients
  and avoid endangering future business. 
- Have Senior position management call personally.
If these steps are taken and it produces no effect,
them we will be forced to stop clients supplies
and proceed with legal action,
if payment is not made in reasonable amount of time. 
Legal Procedures Are A Measure Of Last Resort,
as more cost will be insured on firm,
and is uncertain if full amount can be payed back,
especially if client faces bankruptcy. 
Many businesses handle bad debtors by signing an agreement with
an external Debt Collection Agency. 
Amount Recovered will likely never be equal to Amount Owed by Client.
<br>

Re-order Level 
is an inventory control technique.
Sometimes companies run out of inventory 
and are unable to continue production process
as raw materials in warehouse have been exhausted.
Re-order Techniques allow us to calculate
the level of inventory at which 
we should call suppliers and place an order. 
Three variables to consider
- Lead Time ,
  is days to wait once order has been placed 
  to suppliers for it to be delivered.
- Average Daily Consumption ,
  is amount of raw materials used on a daily basis.
- Safety Stock ,
  is the number of new units 
  we want to have in our warehouse
  when a new shipment arrives.
  In case shipment comes in later than expected. 
Re-order Level 
= (Lead Time * Average Daily Consumption) + Safety Stock
eg
 if 1000 cars are produced a day,
 and Lead Time is 5 days,
 and 4000 tires are required per day,
 with safety stock of 2000 tires.
 Re-order Level = (5 days * 4000 tires/day) + 2000 tires 
                = 22000 tires
 So when company reaches 22000 tires in warehouse, 
 it will place a new order and wait for delivery.
 At time of delivery there should be 2000 tires safety stock.
- Lead Times vary throughout the year.
- Daily production varies throughout the year.
  A superb communication between production facilities,
  sales teams, external supplier is needed to keep method working,
  and avoid production disruptions due to shortage of raw materials. 
<br>

Economic Order Quantity
is another inventory control technique,
and one of the most frequently used methods. 
Here we determine the minimum cost to sustain
when ordering supplies.
We factor in a few variables
- Expected Annual Usage , 
  How much raw material we expect to use in a year
- Product Cost ,
  That is the Price Per Unit including delivery costs. 
- Cost of Purchasing ,
  In terms of Paperwork, Follow Up, Inspection.
  Activities that involve man power which costs. 
- Holding Cost , 
  Warehouse Cost as it can be expensive to store, 
  Obsolescence as can become obsolete or outdated, 
  risk of robbery 
  and costs related blocking money for period of time.
All of these variables give a better idea of Inventory Cost. 
Not only is there cost to finance the inventory,
but also the costs that must be sustained 
related to keeping in warehouse 
Mathematic calculus gives Wilson EOQ formula.
Y axis Cost, X axis Quantity,
Economic Order Quantity is intersection of 
Holding cost line that rises and looks like x=y line,
and Ordering cost that is a decreasing curve.
D = Annual usage of Raw Material
S = Cost to Purchase
H = Holding Cost
EOQ = square root of ( (2*D*S) / H )
eg
 D = Annual Demand = 4000
 H = Holding Cost = 3% * $3 = $0.09
 EOQ = sqr root of ( (2*4000*3) / 0.09 ) 
     = 517 units per order
EOQ Drawbacks
- Lead Time for Vendors is not constant
- Raw Material Prices are not constant
- Doesn't take into account large volume purchase discounts. 
Each variable needs to be estimated carefully.
<br>

A good finance manager doesn't simply deal with
performance monitoring and accounting metrics.
It is their job to implement techniques 
that improve the actual development
of receivables, inventory, and payables. 
Inventory Optimization Techniques
- Setting up Par Levels (Re-order Levels)
  Par Level is a technical term for Re-order Level.
  For calculating the minimum amount 
  of inventory we want kept in warehouse,
  and will serve as red flag for when 
  raw material reaches a critical level 
  and needs to be reordered.
  - Analyze Products
  - Come up with a methodology to set Par Levels
  - Update a few times a year
- Use FIFO
  Oldest items in warehouse should be first ones to go out. 
  Especially true for fruits and vegetables and perishables. 
  Make an effort to sell old items first.
- Communication is Key
  - Speeding up Product Delivery
  - Sending More of a Product
  - Refunding Faulty Products
- Auditing
  Ensures information in ERP matches reality. 
- Have Backup Suppliers Ready
  In case of increased demand for products
  and inability of main supplier 
  to supply the additional raw material units. 
<br>

Accounts Payable 
are the one component of Working Capital
that works in our favour. 
Can be said Accounts Receivable and Inventory 
are two items blocking money,
then can be said Accounts Payable 
can be a source of financing,
allowing us to work with other people's money.
Every company that managed to go along on Accounts Payable
and delay payments to suppliers by 30,45,60 or 180 days,
has a strong advantage going forward. 
It is not ideal to freeze payments to suppliers,
if it doesn't correspond to business terms already agreed upon
when starting to work together. 
It is one thing to contractually agree on payment terms 
of 60 days, and another thing to hold up payments
after the agreed deadline of 10 days and hold up until 60 days.
We must respect Trade Agreements,
and avoid stretching payments to suppliers
when delayed payment isn't part of original agreement. 
Shopping on Credit needs to be pre-agreed. 
<br>

Working Capital Management
is one of the key success strivers for a company.
Plays a vital role in long run
as it allows company to free up capital 
and invest in strategic initiatives. 
And is more important during times 
of economic crisis, 
high interest rates
and lack of financing opportunities.
Working Capital may not appear on firms P&L,
appears on Balance Sheet.
but has direct impact on firms Profitability. 
Working Capital Optimization help for 
- Enhanced Customer Service
  and higher client satisfaction,
  resulting in improved client loyalty.
- Raw Material Efficiencies
  reduction in spend, reduction in raw material obsolescence,
  reduced warehousing and distribution cost
- Operating Expenses Efficiencies
  from lower transaction processing costs 
  and increased standardization and optimization. 
Study found that the Top of Top 1000 companies 
use half the working capital of rest of companies.
<br>

Working Capital Optimization roadmap
- Phase #1 Careful Assessment of firm's working capital position.
  - Are there consistent late players?
  - Are there redundant inventory components?
  - Why we pay suppliers early?
  Metrics like working capital days are useful at this stage
  - Days Receivable
  - Days Payable
  - Days Inventory
- Phase #2 Build Management Reports & Dashboards
  to track and monitor development of KPIs across the company.
  KPI is key performance indicator. 
- Phase #3 Create an Action Plan
  All units and devisions should create an actionable plan
  to find the improvements they aim to achieve and deadline 
  by which such improvements should be acomplished. 
  Must align Executive Compensation and 
  Working Capital Efficiencies obtained by their team.
- Phase #4 Win Top Management Support
  Getting onboard the CEO and CFO.
  Identifying low hanging fruits
  can provide quick wins 
  which would validate importance of entire project.
<br>

Companies are people are resistant to change.
1) One of the key signs a company has not optimized
its Trade Payables function 
is if it doesn't have financial difficulties
but pays interest or late payments
and has been imposed credit sections by suppliers.
Such problems usually mean 
Payment Term Approval Mechanism Issues,
and that in general there is a lack of standardized payment terms.
2) Another key sign a company has not optimized
its Trade Payables function 
is if it has a large number of suppliers.
It is strange to see a company 
work with a large number of suppliers who sell the same product. 
No reason to work with 10 suppliers if you can concentrate on 2,
and get a better deal on price, product and payment terms.
Another issues would be 
firm having multiple payment terms with same supplier. 
Much more efficient to pay everything at same time
and avoid going through same process multiple times per month.
3) Another key sign a company has not optimized
its Trade Payables function 
is if it has an Inaccurate Cash Flow Forecasting of Trade Payables. 
<br>

Time Value of Money
 Money Today is more valuable than money tomorrow.
 The rational is that money we receive today 
 has a potential earning capacity. 
 And is why everyone would prefer to receive money sooner 
 than later and why timing is one of the most important parts 
 when talking about money. 
 eg 
  We will be paid $1000.
  Option A: receive the money today.
  Option B: receive the money after 1 year. 
  For A we can deposit money in bank today
  and receive interest with new total being $1030 after 1 year. 
  Given that the bank wants to attract our money,
  they are willing to pay interest on it. 
  At 3% interest thats an addition of $30. 
  For B we would have missed the opportunity to earn 30$.
 Money today offers more opportunity than money tomorrow. 
<br>

Interest Rate 
is the cost of borrowing 
or the cost that one pays for the rental of funds. 
Mortgage, Fixed Income, Investment Loans, Student Loans. 
Interest Rates influence the economy. 
If a person wants to buy a house but interest rates are too high,
this could impede them from taking action,
and instead deposit savings in a bank,
as they would earn them a high level of interest. 
A similar logic exists in the corporate world. 
High borrowing rate impedes firms from investing in new projects.
It is also true that the economy influence the economy. 
During a period of stable growth,
everyone is less concerned about depositing money. 
During a crisis everyone is cautious and unwilling to lend money,
resulting in high interest rates. 
Understanding the dynamics interest rates have,
in different economic cycles,
is key for making informed and successful financial decisions.
<br>

Components forming interest rates.
 Every type of interest rate can be disaggregated 
 as the sum of 5 components. 
 The building block of all interest rate is the real Risk-Free Rate. 
 An interest rate that assumes no risk of default 
 and simply reflecting the time value of money. 
 1) Risk-Free Rate
    Assuming no risk of default and zero inflation. 
 The second building block is Expected Inflation.
 As time goes by the market prices rise 
 and purchasing power of money is reduced. 
 That is why interest rates contain a component
 that accounts for inflation 
 and compensated for the reduced purchasing power money.
 Such a component is added to the real Risk-Free Rate. 
 2) Expected Inflation
    Compensates for the reduced purchasing power of money.
 When someone borrows a given amount of money,
 there is always the change that 
 they might not be able to repay the money
 because of bankruptcy. Or is not able to pay part of loan.
 This is the Default Risk component. 
 Every borrower has a different default risk profile
 and therefore this component is evaluated on a case by case basis. 
 3) Default Risk 
    Compensated the lender for assuming default risk.
 Fourth component is called Liquidity Premium. 
 Some investments are highly liquid, eg U.S. Treasury bond.
 And have a low Liquidity Premium.
 Others are much less liquid.
 A liquid market gives investors options 
 if they need their money in a short period of time. 
 They will be able to sell their investment on the market. 
 On the other hand if there isn't a market, 
 it is much more difficult to exist at a given position.
 The investor will have to give a significant discount 
 from the price in order to stimulate buyers.
 Which will incur losses. 
 That is why liquid security must compensate
 its owners through a higher interest rate. 
 4) Liquidity Premium
    Premium that investors demand 
    when a security is difficult to sell.
 The fifth and last component is Maturity Premiums.
 A Maturity Premium is added to those securities 
 that have a longer duration. 
 All else being equal, 
 an investor would require compensation,
 for the longer the duration of their investment. 
 Given that they will be unable to use their money
 for a longer period of time. 
 5) Maturity Premium
    Compensating an investor 
    for the long maturity of his investment.
 The sum of these 5 components and a profit margin
 for the bank form these interest rates
 that we encounter on a daily basis. 
<br>

LIBOR (London Interbank Offered Rate)
The benchmark rate used by banks worldwide 
in order to determine the cost of money.
The average interest rate estimated by leading banks in London.
Calculated for
- 5 currencies (USD, EUR, GBP, JPY, CHF)
- 7 maturities (overnight, 1 week, 1 month, 2 months, 3 months,
                6 months, 1 year)
LIBOR rate approximates Risk-Free Rate.
<br>

Variable vs. Fixed interest rates.
The benchmark rate used by banks worldwide 
in order to determine the cost of money. 
Variable interest rates change over time,
and is tied to another market interest rate,
LIBOR has become that industry standard
Variable Interest Rate
 = LIBOR + Spread 
 where Spread is determined by criteria
 such as Inflation, Default risk, Liquidity and Maturity.
Fixed interest rates do not change over time.
Used for loans that have a longer duration,
10 or more years. 
Most people prefer Fixed Interest Rate,
but is not necessarily the right choice. 
It depends on if the current rate is low 
compared to the 20 year historical samples.
Fixed rate also includes some of the additional cost 
for carrying out transactions 
when derivate financial instruments swap, 
which allow banks to fix the interest rate. 
Some studies show Variable Interest Rate 
can be less costly in the long run. 
<br>

Default Risk
 A very important part of the interest rate
 that is assigned to a particular borrower 
 is their default risk.
 It is the only ingredient, which is unique 
 for each and every single case. 
 The other 4 components are common for most loans
 or are trivial to a large category. 
 Every person, every corporation and every country,
 carry their own default risk. 
 And given it is the only component that is strongly individual,
 this is where the bank concentrates when it tries to determine
 how much to charge you. Bank wants to access
 - How much it is going to loose if you default?
 - How likely is it that you will default?
 EL = Expected Loss
 EAD = Exposure at Default
       How much bank's money will be at risk if we default. 
 PD = Probability of Default
      How likely is it that we will default.
 LGD = Loss given Default
       The percentage of bank's money that will be lost.
 EL = EAD * PD * LGD
 Expected Loss 
  = Exposure at Default + Probability at Default
    + Loss given default
 eg 
  An Individual buys a $300K house,
  and finances the acquisition through a bank loan.
  The bank lends them $300k and they buy the house. 
  Banks rarely loose more than 30% on mortgage loans that is LGD,
  as they have the right to resell the property.
  The more guarantees that are given to bank
  under the form of mortgages, Assets, Pledge on shares, 
  future income ,etc. The lower the expected loss will be. 
  If they bank has no guarantees 
  the interest rate will be much higher.
  Several factors conclude the probability of default
  - Earning Potential
  - Liquidity
  - Credit History
  - External Factors
  If the mortgage is $300K, 
  borrower will need to pay 2.5K a month for next 10y,
  or 1.5K a month for next 20y. 
  In addition to that they will be charged interest. 
  The earnings of a person need to match that and more.
  A person may be rich on total value of Assets owned,
  but that same person may have trouble if they are unable to
  convert those Assets to cash. 
  If the borrower is paid on a per project basis,
  and if the next payment is delayed 3 months.
  Then they will miss 3 mortgage payments. 
  And will incur further debt to cover living expenses. 
  Which is why Liquidity is important 
  incase things do not go as planned. 
  A borrower with a record of paying on time,
  and having a long term address, 
  should be offered a lower rate of interest,
  than someone who has missed their payments.
  That is if borrower has good credit history,
  and has been a good bank borrower in past,
  then much more likely will be granted loan 
  and with better interest rate.
  Industry Development and Market risk are external factors. 
  These are not dependent on borrower,
  but are related to their ability to repay the loan.
  If they operate in an industry that is cyclical,
  this represents an additional risk that is accounted for 
  in the interest rate attributed to the borrower. 
<br>

Corporate Borrowers
have access to more sophisticated loan forms.
- syndicated loans
- mezzanine debt
- convertible loans
- bonds
Interest rates are determined by
- earning potential
- quality of assets
- guarantees
- liquidity
- credit history
- industry of operation
Some corporate loans involve a great deal of risk
- startups
- fast-growth firms
- distressed firms
High-yield interest rates do up 15% per year.
High interest rate make the possibility of such loans to exist.
Even though default rate is substantial,
the financiers are able to make up for it by charging more. 
A corporate borrower needs to convince financiers that 
- it has solid plans for the future
- its assets are valuable and in good health (guarantees)
- sufficient liquidity
If a firm can convince a bank of this,
then can get a lower interest rate compared to peers.
<br>

Going by money today is more valuable than money tomorrow,
and Comparing Cash Flows of
- Scenario 1: Receive $100 in 2 years and $110 in 3 years
- Scenario 2: Receive $100 in 1 year  and $100 in 2 years
By simple math scenario 1 gives 210 vs 200 for scenario 2.
But considering the Time Value of money gives a different answer.
If $100 is deposited in Bank in present day,
and if money stays in bank for a year at 3% interest rate,
then Interest Rate * Present Value = 3% * $100 = $3, 
giving a future value of $103.
Future Value = Present Value * (1+i)
Future Value = 100 * (1 + 3%) = 103
Present Value = Future Value / (1+i)
If it stays in bank for another year,
$100 * (1+3%) * (1+3%) = 106.09
Present Value = Future Cash Flow "n" years from now / (1+i%)^n
Given an interest rate of 10%,
- Scenario 1: Receive $100 in 2 years and $110 in 3 years
  Present value of $100 2 years from now is $100/(1+10%)^2 = 83
  Present value of $110 3 years from now is $110/(1+10%)^3 = 83
  Total Present Value = 166
- Scenario 2: Receive $100 in 1 year  and $100 in 2 years
  Present value of $100 1 year  from now is $100/(1+10%)^1 = 91
  Present value of $110 2 years from now is $100/(1+10%)^2 = 83
  Total Present Value = 174
The Discount Rate will be the Rate of return 
an investors expects, of his investments. 
<br>

Project Feasibility
Every new project requires 
a careful assessment of its future cash flows. 
Present vs. Future Cash Flows
 Investment(Present) vs. Future Cash Flows(Future)
 are not comparable.
 We must discount Future Cash Flows 
 and obtain their Present Value.
 We need to measure the approximate amounts 
 and points in time when they will be saved or paid. 
 Determining the value of price can be challenging,
 because of the time value of money as we already know 
 a dollar earning in future is not equal to a dollar today.
 Discounting cash flows and obtaining their present value,
 is a way to account for this. 
 eg
  Investment Decision(Example)
  Buying a stock,
  compare the stock's price 
  and the future cash flow that it will produce. 
  An investor will compare the Price 
  that he will pay for a given stock today, 
  and the Cash Flow(Dividends) 
  that he will receive in the future. 
  If the Present Value of Future Cash Flows is higher,
  than the current investment,
  the investor will buy the stock. 
  Price of Stock Today > or < or = Stock price and Dividend n years.
Net Present Value
 NPV 
 = (Sum of (Cash Flow after n periods / (1+i)^n)) 
   - Initial Investment
 That is Sum of Discounted Cash Flows minus Initial Investment.
 eg
  A firm plans to build a plat that will produce 
  the following cash flows,
  30 for Year 1, 120 for Year 2, 
  200 for Year 3, 120 for Year 4, 
  120 for Year 5,
  and after year 5 the plant will be obsolete 
  and will have to be replaced. 
  Given the plant costs 500,
  and the firm's marginal borrowing rate is 10%,
  Present Value Year 1 = 030/(1+10%)^1 = 027,
  Present Value Year 2 = 120/(1+10%)^2 = 099,
  Present Value Year 3 = 200/(1+10%)^3 = 150,
  Present Value Year 4 = 120/(1+10%)^4 = 082,
  Present Value Year 5 = 120/(1+10%)^5 = 075,
  NPV = 28+99+150+82+75 - 500 = -57,
  which means project is not feasible,
  and should be avoided.
The concept of Net Present Value is very important,
as it stands at the core of some fundamental financial techniques. 
It is applicable in many cases when a person,
or corporation faces an important financial decision. 
<br>

Annuities
 An annuity is a series of payments made at fixed intervals of time.
 - Monthly Mortgage Payments
 - Insurance Payments
 - Pension Payments
 Future Value of an Annuity:
  S[n,i] = actuarial value S
  R = constant monthly payment
  i = interest rate
  Future Value(i,n,R) = R * S, where 
  S = ((1+i)^n - 1) / i 
  eg 
   Number of Periods = 60
   Monthly Payment = 100
   Interest Rate (annual) = 10%
   Interest Rate (monthly) = 0.8%
   Future Value => EXCEL =>  = -FV(0.8%,60,100) = $7744
   Which is the amount we would have in 5 years,
   if we were to make constant monthly payment of 100$,
   and an annual interest rate of 10%. 
<br>

Calculating a Loan Schedule
Capital vs Interest Payments
 Consider a bank loan that requires constant monthly payments.
 Loan Parameters:
  Amount to be financed: $300,000
  Interest Rate: 3% (2-4%, 3% approximately)
  Loan duration: 10 years
  Number of Periods = 120
  Interest Rate (monthly) = 0.25%
  Loan Amount ($) = 300,000
  2 ways to calculate Monthly payments.
  - Future Value of an Annuity:
    Future Value(i,n,R) = R * S where S = ((1+i)^n - 1) / i
    R = constant monthly payment
    n = number of periods
    i = interest rate
  - Present Value of an Annuity:
    Present Value(i,n,R) = R * a where a = (1 - (1_i)^n) / i 
     Monthly Payment
     => EXCEL => =PMT(rate,nper,pv) =PMT(0.25%,120,300000)
     = $2,896.8/month for 10y to pay loan.
<br>

Capital Budgeting
also known as Capital Asset Planning
is the term relating to the decision making process
companies go through when they must determine
whether to invest in a specific long term Initiative or Asset. 
In addition Capital Budgeting is used as a tool,
allowing executives to compare alternatives they have,
when making strategic decisions.
Capital Budgeting is used to assess
- The investment in a new production plant
- The acquisition of a new ERP system
- R&D activities related to a new project
- Expanding our existing warehouse
- Purchase or leasing new vehicles
- Invest a significant amount in employee training
These are all long term, important and large investments,
and these decisions impact a company's business for years to come.
Cannot be easily reversed. 
When discussing a projects feasibility,
the topics to discuss are
- The amount of capital
- The project's timeline
- The financial return
<br>

The core principal of finance is
Money Today is more valuable than Money Tomorrow.
The rational is that Money received today 
has a potential earning capacity. 
And why every person would rather receive money today than later.
Hence Timing is one of the most important topics regarding Money.
Money today offers more opportunity than money tomorrow.
$1000 received today and deposited in bank 
could be $1030 after 3% interest annual 1 year from now. 
When we build a plant or invest in R&D today,
we commit money that is available now,
to reap the benefits later.
Invest today, get more money later.
Capital Budgeting exercise aims to answer the question
of if it is worth investing x today,
if we expect to obtain x+y a year from now.
The analysis shows if the project will create or destroy value,
and will also allow us to compare different investment alternatives,
and see which one offers a higher rate of return. 
Present Value = Future value after n periods / (1+i%)^n
Project Cash Flows involve Investment today which is negative,
and Cash flow 1, 2 ... n which are positive. 
Discounting Future Cash Values allows us 
to compare with present value 
and calculate rate of return of project. 
To find the Discount Rate to use for calculation,
depending on the project, it can be using
- The firm's Cost of Debt
  Cost of Debt is the average interest rate 
  that a company pays on its borrowings. 
  And it makes sense to use the Cost of Debt as a discounting rate,
  if the entire project is financed with debt. 
- The firm's Cost of Equity
  There are many ways to calculate Cost of Equity. 
  Investment bankers use CAPM,
  or Capital Asset Pricing Model,
  Cost of Equity 
   = Risk-free Rate + Beta * Market Risk Premium
  The Risk Free Rate in an economy
  is the rate of return that an investor 
  would expect from a financial security
  that contains zero default risk.
  The investor buys a security 
  and will be certain he is paid on time and in full.
  Practitioners approximate Risk-Free 
  with a 10 year Government Bond to approximate this measure.
  The Governments of developed countries have a solid reputation,
  and can be trusted in a 10 year time frame. 
  The rational behind using a 10 year and not 3 month bond,
  is that the valuation of a firm is a multi year exercise.
  The next component is Beta. 
  This is a statistical measure. 
  Shows how a security behaves with respect to rest of market. 
  Beta = Cov(r[i],r[m]) / Var(r[m])
  That is diving its covariance with rest of market's variance.
  Can find Beta for stocks on yahoo finance, etc. 
  Beta < 1 , means less volatile than the market. 
  Beta = 1 , shows as volatile as the market.
             That is if market gains 1%, it also gain 1%. 
  Beta > 1 , more volatile than market. 
             If market grows 2%, stock might grow 2.5-3%.
  A company's Beta will have a value ranging between 0 and 2.
  The next component is Market Risk Premium.
  Theoretically given by average expected 
  market return minus Risk-Free Rate.
  Academic search shows the Average Market Risk Premium rate
  varies between 4-5% and 5-5.5%, and most practitioners
  use 5% in their calculation.
  Cost of Equity = Risk-Free Rate + Beta * MRP
   = Risk-Free Rate + Beta * 5%
  Can find yield of 10 year US bond on google,
  this is the Risk-Free Rate.
  Company's Beta is found on yahoo finance or google.
  MRP is usually taken as 5%.
  Cost of Equity 
   = Return For Investing Without Risk + Return For Extra Risk
  Cost of Equity is a suitable Discount Factor 
  for projects financed with 100% Equity. 
  This is an assumption that no debt will be used.
  US 10Y Bond yield is 1.612%
  India 10Y Bond yield is 6.318%
  Apple Stock Beta is 1.22
   1.612% * 1.22 * 5% = Apple's Discounted Rate = 9.8%
  Facebook Stock Beta is 1.32
   1.612% * 1.32 * 5% = FB's Discounted Rate = 10.6%
  HDFC stock Beta is 0.89
   6.318% * 0.89 * 5% = HDFC's Discounted Rate = 28.11%
  ITC stock Beta 0.56
   6.318% * 0.56 * 5% = ITC's Discounted Rate = 17.7%
<br>

  Project Specific Beta
  There can be a difference between a project's Beta
  and a company's Beta. And happens when a project 
  is financed with a different amount of leverage, 
  than a typical amount of leverage used by the company. 
  eg 
   GE wants to finance a project with 30% Equity and 70% Debt.
   A typical company does 60% Equity and 40% Debt.
   The greater the debt taken up in a project,
   the riskier it is and the higher its payout will be. 
   And is not theoretically correct 
   to use Company's Beta for this calculations. 
   To account for this there are few manipulations. 
   That is adjust the Company's Beta for the risk profile of the industry in which the project will be carried out. 
   And the amount of leverage for the project. 
   eg
    Company's Beta = 0.6, Debt/Equity = 1.86x or 65%, Tax Rate = 30%
    First we must deliver company's Beta, that is calculate a Beta independent of firm's capital structure. 
    Beta[n] 
     = (1 / (1 + (1-t)*(D/E))) * Beta[l]
     = (1 / (1 + (1-0.3)*(1.86))) * 0.6 
     = 0.26
    This is company x's unlevered Beta,
    independent of the firm's capital structure. 
    Beta[l] = Beta[n] * (1 + (1-t)*(D/E))
            = 0.26 * (1 + (1-0.4) * 2.33) = 0.63 where 2.33 is 70%
            = 0.63
    Giving the Project Specific Beta as 0.63 vs company Beta 0.6
<br>

- Weighted Average Cost of Capital
   Whenever we need to access a project,
   which will be financed with both Debt and Equity,
   we must use a blend of the two discount rates. 
   Cost of Debt and Cost of Equity.
   The Discount Factor that takes into account both debt and equity,
   is WACC or Weighted Average Cost of Capital.
   It provides a sense of the average opportunity cost
   sustained by investors for investing their funds in a firm.
   WACC = D/(D+E) * k[d]*(1-t) + k[e] * E/(D+E)
   D/(D+E) + E/(D+E) = 1
   Shows that if a project is prevalently financed with Debt,
   the Cost of Debt will have a higher weight 
   and coversly for Equity.
   The Cost of Debt includes a third factor that is (1-t),
   considers the fact that interest expenses are tax deductible,
   and the cost of debt is lower than it seems,
   as it provides borrowers with a tax shield. 
- A hurdle rate chosen by management
<br>

Typical Sequence of Cash Flows in a Project
eg 
 Company expects to build a plant that assembles bicycles.
 And plant costs an estimated $25 mill. 
 The first cash flow would be the capital outflow of $25 mill. 
 Investing to build out the fixed asset. 
 Once plant is ready Working Capital would be needed. 
 Can't assemble Bicycles without buying parts 
 and holding certain amount of inventory. 
 Reasonable to expect every project like this one 
 would require some Working Capital,
 and be blocked throughout its lifetime. 
 If this company already has an old assembly plant, 
 then it can sell some of its equipment there,
 and this would cause a positive cash inflow. 
 The budget for new plant comprises of acquitition of new machinery. 
 Allowing us to sell old Assets. 
 Once plant is ready,
 company will assemble new bicycles,
 and will have recurring Operating Cash Flows,
 from companies buying and distributing these bicycles. 
 Recurring Operating Cash Flows 
 are what will determine if this will be a successful project. 
 The more bicycles are assembled 
 and the higher the efficiency with which it is done in plant,
 the higher the cash flows realized 
 throughout the plants life 
 and higher the chances of project succeeding. 
 If we assume the plant will be used for 15 years,
 and after that company must build a new plant,
 we must consider the fact 
 that the plant we are about to build 
 will have a significant residual value 15 years from now. 
 Perhaps some machinery will be sold 15 years from now. 
 Otherwise will be recycled, 
 or someone else might want to buy the plant. 
 Once the project life ends, 
 the working capital invested at the beginning,
 to buy inventory parts for bicycles,
 would be freed up. 
 Working Capital will have positive cash inflow from Asset Recovery. 
 We must Estimate The Total Investment Needed.
 And make sure Have A Good Idea About Costs,
 and money needed to compete the project. 
 Less Risk If A Third Party Bears Cost Overruns. 
 Otherwise if we ourselves invest in building the facility
 and construction becomes more expensive than initially thought,
 the entire project assessment prepared 
 with Capital Budgeting Exercise becomes irrelevant. 
 It is key to understand if initial investment is a fixed amount,
 or an estimation that will likely change once project starts. 
 For this second scenario, we must perform a sensitivity analysis.
 Allowing decision makers to see how the projects financial 
 will look in different stages of the world.
 Done by creating different scenarios in-which the plant being built
 costs different amounts. 
 Once the project has been completed it will serve its purpose. 
 In the example earlier the plant will produce bicycles 
 and generate money. We estimate how much money will be made 
 before project starts. 
 This involves assessing the demand for bicycles 
 and making an assumption about the price they will be sold. 
 Not just a year from now but thought the life of entire project. 
 By estimating potential demand and price at which bicycles can be sold, we obtain a projection of revenue figures. 
 Projected Revenue 
  = Demand * Price
 Estimating expenses can have many unknowns.
 Price of bicycle parts could change, 
 cost of labor can change over time,
 and many unexpected factors along the way. 
 It is important to model expenses in sync with revenues,
 and respect assumptions made when forecasting revenues. 
 Most practitioners prefer modelling COGS and OPEX costs 
 as Percentage of Revenue. 
 And this can be a viable approach, especially in long run. 
 Cash Flow Impact of Balance Sheet Items include,
 Working Capital investment will represent significant Cash
 tied up into the project. 
 That is Inventory, Trade Receivables, Trade Payables. 
 The Days Technique would allow to forecast 
 the items inline with Revenues and COGS assumed earlier. 
 Consider forecasting other items if they have a material cash impact.
 In certain legislations, can deduct certain costs earlier,
 which will give rise to deferred tax liabilities. 
 If so and amount is serious,
 we should take deferred taxes into consideration 
 when coming up cash flow estimations. 
 There are Two Sources of Income At the End. 
 Residual Value and Working Capital. 
 One deriving from selling the Residual Assets related to project,
 and another from freeing up of Working Capital. 
 Terminal Value is a function of the degree of obsolescence. 
 If it is an Asset that ages quickly then the Terminal Price 
 will be a small fraction of its original price. 
 However also possible to have an Asset that is 
 also valuable and can be sold at a good price. 
 Usually companies use the services of specialized personnel 
 who can derive the value of such Assets 
 and come up with a concrete value. 
 In some models, Terminal Value can be as low as 3-5%
 and in others as high as 40%. 
 Amount of Working Capital Freed Up
  = Working Capital in Last Year of Projections
<br>


Moving Car Production Plant from Vietnam to Italy.
Capital Budgeting Practical Exercise: 
 These days companies try to maximize their value,
 by investing in the best possible projects.
 To be able to compare different projects financially,
 - Build a plant
 - Invest in R&D
 - Hire more personnel
 - Modernize the auto fleet
 firms need Capital Budgeting Models. 
 Consider a situation where an Auto producer company in Italy,
 tries to access whether it would make financial sence,
 to move some of its production to Vietnam. 
 Which could mean 
 - Lower cost of personnel
 - Lower taxes
 - Cheaper raw materials
 The board members require a formal financial assessment. 
 Including Best, Base and Worst case scenarios. 
 To have a scene of possible risks a company will face,
 if things don't go well. 
 And for greater precision a 10y model is required. 
 The main source of income a company expects to generate 
 from this endeavour is savings derived from 
 the cheaper production of automobiles. 
 Production Price (Italy) - Production Price (Vietnam)
  = Savings per car
 We will compare the end price of one car produced in Italy,
 and the end price of one car produced in Vietnam. 
 The difference between the two gives us the actual Savings Per Car. 
 The Operations and Controllership teams have done 
 the heavy lifting of estimating the Cost Per Car. 
 Our job is to model the rest, that is Build a Financial Model,
 and come up with a conclusion that tells us if the project 
 generates or destroys value. 
 For the Capital Budgeting Model we will use following figures,
 also called Drivers,
  Selected Case Input
   - Best, Base and Worst case
  Expected Long-Term Inflation (annual)
   - Italy   1%
   - Vietnam 3%
   Inflation is needed because it effects everything.
   The price of products in countries will grow at that rate.
   Italy has a lower expected inflation in the long term. 
  Price of Production (EUR)
   - Italy    15,500
   - Vietname 11,000
   An output received from business partners 
   in Operations and Financial Controlling.
   They have carefully studied the various costs sustained 
   in Vietnam and expect the company will be able to realize 
   4500 EUR of savings per car. EUR 15.5K-11K = EUR 4.5K
   Which is a considerable amount.
  Estimated Initial Investment (EUR)
   - Best case  320 mill
   - Base case  350 mill
   - Worst case 380 mill
   or overall CAPEX for Investment Project.
   Operations Team express significant uncertainties.
   That initial forecasts are 350 mill, 
   but could fluctuate 30 mill in either direction. 
  Useful life (years)
   - 10 
   for all CAPEX investments. 
   Which is rarely the case in practice,
   but helps us reduce complexity without oversimplifying.
  Working Capital (Italy) (Days)
   - DIO                25
   - DPO                30
   - Net Trading Cycle -05
   Given only production figures are concerned,
   DSO figures are not included. 
   The firm has a favourable Net Trading Cycle in Italy,
   which means it can finance part of its operations 
   with suppliers capital, given that DPO > DIO
  Financing Facilities 
   - Senior Facility (EUR)			  200,000,000
   - Interest Rate Senior Facility (%)          5
   - Repay Senior Facility in (years)          10
   - Use as much debt as possible
   are the financing terms the company will use 
   to finance the initiative. The firm will use
   a mix of Debt and Equity. 
   The loan terms have been pre-agreed with bank. 
   They will provide a loan 
   that can go up to a maximum of EUR 200 mill.
   The rest will be covered with Equity. 
   Management has agreed to use 
   as much debt for this initiative as possible. 
   The interest rate for financing the facility is fixed at 5%.
   Higher than market rates, 
   but gives stability predicting future interest rates.
  Loan Repayment Schedule
   - Y0  0%, Y1  0%, Y2  5%, Y3  10%, Y4 10%, Y5 10%, Y6 10%,
     Y7 10%, Y8 10%, Y9 10%, Y10 10%
   The loan must be paid under this reinvestment scheme. 
   Bank agreed to forego interest payments in year 0.
   But with a Covenant,
   " Production should not be less than 15K cars per year.
     Otherwise penalty of EUR 1 mill per year. "
   This is to ensure the firm is serious
   about producing cars at this facility. 
   And the Covenant is waived for year 0 only,
   as this is when construction takes place,
   and is impossible to produce any units. 
  Tax Rate (%)
   - 30
   If earnings before tax is negative,
   tax will not be paid,
   and will assume company cannot carry these Tax losses forward.
  Residual Value of Project (EUR)
   - 100,000,000
   The Operations Team has indicated that 
   according to their estimations
   the plants residual value
   after the 10y projections will be 
   EUR 100 mill minus the Residual Debt Outstanding. 
 When the company's executives 
 considered moving production to Vietnam,
 instead of staying in Italy,
 they had one thing in mind.
 Cost Savings. Initial research indicated production in Vietnam
 could cost as low as 2/3 the costs sustained in Italy. 
 Developing economies offer cheap labor, 
 low prices of electricity and raw material
 and gov support for licenses and authorizations. 
 After a deeper analysis Financial Controlling came up with
 a more precise figure to work with.
 If the price of production in Italy is EUR 15.5K,
 and the cost of same car in Vietnam is EUR 11K,
 assuming the same price for various volumes. 
 But in actuality the actual cost per unit
 would depend on number of units produced in a plant.
 After comparing Prices Per Unit,
 the next step to access Production Volumes. 
 The operations team suggests 3 main cases,
 - Best Volume  22,000
 - Base Volume  20,000
 - Worst Volume 18,000
 The panned volume depending on the demand expected 
 for their cars for next 10years. 
 Productivity (as a %)
  - Best  Case Y1 85%, Y2 87%, ... Y9 84%, Y10 83%
  - Base  Case Y1 80%, Y2 85%, ... Y9 82%, Y10 81%
  - Worst Case Y1 75%, Y2 80%, ... Y9 77%, Y10 76%
  is a variable the operations team used 
  to describe their expectation regarding 
  plant's operability in each year. 
  It is reasonable to expect a slower start,
  then a ramp up of production for next few years,
  and as the plant ages production slows down.
 To obtain Volumes of Production per each scenario,
 we multiply Base Volume by 
 expected level of Production for that year.
 Volume (in units)
  - Best  Case Y1 85%*22K, Y2 87%*22K, ... Y10 83%*22K
  - Base  Case Y1 80%*20K, Y2 85%*20K, ... Y10 81%*20K
  - Worst Case Y1 75%*18K, Y2 80%*18K, ... Y10 76%*18K
 Now we can update Price of Production Per Car in 2 countries,
 with the expected inflation. 
 Price of Production (EUR)
  - Italy   Y1 15.5K, Y2 15.5K*(1.01)^1, Y3 15.5K*(1.01)^2,...
  - Vietnam Y1 11.0K, Y2 11.0K*(1.03)^1, Y3 11.0K*(1.03)^2,...
  - Savings Per Unit = Y1 4.5K, Y2 4.325K, Y3 4.142K, ...
                     = Italy - Vietnam (post inflation for each year)
  This is the actual income that would be made,
  and when creating a budgeting model,
  We will use this figure as the basis for our EBITA. 
 Total Savings
  = Saving Per Unit * Expected Annual Volume for each case in Units 
 Savings are the Operating Income for project. 
 Now we work on Preparing a Fixed Asset Roll-forward Schedule.
  Estimated Initial Investment (EUR)
   - Best case  320 mill
   - Base case  350 mill
   - Worst case 380 mill
  Useful life (years)
   - 10
   We are assuming all Asset categories with same useful life.
  Investment Plan
   - Y0 80$, Y1 10%, Y2 10%, Y3 to Y10 at 3% per year
   100% of investment in first 3 years 
   and additional 3% per year afterwards. 
  Fixed Asset Roll-forward (EUR)
   - Beginning PP&E (Each Year 1 to 10): 
       For Year 1:
        Best, Base and Worst Estimated Initial Investment 
        * Investment Plan Percentage for Year 0 (80%)
       For Year 2-10:
        Ending PP&E of Year 1-9 respectively
   - CAPEX:
       For Year 1:
        Best, Base and Worst Estimated Initial Investment 
        * Investment Plan Percentage for Year 1 (10%)
        ... Until Year 10
   - D&A:
       For Year 1 to 10 is calculated in D&A Schedule below.
   - Ending PP&E:
       For Year 1 to 10 is Beginning PP&E + CAPEX - D&A
   We use the Excel Choose Function for each case. 
  D&A Schedule (EUR)
   - Year 1: Beginning PP&E Y1 / 10
   - Year 2: Beginning PP&E Y1 / 10 + CAPEX Y1
   - Year 3: Beginning PP&E Y1 / 10 + CAPEX Y1 + CAPEX Y2
   ...
   - Year 10: Beginning PP&E Y1 / 10 + CAPEX Y1 + ... + CAPEX Y9
 Now we calculate the impact of Working Capital
  Necessary because both plants, Italy and Vietnam, 
  will need a different Working Capital.
  DSO is not considered as not related to production of plants. 
  DIO Vietnam
   Best Case  = 45
   Base Case  = 50
   Worst Case = 55
  DPO Vietnam
   Best Case  = 25
   Base Case  = 30
   Worst Case = 35
  Working Capital Italy
   - DIO = 25
   - DPO = 30
   - Net Trading Cycle = -5
  Working Capital Vietnam
   - DIO = 45
   - DPO = 25
   - Net Trading Cycle = 20
   The DPO is higher because it is less favourable in a new location.
   The DIO is higher because of a longer storage period,
   as it is a longer distance from place it is sold. 
  Extra Working Capital (EUR)
   - Extra Production Value:
      = From Savings Forecast,
       Volume expected to be produced each year 
       * Price of Production Vietnam of each year 
         (inflation variance)
   - Delta Net Trading Cycle (days)
      = Net Trading Cycle Vietnam - NTC Italy = 25
      Assumed to be constant for each of 10 years
   - Working Capital
      = ( Extra Production Value (for that year) 
          * Delta Net Trading Cycle ) / 360
   - Delta Working Capital
      = Current Year - Previous Year Working Capital
      Year 1 is 14.2 mill
      Year 2 is 15 mill - 14.2 mill
      Year 3 is 15.8 mill - 15 mill
      ...
 Now we look at Financing
  Project is financed by both Equity and Debt.
  Investment in Year 0 (EUR)
   - 256,000,000
  Financing Facilites
   - Debt Facility (EUR) = 200,000,000
   - Interest Rate Debt Facility = 5%
   - Repay Debt Facility = 10years
   Debt Facility will be amortized in 10 years.
  Repayment Schedule 
   - Y0 0%, Y1 0%, Y2 5%, Y3-Y10 10%
  Financing (EUR)
   - Beginning Debt: Y0 200m, Y1 Ending Debt of Y0, 
                     Y2 Ending Debt of Y1, ...
   - Repayment: Y0 0, Y1 0, Y2 10m, Y3-Y10 20m
   - Ending Debt: Beginning Debt - Ending Debt (for each year)
   - Interest Expenses: Beginning Debt * Interest Rate (for each year)
      Interest Expenses fall over time as debt is repaid.
      Bank agreed to forego interest expenses 
      during construction stage. 
   - Volume:
      From Saving Forecast Sheet (for each year). 
   - Volume lower than 15K (for each year)?
      =IF(E10=0,0,IF(E19="Yes",1000000,0))
   - Covenant Penalty:
      0 for all years as Volume never below 15K.
   This is how we model Debt. Now to calculate Equity.
   - Net Cash Flow
   - Equity Financing
   To calculate Equity we must calculate the firm's net cash flow.
   If Cash Flows become negative at a certain point in time,
   the company must increase its Equity investment. 
 Now we make the P&L
  This will allow us to find the taxes owed by company. 
  As we cannot calculate Cash Flow without taxes. 
  We are not interested in Net Income 
  given it is an artificial measure in this case.
  We are comparing the difference 
  between the two production plants
  and it makes little sense to measure 
  in terms of actual bottom line profitability. 
  P&L (EUR)
   - Savings (EBITDA): Y1-Y10 taken from Savings Forecast
      It compares cost that would have been sustained 
      in Italy vs Vietnam, and gives us an operating profit margin. 
      We will assume that OPEX has been included in Savings. 
   - D&A: Y1-10 taken from Fixed Asset Roll-Forward
   - EBIT: Y1-10
      = Savings (EBITDA) - D&A , (for each year)
   - Interest Expenses: Y1-Y10 taken from Financing
   - Covenants: Y1-Y10 taken from Financing
   - EBT: Y1-Y10
      = EBIT - Interest Expenses - Covenants , (for each year)
   - Taxes: Y1-Y10 
      = Taken from Drivers (30%) * EBT , (for each year)
   - Net Income:
      = EBT - Taxes
 Now we make the Cash Flows
  Cash Flows (EUR)
   - Savings per unit (EBITDA):
      Taken from Saving Forecast for Y1-Y10
   - Taxes:
      Taken from P&L for Y1-Y10
   - Delta Working Capital
      Is extra working capital we will have to invest,
      when moving the plant from Italy to Vietnam.
      And to adapt to the changing supplier 
      and inventory time conditions. 
      Taken from Working Capital for Y1-Y10
   - CAPEX
      Taken from Fixed Asset Roll Forward for Y1-Y10
   - Operating Cash Flow
      = Savings Per Unit (EBITDA) 
        - (Taxes + Delta Working Capital + CAPEX)
   - Debt Repayment 
      Taken from Financing for Y1-Y10
   - Interest Expenses
      Taken from Financing for Y1-Y10
   - Covenant Penalty
      Taken from Financing for Y1-Y10
   - Increase of Equity
   - Project Cash Flow
      = Operating Cash Flow
        - (Debt Repayment + Interest Expenses + Covenant Penalty)
      Now we have arrived at Net Cash Flow. 
      The actual amount of money 
      that will go in and out of firm's bank account. 
   - Residual Value
      = Residual Value of Project (Taken from Drivers) 
        - Ending Debt at end of Year 10 (Taken from Financing)
      That is EUR 100 mill - Outstanding Debt
 Now we calculate the Equity necessary for the project
  We shouldn't presume the project will need Equity in year 0.
  If Cash Flow in 1 year become negative, 
  company will have to fund the project with new equity. 
  To calculate such Equity increases,
  We go to Financing Sheet, and start from year 0,
  which is Cash Flow Y0,
  and below we calculate Equity for Y0. 
  Equity in Year 0 = 
   (- Net Cash Flow in Year 0) + Ending Debt at Year 0
  Financing
   ...
   Net Cash Flow 
    - Taken from Cash Flow (Projected Cash Flow Y0-Y10)
   Equity Financing 
    - IF(Net Flow Flow for the year is > 0,
         then Equity Financing for this year
         is previous year Equity Financing,
         else Equity Financing for the year
         is (previous year Equity Financing - Net Cash Flow) )
    That is if Cash Flow > 0 then Do not raise Equity.
    And if Cash Flow < 0 then Raise Equity to same amount
    to cover the negative cash flow and repay liabilities due.
 Now we calculate the Projects Weighted Average Cost of Capital
  To be able to Discount Cash Flow, 
  we need an appropriate Discount Rate. 
  The discount factor that takes into consideration,
  both Debt and Equity Investors is called
  WACC or Weighted Average Cost of Capital. 
  Which represents the opportunity cost that investors sustain
  for investing their funds in the firm.
  WACC = (D/(D+E)) * k[d] * (1-t) + (E/(D+E)) * k[e]
  where D = Amount of Debt Financing,
        E = Amount of Equity Financing,
        k[d] = Cost of Debt, k[e] = Cost of Equity
        t = Tax rate
  The 2 weighting components of WACC are (D/(D+E)) and (E/(D+E)).
  And the sum of these two components is 1. 
  If D>E the Debt will have higher impact on WACC and conversely.
  The third factor of WACC is (1-t),
  that takes into account that interest expenses are deductible,
  and hence cost of debt of firm is lower than it seems. 
  WACC
   Cost of Debt 
    - 5% , from Drivers
   Risk Free Rate in Vietnam 
    - 3% , from Drivers
   Tax rate 
    - 30% , from Drivers
   Market Rate Premium in Vietnam
    - 6% , from Drivers
   Comparable Companies | Leverage | Beta
    - Company A | 80% | 0.60 , from Drivers
    - Company B | 90% | 0.65 , from Drivers
    - Company C | 85% | 0.57 , from Drivers
    All data above is collected by Operations Team
   WACC (EUR)
    - Debt Financing 
       Taken from Financing , for each year
    - Equity Financing
       Taken from Financing , for each year
    - Total Financing
       = Debt + Equity
    - Debt Financing %
       = Debt / Total Financing , for each year
    - Equity Financing %
       = Equity / Total Financing , for each year
    - Total Financing %
       = Debt % + Equity %
   Comparable Companies 
    - Average Leverage
       = Company A-C Leverage / 3
    - Average Beta
       = Company A-C Beta / 3
   Project Beta
    - Debt/Equity
    - Bata Unlevered
    - Project Beta
   Cost of Equity
    There are many ways to calculate a company's Cost of Equity.
    The CAPM is most popular. 
    The Capital Asset Pricing Model (CAPM) introduced in 1960s,
    but remains valid to this day and age. 
    k[e] = r[f] + Beta * Market Risk Premium
    The Capital Asset Pricing Model suggests that 
    a company's Cost of Equity.
    is the Risk Free Rate (r[f]) + Beta * Market Risk Premium.
    We must make sure to use project-specific parameters 
    when applying CAPM for Capital Budgeting.
    When it is applied in a Capital Budgeting context,
    we have to be careful 
    and consider parameters relevant to project. 
    We have to apply Risk Free Rate, a Beta and Market Risk Premium,
    which are Project Specific. 
    r[f] or Risk Free Rate in an economy 
    is the rate of return of an investment with zero risk(100% secure)
    that an investor would expect from a financial security,
    that contains zero default risk. 
    The investor buys the security,
    and can be absolutely certain that he will be repaid on time,
    and in full. In reality very few securities can be considered 
    risk free, but most practitioners 
    use the yield of a 10 year government bond 
    in order to approximate this measure. 
    The rational behind using a 10y and not a 3 month bond
    is that the valuation of the firm is a multi year exercise.
    Hence the risk free rate that is used,
    shoulden't reflect a period as short as 3 months. 
    Practitioners approximate risk-free 
    with the yield of a 10-year government bond 
    In the Drivers Sheet 
    we have Risk Free Rate in Vietnam as 3% and Italy as 2%,
    derived from bond securities of the respective governments. 
    As the Project is for Vietnam we use Vietnam's risk free rate. 
    The next component is Beta which is a statistical measure
    which is Cov(r[i];r[m])/Var(r[m]), i the investment, m the market,
    that is how a financial security behaves,
    with respect to the rest of market. 
    Can find Company's Stocks Beta on sites like Yahoo Finance. 
    A Beta < 1 is Defensive or less volatile than market, 
    Beta = 1 is Neutral or as volatile as market, 
    that is if market gain 1%, stock also gains 1%,
    Beta > 1 is Aggressive or more volatile than market,
    that is if market gains 2%, stock gains 2.5-3%.
    A company's Beta will typically have a value ranging between 0-2.
    In the Drivers Sheet we see the company's Beta is 0.9.
    But this is the entire firms Beta, which can be misleading. 
    A preferable practice is calculating a Project Specific Beta,
    reflecting the actual market conditions 
    of doing business in Vietnam. 
    Which is why the Operations Team provides 
    a list of comparable company Betas 
    performing same activity in Vietnam. 
    We have their Leverage and Beta. 
    So we use the Average Leverage and Average Beta. 
    And then Adjust the Average Beta obtained 
    to the Leverage of our project. 
    For this we use the formula for Unlevered Beta.
      Beta[Unlevered] 
       = Beta[levered] / (1+(1-t)*(D/E)) ,
    where t = tax rate ,
    Beta[levered] = Average Beta of comparable companies ,
    D/E = Average Leverage of comparable companies ,
    Unlevered Beta is Beta of company with no Debt on balance sheet,
    we divide Average Beta of comparable companies, 
    by 1+(1 - tax rate) * Average Leverage of comparable companies.
    Unlevered Beta is a Beta which disregards financial leverage. 
    We must now Re-Lever Beta with the Projects Leverage. 
    B[levered] = Beta[Unlevered] * (1 + (1-t) * D/E)
    The final variable we need to calculate the cost of Equity,
    is Market Risk Premium. Which is the extra return,
    investors in a given market require in order to invest in equity
    and bear additional risk. 
    It has been proven to vary between 4.5-6.5% historically. 
    The Market Risk Premium in Vietnam is 6%.
    Cost of Equity or k[e],
     is given by Risk-Free Return or r[f]
     + (Project specific Beta * Market Risk Premium )
    k[e] = r[f] + Beta * Market Risk Premium
    We can also calculate WACC while we are at it
    WACC = (D/(D+E)) * k[d] * (1-t) + (E/(D+E)) * k[e]
    k[d] = Cost of Debt
    k[e] = Cost of Equity
 Now we work to find the Discounted Cash Flows
  This is necessary because it is the basis for calculating 
  the present value of the project and deciding 
  whether to go through with it. 
  Discounted Cash Flows
   - Selected case: Best, Base or Worst
   - Residual Value: 70,000,000 or Terminal Value
   - Net Cash Flow: Y0-Y10 Taken from Cash Flow Sheet
   - Cost of Equity: Y0-Y10 Taken from WACC sheet
   - Discounted Cash Flow: Y0-Y10
      = Net Cash Flow / (1 + Cost of Equity)^Year
   - Present Value Residual Value:
      = Residual Value / (1 + Cost of Equity Y10)^10
      is only for Y10
   - Discounted Cash Flow with Residual Value:
      = Discounted Cash Flow + Residual Value
   Whenever the Cash Flows being Discounted 
   are the ones going to Shareholder,
   you must discount them by Cost of Equity. 
   It is incorrect to discount by WACC,
   because interest expenses have already been taken into consideration in the Net Cash Flow.  
   On the other-hand if Operating Cash Flows are being discounted,
   due to the fact that they 
   take into consideration interest expenses,
   it would be perfectly fine to discount WACC.
   So for Cash Flow to Equity, we discount them by Cost of Equity.
   For Cash Flow to the Firm, we discount them by WACC. 
   The residual value shows us the projects worth 
   at the end of the tenth year.
   Now that we have discounted all future cash flows 
   and obtained their present value, we are ready
   to apply the various methods that will give us 
   an indication of whether the project makes sense 
   from a financial perspective.
 Now we will apply VPN and IRR techniques 
 and also perform analysis of sensitivity.
 We have Discounted Projects Cash Flows,
 We have calculated WACC and Cost of Equity,
 and decided to use Cost of Equity as a Discounting Factor.
 Before that we obtained the actual Cash Flows 
 for the entire 10 year forecast period. 
 The first rule of thumb for any investment project like this one,
 is to see its NPV or Net Present Value. 
 If the sum of Initial Investment and Discounted Cash Flows,
 is lower than 0, then there is no point 
 in continuing discussions further. 
 That is the project destroys value rather than creating it. 
 So in case 3 that is Worst case,
 where Sum of Discounted Cash Flows or NPV is EUR -17 mill,
 we will definitely recommend to the Board to Avoid the Project. 
 In case 1 that is Best case,
 the NPV is EUR 122 mill, 
 the project looks like a very good opportunity.
 And in case 2 or Base case,
 the NPV is EUR 63 mill,
 which might or might not be attractive 
 if there are other options to weigh that could generate more money.
 If the company aims to invest in projects that earn 
 a hurdle rate or required rate greater than 10%,
 and knowing that this opportunity has EUR 63 mill doesn't say much.
 We simply don't know if this is the case by considering NPV only.
 Instead we should calculate IRR, and see its value. 
 And then compare IRR with other projects. 
 We make a new line under Net Cash Flow and above Cost of Equity
 in Discounted Cash Flow Sheet called Net Cash Flow + Residual Value. 
 We apply the IRR Excel function, =IRR(Y0 NCF+RV : Y10 NCF+RV)
 to get 17.7% in Base case, 3.7% in Worst case, and 37% in Best case.
 IRR or Internal Rate of Return
  - Best case: 37%
  - Base case: 17%
  - Worst case: 3.7%
   => EXCEL => =IRR(Y0 NCF+RV : Y10 NCF+RV)
   NCF+RV = Net Cash Flow + Residual Value
 Sensitivity Table
  We use it to test how IRR 
  is impacted by different amounts of Residual Value.
  We make a table such as 
  		       | 17.7%
  	70,000,000 |
  	80,000,000 |
  	85,000,000 |
  	95,000,000 |
  	115,000,000|
  Then select the entire table,
  Go to EXCEL "DATA" Tab, "What if" and "Data Table",
  then for "column" option we select the Residual Value,
  which is 70,000,000. Giving us the new Sensitivity Table below:
    		   | 17.7%
  	70,000,000 | 17.7%
  	80,000,000 | 18.2%
  	85,000,000 | 18.4%
  	95,000,000 | 18.9%
  	115,000,000| 19.8%
  where we can vary the IRR % using case based Best, Base, Worst.
  This tells us how strong certain hypothesis is in out model,
  and help us identify the main drivers that have financial impact. 
  By adjusting the respective scenarios we are able to see the 
  implications of going through the project 
  in different states of world.
 And that is what financial modelling is all about,
 allowing us to create a credible simulation of different scenarios,
 and hence facilitating an improved decision making process
 based on more information. 
<br>


Tesla Company Analysis:
 First we look at the Drivers Sheet of our Model.
 Some of the parameters in Drivers we will be looking at are:
  - Selected Case (BBW) , - Company , - Currency 
  , - Domestic Country , - 10-year Treasury Yield (Sep 27 2018)
  , - Market Risk Premium US , - Company Beta (Sep 27 2018)
  , - Tesla Share Price (Sep 27 2018) , Bond Yield (Sep 19 2018)
  , - Corporate Tax Rate , - Expected Inflation
 It is a good practice to add a Drivers Sheet to a model,
 as this is a nice way to group or organize all inputs 
 that have been factored into the model. 
 Drivers
  - Selected Case: Given that we are trying to create 
     a flexible model, the idea here is to add a field 
     which would allow us to change scenarios. 
     It is a good idea to include at-least a few scenarios 
     and analyze different states of the world 
     by changing the selected case. We will have 3 scenarios 
     designated with numbers 1(Best),2(Base),3(Worst).
     It will be very insightful to see how Tesla's financials,
     and overall cash flow look in each of these scenarios. 
     And later on when model is ready will be we able to switch 
     between scenarios from this EXCEL cell. And given we want only
     3 possible values, we go to EXCEL "Data" tab, 
     use EXCEL "Data Validation", 
     to make a list of these three values.
  - Company: Tesla Inc.
  - Currency: USD
  - Domestic Country: United States
  - 10-Year treasury yield (Sep 27 2018): 3.07
     Found by just googling it. 
  - Market Risk Premium US: 5%
     Historically has been proven to be between 4.5% and 5.5%.
  - Company Beta (Sep 27 2018): 0.78
     Found on Google or Yahoo. 
  - Company Share Price (Sep 27 2018): 307.80
  - Bond Yield (Sep 19 2018): 7.5%
     This is the rate of return offered for buying 
     the company's debt on the market. 
     This is a really good approximation 
     on the market rate of cost of Debt. 
  - Corporate Tax Rate: 30%
     Taken as an approximation of corporate tax rate in US. 
  - Expected Inflation: 2%
     Taken as an approximation , 
     as the expected long term value of Inflation. 
 Now we must look at historical inputs 
 and how we will organize them in our model. 
 For P&L input and Balance Sheet input 
 we have already done this before in previous Tesla Exercise 
 to see what the concerns of Tesla's Financials are. 
 Can be taken from a company's 10-K annual statement each year
 and 10-Q quarterly statement. 
 The Workings EXCEL Tab will helps us separate 
 the model's actual workings, where we forecast 
 and make assumptions about the future. 
 Also a EXCEL tab for Income Statement Items,
 an EXCEL tab for Balance Sheet Items,
 an EXCEL tab for Automotive Business Line,
 which accounts for 80% of company's revenues of 2017.
 We will be using figures from an article that states 
 Teslas planned upcoming models and lineup 10 year from now,
 and its expected orders, price, revenue,
 and profits based on 20% and 25% Gross Margin. 
 " https://cleantechnica.com/2017/12/25/tesla-vehicle-revenue-2022-73-7-billion/ ".
 As Revenue is Number of vehicles delivered * Average Price, 
 we must figure out which models, Tesla will sell in 10 years. 
 Company currently offers Models S, 3, X, 
 and has announced Y, Roadster 2, Pickup, Semi. 
 Model Y expected at end of 2019, 
 but likely serious production will not start till 2020. 
 In first half of 2018, H1 2018, Tesla delivered 26,620 model 3s,
 a considerable achievement since 2017 was just 1,764 model 3s.
 In sep 2018 was reported that Tesla ramped up production
 and delivers 6000 model 3s a week. 
 For the H2 2018 forecast we will be conservative and say 4K a week,
 so 26 weeks * 4K is 104,000, making full year figures H1+H2 2018.
 We will group together model S and X as they have same price,
 and Tesla also reports both delivery together. 
 In first half of 2018, H1 2018, Tesla delivered 44,100 model S&X,
 and latest guidance says they expect to deliver 100K for 2018. 
 Which means H2 numbers were higher likely due to production struggles.
 The y-o-y growth % can now be found using (= (2018/2017) - 1)
 Model S and X together grew -1% in deliveries from 2017 to 2018.
 Model 3 grew 7305% in deliveries from 2017 to 2018.
 No other models were delivered in 2018 so we say "n.a".
 In 2019, going by 5K deliveries a week for model 3 will mean,
 5K * 52weeks = 260K, which is a 99% growth y-o-y.
 We take assumed growth after introduction as same as Model 3,
 then 10% for 2 years after that, and 5% for 2 years after that 
 and 2% onward. As we don't have the third year we manually forecast 
 at 8K a week, that is 416K in 2020 or 60% y-o-y. Now we forecast 
 using above for future y-o-y. Model S and X has been selling a while,
 and we assume a constant 2% y-o-y growth for all years afterwards.
 We apply this to obtain the delivery volume for forecasted period.
 For Model Y forecast we use Model 3 historical figures,
 and use same growth trajectory. For Roadster 3 we assume a sale 
 of 500 for first year, but we don't assume the growth rate 
 used on other cars as its intended for a richer audience.
 We assume 100% for second year, 50% for third year, 
 then the usual growth cycle used for other cars. 
 For Tesla Pickup and Tesla Semi we assume 250 
 for each for first year. Then we assume the same growth pattern 
 as model 3 and model y. These are commercial vehicles,
 but starting from a low first year delivery volume doesn't 
 make the forecast too aggressive. 
 The number of vehicles delivered is the foundation of our model. 
 We now consider the delivery estimates and visualize the growth.
 We have a tab "Deliveries Development" visualizing the deliveries.
 The chart shows the strongest growth happening 2019 to 2022. 
 That is when new Tesla models will be introduced to market,
 and when we assume the company surpasses the 1 mill vehicles
 delivered per year mark. If Tesla is to become a global powerhouse,
 these are the years that this should happen.
 In tab "Deliveries Comparable" we compare the numbers 
 to other industry leaders. We don't compare with Jaguar,
 Porch, Ferrari, ... as they are a niche market. 
 We look at companies like GM, Ford, Fiat Chrysler, BMW and Volkswagen.
 They deliver 6.8 mill vehicles on average. 
 BMW is smallest at 2.5 mill a year. 
 It is always a good practice to compare forecast results,
 with the one of industry peers as done here. 
 This gives the valuation prepared a stable foundation,
 and is a useful sanity check. It may take a significant 
 amount of time to find this information from financial statements,
 but this improves the quality of our output significantly. 
 Going forward we use this as a sanity check and hypothesis. 
 Now that we have forecasted Teslas Vehicle deliveries 
 over the next 10 years, now we focus on the average selling price 
 of the automobiles and trucks. 
 Different configurations for each vehicle can vary the price,
 but our most practical approach is to apply reasonable 
 average prices for each model and obtain a good enough approximation,
 of the revenue Tesla will make. From the article before 
 from cleantechnica, it included the average price estimation.
 In reality one team of people prepare a market study,
 closely examining average prices, estimating demand and top line. 
 And then a different team carries out the valuation exercise.
 Model 3 we take 42K usd, Model S and X we take 87.5K usd,
 Roadster 2 at 230K usd, Model Y at 50K usd, Pickup at 63k usd
 based on comparable gasoline pickups + battery,
 and Semi at 200K usd based on articles.
 We can now estimate Revenue. Our goal is to see what would happen
 to Tesla's Revenues if the average selling price, 
 or number of vehicles delivered was different to whats predicated,
 using Best(102%), Base(100%) and Worst(98%) cases.
 To tie the percent cases to the drop down 1-3,
 we use the EXCEL "Choose" function, 
  =choose(index 1 or 2 or 3, 102%, 100%, 98%)
 Now we calculate Tesla's automotive gross profit. 
 And what portion of Automotive Revenues become margin 
 after the company takes production expenses into consideration.
 Given we worked out Revenue for 6 different vehicles types,
 we can calculate a separate Gross Profit Margin for each of them.
 We can estimate a reasonable GP% for each model,
 based on the margin of similar comparable companies selling
 similar vehicles on the market. 
 For each model type we consider the G.P. Margin of three comparable 
 companies. It would be preferable to select specific model types
 from each company but such information is not available to outsiders.
 For Model 3 its GM, Ford, Fiat Chrysler.
 For Model S and X its BMW, Mercedes, Volkswagen.
 For Model Y its BMW, Mercedes, Volkswagen.
 For Roadster 2 it's Jaguar, Porch, Ferrari.
 For Pickup its GM, Ford, Fiat Chrysler.
 For Semi its Scania, MAN, Paccar.
 The detail we use, the more stable our model is. 
 Taking the data of Gross Profit Margin
 from each company's financial statements 
 gives us possible Average Gross Profit Margin for each model type. 
 Now we will apply these figures with Teslas Revenue
 to obtain Total Automotive Gross Profit Figures in Absolute terms.
 We add 1.5% for our Best case and subtract 1.5% for our Worse case,
 from the Average Gross Profit Margin we found for each model type. 
 This leaves room for some optimism and pesimisim for our model
 depending on who uses it, and how conservative their estimates are
 about Teslas ability to achieve the planned level of G.P. Margin is.
 We use the Choose function for case selection.
 Now we just multiple the Revenues * Gross Profit Margin %.
 Now we calculate Tesla's Cost of Sales for the Forecast period. 
 Gross Profit = Revenue - Cost of Sales
 Cost of Sales = Revenue - Gross Profit
 We add a minus sign in-front of formula as we are referring to costs
 and they are negative by definition.
 Now we forecast Revenues from Energy and Others business lines.
 Since we don't know the nature of whats included in Energy generation 
 and storage, as well as in services and others, we forecast
 the two together in Total Energy and Other. 
 Since SolarCity is merged, we ignore the sub-values in forecast 
 and give "n.a".
 Energy Revenue 2019 
  = Energy Revenue 2018 * (1 + Growth Rate)
 Now we will forecast Cost of Sales and Gross Profit 
 for these business lines. 
 Operating Expenses are the costs that a business incurs during 
 the process of performing normal business operations. 
 OPEX is not equal to Cost of Sales. 
 Examples of Operating Costs:
 - Research and Development , - Accounting , - Top Management
 , - Rent , - Utilities , - Sales , - Show Rooms , - Advertising
 Now we will forecast Tesla's Operating expenses 2019-2028.
 We consider that Tesla is not that young of a company,
 but it is not a mature auto producer either. 
 It continues to grow at a rapid pace each year.
 Chances are it will soon benefit from economies of scale
 larger auto producers benefit from.
 Such economies of scale include being able to diminish Fixed Costs,
 by selling more auto units (higher Volume Sold),
 therefore decreasing costs per unit. 
 The amount of OPEX as a percentage of Revenue the company spends now,
 is not going to stay the same. At some point, OPEX incidence on Revenue
 is going to decrease. Because Revenues are going to grow faster
 compared to OPEX. We cant say exactly by how much,
 but we can look at comparable Auto producers. 
 When we take take Adj. Average from Average we exclude 
 the outliers which have a significantly higher or lower OPEX.
 Which gives 12%. Best cast at 10% and Worst at 14%.
 We use the choose function to change % by selected case.
 OPEX = (OPEX as % of Revenue) * Revenues
 For 2018 we take average of previous years. 
 Now we forecast PP&E.
 Which is one of the most challenging aspects when integrating 
 a three statement financial model. 
 The Property, Plant and Equipment sheet is also where
 we calculate Depreciation and Amortization. 
 It links the P&L in Balance Sheet. 
 To forecast PP&E we take into account beginning PP&E. 
 Ending PP&E 
  = Beginning PP&E + CAPEX - D&A
 The more a company spends on CAPEX and less it spends on D&A,
 the higher its Ending PP&E will be after a given period. 
 If the firm does not spend a significant amount on CAPEX,
 its D&A is higher, then its Ending PP&E 
 will be lower than Beginning PP&E. 
 Two main ways to forecast CAPEX:
 - Model as a % of Beginning PP&E
 - Model as a % of Revenues.
 The amount of CAPEX spent by the company will be a function of 
 beginning PP&E. 
 If the % of beginning PP&E is reasonable high,
 and Assets are amortized at a slower pace, 
 then this would mean Tesla's PP&E would grow over time. 
 Alternatively we can use Revenues as a driver. 
 Because growing Revenues go hand in hand with expanding 
 and building new Plants, and thus spending on CAPEX. 
 This would also penalize the company as we will assume 
 that every inch of growth on business means 
 new CAPEX needs to be spent, and thats rarely the case. 
 So our main scenario will be Model as a % of Beginning PP&E. 
 We can also use Choose function to model for each scenario. 
 We must now estimate the Drivers for both scenarios. 
 For Capex as % of PP&E for forecasted periods,
 we take average of all previous periods for H2 2018,
 then 60% 2018, 40% 2019, 30% 2020, 20% 2021-2028.
 For Capex as % of Revenue for forecasted periods,
 we take average of all previous periods for 2018-2019,
 then 20% 2020, 15% 2020, 10% 2021-2028.
 Once we are ready with our complete fixed asset roll-forward,
 we compare the D&A figures as a percentage of revenues 
 with the ones of other companies from industry. 
 We can not really do that with CAPEX as that data is hard to obtain. 
 All we need for the model is to apply the % figures to their Driver. 
 We use choose function to select the case 1,
 then (the CAPEX as % of PP&E) * (Beginning PP&E),
 then select case 2, 
 and (the CAPEX as % of Revenue) * (Revenue from that period).
 This is the full year 2018 CAPEX. 
 The CAPEX H218 = CAPEX FY18 - CAPEX H118.
 Building a complete D&A schedule is the more sophisticated way
 to model D&A. The other option is to apply a percentage of Revenues,
 or Beginning PP&E and calculate ending PP&E directly, 
 which is imprecise. So we will in the employ D&A schedule. 
 Two of the most important inputs needed for this are
 expected Useful life of CAPEX or newly acquired fixed assets, 
 and Useful life of historical acquired fixed assets. 
 We assume both new and legacy assets will be depreciated in 15 years. 
 D&A H2 2018 we have is acquired from D&A of historical assets
 and, D&A of CAPEX H22018. 
 2018 H2Fcst 
  = (((Ending PP&E H12018) / 15) / 2) + ((CAPEX H22018 / 15) / 2)
 We make this negative as its a cost. 
 D&A 2018 = D&A H12018 + D&A H22018
 Ending PP&E for 2018 is Beginning PP&E for 2019. 
 And allows us to obtain CAPEX for 2019. 
 2019Fcst 
  = (Ending PP&E 2018) / 15) + (CAPEX 2019 / 15)
 We take cell references paste to all cells on right for whole period.
 This is because Historical assets and newly acquired CAPEX will be
 depreciated for rest of forecast period.
 See "14 Building a Fixed Asset Roll Forward D&A Schedule.mp4"
 We built our hypothesis on how fixed assets will develop over time,
 using CAPEX as the main diver. However it is difficult to say if 
 numbers we considered are reasonable. It is also difficult 
 to find information about CAPEX of comparable companies. 
 But we need to find a way to conduct a sanity check. 
 For this we calculate D&A as a % of Revenues,
 and D&A as a % of Beginning PP&E. This would make it a bit easier,
 to now compare with comparable companies. 
 As D&A is easier to find in financial statements,
 and is also easier to calculate D&A as a percentage of Revenues
 and Beginning PP&E. With this we must decide if the CAPEX figures
 we have assumed yield a reasonable D&A incidence. 
 Now we will model Tesla's Working Capital Components:
  - Trade Receivables , - Inventory , - Trade Payable 
  , which Together make up - Net Trade Cycle
  , we also look at - DSO , - DIO , DPO , - Net Trade Cycle
 We will model the three using the days technique. 
 Which is a standard method applied by Bankers 
 and Finance Professionals performing Corporate Valuation. 
 Our goal is to understand how many days it takes for Tesla 
 to collect Trade Receivables, keeps Inventory in its warehouse,
 and days to pay Trade Payables to suppliers. 
 Earlier in the study we calculated financial ratios,
 and days for historical period. These values have been linked to 
 Working Capital Sheet. 
 Net Trade Cycle = DSO + DIO - DPO
 For forecasting period we simply take the historical average of each.
 Before we figure out the Trade Receivables, Inventory 
 and Trade Payables for the forecasted period,
 we make a P&L output sheet with format:
  - Revenues = Automotive Revenues + Energy Revenues 
  , - Cost of Sales , - Gross Profit = Revenues - Cost of Sales
  , - Operating Expenses , - EBIT = Gross Profit + Operating Expenses 
  , - Interest Expenses/Income , - EBT = EBIT - Interest Expenses
  , - Taxes , - Minority Interest
  , - Net Income = EBT - Taxes - Minority Interest
 A benefit of having seperate output sheets is that 
 they facilitate printing, and useful when preparing a presentation. 
 We fill the cell data using Sheets prepared earlier. 
 Now that we have a clean output sheet, 
 we continue with the Working Capital Sheet. 
 Trade Receivables = (DSO * Revenues) / 360
 Inventory = (DIO * Cogs) / 360 
 , we make sure figure is positive as all Balance Sheet figures are.
 Trade Payable = (DPO * Cogs) / 360
 Net Trade Cycle = Trade Receivables + Inventory + Trade Payable
 Thus far we have EBIT, Working Capital Estimates, 
 and Capex from roll-forward of fixed assets. 
 Now we calculate UFCF or expected Unlevered Free Cash Flow,
 which will help us determine Tesla's financing needs in future. 
 Cash Flow Sheet:
  - EBIT , - Operating taxes (30%)
  , - NOPAT = EBIT + Operating taxes , - Add-back D&A
  , - Gross Cash Flow = NOPAT + Add-back D&A , where NOPAT is negative
  , - Trade Receivables , - Inventory , - Accounts Payable 
  , - Investments in Working Capital = T.R. + I. + Accounts Payable 
  , where I. is negative , - Capex , - Other Assets , - Other Liabilities
  , Unlevered Free Cash Flow = Capex + Other Assets + Other Liabilities
  , - Interest Expenses , - Delta Financial liabilities 
  , - Delta Equity/Other Equity movements , - Tax adjustments 
  , - Minority Interest , 
  , - Net Cash Flow = I.E. + D.F.L. + D.E + T.A. + M.I.
  We note that Operating Taxes are different from Cash Taxes. 
  NOPAT is Net Operating Profit After Taxes. 
  We add-back D&A as it is a non-monetary expense,
  and will be accounted for in a different way.
  Company will not pay taxes if EBIT is positive,
  which we can add the condition to for cell using Excel "if".
  D&A would be negative but this is Add-back D&A so is positive. 
  When Assets increase, it represents a Cash Outflow,
  that is we invested to acquire the Asset.
  If an Asset decreases, it represents a Cash Inflow,
  that is we sold the Assets and received money for it.
  Liabilities behave in opposite way of Assets. 
  When Liabilities increases, it is as if we have borrowed money,
  and is a Cash Inflow. When Liabilities decreases we think of it
  as repaying of Debt, and is a Cash Outflow or negative Cash Flow.
  Trade Receivables is an Asset and will be negative.
  Inventory is also an Asset and will be negative. 
  Account Payables is a Liability and increase of Account Payables
  is a positive Cash Flow. 
  Capex is negative as it is money we spend. 
  Now we forecast Other Assets and Other Liabilities,
  so that we can find Unlevered Free Cash Flow.
  Not all Assets have to grow proportionally to the business
  as it grows, ex if Tesla registers some Restricted Cash and Securities
  in its Assets, this does not mean the company will have to grow 
  restricted cash and securities as it sells more cars,
  and can be modelled as flat for the entire forecasting period.
  The other option is an item expanding at the same pace as Revenues,
  ex with Prepaid Expenses. First we take the average of its historical
  period and then we apply it to the company Revenues in a given period,
  to obtain the expected Prepaid Expenses for that period.
  Prepaid Expenses 
   = Prepaid Expenses as a % of Revenue * Revenues
  So the two situations are stays flat, 
  or grows at same pace as Revenues,
  with Cash being the only exception. 
  As we wont be able to fill in Cash before we calculate Tesla's 
  actual Net Cash Flow. Operating Lease Vehicles can be modelled as flat.
  Same with Solar Energy System Leased. Such types of operations,
  are not part of the core business. Intangible Assets stays flat.
  We assume that all Other Assets grows as a % of Revenues. 
  Other Assets = Other Assets as a % of Revenue * Revenues.
  Now we do the same for Liabilities. 
  Accrued Liabilities will likely grow as % of Revenues,
  given that it is of an operational nature.
  Same for Deferred Revenue, Resale Value Guarantees, 
  and Customer Deposits. As Tesla's business expands,
  all of these will likely grow at same pace as Revenues. 
  Long-term Debt is an unknown and can be calculated once we have 
  the company's Unlevered Free Cash Flow. This will indicate
  whether and how much additional financing, debt or equity,
  that Tesla will need in the forecasting period. 
  We assume Other Liabilities will grow as a % or Revenue. 
  Now we can we can calculate Tesla's UFCF,
  that is the amount of cash the company can make 
  regardless of financial structure,
  whether financed by Equity only, by Debt and Equity 
  or is predominantly Debt financed. 
  First we start with Other Assets. 
  The impact of all Assets has to be taken into account 
  in the cash flow statement. So we must now consider all Assets 
  that we have no considered in the statement so far. 
  Other Assets (Balance Sheet) is not equal to Other Assets (Cash Flow),
  and here Other Assets (Balance Sheet) 
  is a part of Other Assets (Cash Flow).
  Other Assets (Cash Flow) 
   = Restricted Cash and Securities + Prepaid Expenses 
     + Operating Lease Vehicles + Solar Energy Systems Leased
     + Intangible Assets + Other Assets (Balance Sheet)
  The impact of all Liabilities has to be taken into account 
  in the cash flow statement. Otherwise we will not be able 
  to satisfy the Accounting Equation.
  Other Liabilities 
   = Accrued Liabilities + Deferred Revenue + Resale Value Guarantees
     + Customer Deposits + Other Liabilities 
  Unlevered Free Cash Flow 
   = Gross Cash Flow + Investments in Working Capital
     + Capex + Other Assets + Other Liabilities 
  Now we work on the Financing Sheet. 
  We build a solid logic that works when Tesla's business goes well
  and is profitable, but also incase of when the company struggles 
  and requires additional funds from outside.
  Many expect that the company will need external financing 
  and will have to raise Equity or Debt Capital one or more 
  times in the upcoming years. This is why we make following assumptions
  and incorporate them into our model:
   - Assumption 1: When UFCF<0, Tesla raises financing on
      the first day of the following year. 
   - Assumption 2: Tesla will use 50% debt and 50% equity financing
      to cover negative cash flows.
   - Assumption 3: The company's cost of debt remains flat 
      throughout the entire forecast period. It will be equal to 7.5%
      which was the yield of Teslas bonds as of 19th Sep 2018.
  Now we estimate Tesla's Long Term Debt and Interest Expenses. 
  We need to model for if there are other or additional years of 
  negative cash flows, and have this happen without our intervention.
  We use the if function of if we have a negative UFCF 
  in a given period. And if this logical test is true,
  we cover the loss with 50% debt. We multiply negative cash flow
  with 50% debt. 
  Now we calculate the Outstanding Debt and 
  use that to calculate Interest Expenses. 
  Outstanding Debt (end of 2018) 
   = Outstanding Debt (end of 2017) + Newly raised Debt (2018)
  Interest Expenses 
   = Outstanding Debt * Interest Rate
  Now we can use the P&L Sheet to obtain the Net Income. 
  For Income Taxes we first verify if EBT is positive
  and pay Taxes only if it's positive. 
  Taxes = EBT * Tax Rate
  We assume Minority Interests will be 0 in forecast period.
  Net Income = EBT + Taxes(negative) + Minority Interest(negative)
  Unlevered Free Cash Flow is a theoretical measure
  we calculated to obtain company Cash Flow if it was Debt free,
  so that we can arrive at a company Valuation that is independent 
  of capital structure and enterprise value. 
  To balance the Balance Sheet, 
  we need the actual cash flow or Net Cash Flow
  for a given period. 
  Delta Financial Liabilities 
   = Debt Current Period - Debt Previous Period 
  Debt Current Period = Long Term Debt Current Period
  Ending Equity 
   = (Opening Equity) +/- (Net Income/Loss) 
     +/- (Other Equity Movements) 
  Other Equity Movements = Dividend Payments or Increase of Capital
  Tax Adjustment = Taxes (P&L) - Operating Taxes (Cash Flow)
  This will mitigate the difference.
  Ending Cash = Beginning Cash + Net Cash Flow
  We now check if Assets = Liabilities + Equity ,
  in the Balance Sheet. 
<br>



---------------------
Scribble of some Excel Shortcuts
<br>

Monthly Mortgage Payment:

-insert function button (fx)
-search for "payment"
-click on function PMT 
(   which calculates the payment for a loan,
based on constant payments and a constant interest rate.   )
-Rate param is cell of "Monthly interest Rate"
-Nper param is cell of "Number of Periods(months)"
-Pv param is cell of "Price"
<br>


Top area of excel is ribbon,
Bottom is the Workspace
16k columns and 1mil rows
Hit "Enter" for cell below
Hit "Tab" for cell to right
Text are aligned to left
Numbers are aligned to right
Hit "Esc" to clear cell
Hit "F2" to activate formula bar
Hit "Del" to clear cells but leave formatting
Hit "Clear" in ribbon to completely clear cells
<br>


Hit "Cntrl + Space" to select a column
Hit "Shift + Space"  to select a row
<br>


Start a formula with + or =
<br>


the "If" function has three parts
-"Logical test" for condition to verify
-"Value if true" and "Value if false" is value to display
-eg: Logical Test of C9>D9, and if true Bigger, if false Smaller
-eg: =IF(C9>D9;"Bigger";"Smaller")
<br>

Hit "Alt + E + S" for "Paste Special"
- to paste eg only the values or only the formulas
<br>

Hit "Alt + Enter" to move part of text to new line in same cell
<br>

To formatted pasted text, go to "Data" and "Text to Columns"
- and use "Delimited", and "Tab" and "Space" as Delimiters
- Note: Also consider using Highpyn/Dash when typing sentence in cell
<br>

To specify print area, select cells, go to "Page Layout",
and select "Print Area", which creates a border around the cells
<br>

Hit "Wrap Text" button to put content of cell within cell space
<br>

Can insert "HyperLinks" into cell,
which on click can take you to place in document or web page,
content of cell can be modified.
<br>

To Freeze a row or column while scrolling,
select the row or column after the one to be frozen,
go to "View" and "Freeze Panes"
<br>

"Tell me what you want to do" box provides suggestion,
if you don't know or remember functionality or tool
<br>

"Pivot Tables" are excels dynamic and interactive tables.
-First select all rows and columns
-Go to "Insert" and "Pivot Table"
-Then Select fields to analyze from table
-eg: Drag Volume to "VALUES", default is count,
     and then select "Value Field Settings" in "VALUES" for sum
     Drag Year to "COLUMNS" and Product Group to "ROWS"
     Which now shows volumes per year for year product
<br>

Hit "Cntrl + A" to select all cells 
<br>

To enable "Macros", 
right click on ribbon and select "Customize Ribbon",
select "Developer" from Main Tabs
-An Excel Macro is a set of instructions that can be triggered,
 by a shortcut, toolbar button or an icon
-To record a macro, go to "Developer" tab and hit "record"
-Note: record macros only on one sheet to avoid issues
-Can be used for all the formatting to a sheet,
  eg like background colour, width of first column, 
  and first row size and colour. 
 Which can be saved and replayed on new sheets
<br>

For "fast scrolling" hit "Cntrl + arrow key",
and "Cntrl + Shift + arrow key" for fast scroll select
<br>

Disable "Allow editing within cells"
-Then "double click" on cell in sheet to take to first part of formula
-Then "f5" to return to cell and sheet with formula
<br>

Placing a "$" in front of a cell reference,
fixes the reference to cell during copy paste.
eg: "=$G4*H6" to fix column G, "=$G$4*H6" to fix column G and row 4
<br>

Hit "f5" after selecting the work cells for "Select Special"
- Here you can specify to select all eg blank cells,
  by hitting the "special button" and selecting criteria
  can paste eg n.a into empty cells
<br>

For "Dynamic Naming",
in cell type in eg ="P&L: "&C4,
which changes whats displayed based on C4 value,
eg P&L: Google Inc.
<br>

You can create names to ranges you select,
by first selecting the cells in column or row,
then naming it in "Name Box",
then you can find eg =SUM(Sales12),
but you can do calculation of two different range names,
eg error on = sales12 + sales13
<br>

To keep numbers with formatting as numbers and not text,
right click on cell with number and select "Format Cells",
then "custom" and type in the desired format eg 0.0x
<br>

"Data Validation" is if there are ,
only a few possible values for a row or column
first select the relevant columns or rows, 
then go to "Data" and then "Data Validation" and select "List",
which can be specified in different cells in sheet.
Now there will be a drop down for each of those cells.
Error alert can be turned off in validation options.
<br>

To sort data first select whole table,
then go to "Sort&Filter" then "Custom Sort",
then select largest to smallest or smallest to largest by column.
<br>

Can add "Quick Access toolbar" on mac by going to preferences,
then "Ribbon and toolbar".
<br>

On windows to see shortcuts press the "alt" key to reveal
<br>

To check if all cells in a column or row are numbers,
multiply each cell with 1 and the incorrect cells will reveal.
<br>

"Cntrl + H" to find and replace.
Can be used to change format
<br>

Always beauty save files.
Select the A1 cell in all sheets and save.
This way every-time excel is opened by anyone its opens as it should.
<br>

Can use "Conditional Formatting",
to add visual representation to make information easier to digest.
simply select the area and select "Conditional Formatting"
-Can specify custom rules to the formatting,
 like positive and negative ranges.
<br>

"IF" serves as the basis for sumif, sumifs, countif, countifs.
-checks if condition is satisfied or not
-eg: =IF(D4="Yes";F4;0)
"SUMIF"
-to calculate the number of games played by Italy in a list of countries
- =SUMIF(C4:C12;C18;E4:E12)
  where C4:C12 are the countries, C18 is "Italy" in a cell,
  and E4:E12 are the games played by each country 
  will only sum games played by Italy
"SUMIFS" for more than one condition check
- =SUMIFS(F4:F12;C4:C12;C:16;D4:D12;D16)
  where F4:F12 are the points by country, 
  then first condition list and criteria eg "England,
  then second condition list and criteria eg "Yes"
  eg add the points where country is England,
     and played in campions league
"COUNT" counts the num of cells within a range that contains nums
"COUNTA" counts non empty cells both num and text
"COUNTIF"
- =COUNTIF(F4:F12;">60")
 returns 6 ,  which means 6 of 9 teams earned greater than 60
"COUNTIFS"
- =COUNTIFS(D4:D12;"Yes";F4:F12;">60")
"AVERAGEIF"
- =AVERAGEIF(D4:D12;"Yes";F4:F12)
<br>

"LEFT" prints first selected num of characters in text
- =LEFT(D6;6)
"RIGHT"
"MID" has start and end 
- =MID(B6;4;7)
"UPPER"
"LOWER"
"PROPER" for first letter cap and all other lower
"CONCATENATE" is same as &
Working with text eg =A5&","&" "&B5 is Italy, Rome
"MAX"
"MIN"
"ROUND"
- =ROUND(B5;1) is round B5 to 1 decimal place
 <br>

"VLOOKUP" is for columns and has 
-"Lookup Value" which are column values to look up eg cities
-"Table array" is the table from which to lookup
-"Col index num" is the col from which to extract value if match exists
-"Range lookup" to look for exact match(FALSE) or closest match(TRUE)
eg: =VLOOKUP($H4;$B$4:$F$12;2;FALSE)
    where H4 is the team where H column is fixed, 
    next is table which has fixed location, 
    2 is col num to populate which here is country,
    and col num changes,
    FALSE for exact match
<br>

"HLOOKUP" is for rows and has 
-Here it is likely that the column heading are in a column,
 with its values in rows.
- eg =HLOOKUP($H4;$B$3:$F$7;2;False)
  where the row number 2 would change 
"INDEX & MATCH" is the lookup tool used by experienced Excel users
"INDEX" returns the value relative to index in selected table
- eg =INDEX(B4:C12;5;2) where 5 is row and 2 is column giving Italy
"MATCH" 
- eg: =MATCH(B19;B4:B12;0) 0 for exact match
- eg: =MATCH($I4;$B$4:$B$12;0) 0 for exact match
-"INDEX" formula needs as an input the number of the row in range
-"MATCH" function indicates position of result
- eg: =INDEX(C$4:C$12;MATCH($I4;$B$4:$B$12;0))
<br>

"IFERROR"
- eg =IFERROR(F7/$F$13;"n.a")
"RANK" to place a rank value in a column
- eg =RANK(D5;$D$5:$D$20) ,
  where D5 is first value to be ranked then range
  can now use "VLOOKUP"
  eg =VLOOKUP(B4;RANK!$B$5:$C$20;2:FALSE)
<br>

"CHOOSE" performs an action from a list of values based on index num
- eg =CHOOSE($I$4;D7;D8;D9) which based on index value,
  for 1 it would show D7, 2 it would show D8
<br>

"What-if Analysis button"
the "Goal Seek" feature based on a formula specified in a cell,
will find the possible value to the empty cell
the "Data table" feature can calculate possible results
- eg if interest rate and period are specified and calculated,
     a table can be formed with possible rates and periods.
<br>


----------------------------
</pre>
