## 83 Basiskonten

TODO: Belegorientierets Buchen

Die 83 [Basiskonten](http://wiki.idempiere.org/de/Basiskonten) werden auch [Standardkonten/default accounts](http://wiki.idempiere.org/de/Standardkonten) genannt. 10 davon beziehen sich auf das [Hauptbuch/general ledger](https://de.wikipedia.org/wiki/Buchf%C3%BChrung#Hauptbuch). Sie haben fest programmierte Namen, die man in Spalten der Tabellen ``c_acctschema_default`` oder ``c_acctschema_gl`` wiederfindet. Die Namen enden mit ``_acct`` und haben oft einen Prefix, der auf die Verwendung verweist. 

Präfix  | Prefixbedeutung | Tabellen, die ``c_acctschema_default`` überschreiben
------- | --------------- | ----------
B       | Bank            | ``C_BankAccount_Acct``  
C       | Customer        | ``C_BP_Customer_Acct`` , defaults in  ``C_BP_Group_Acct``
E       | Employee        | ``C_BP_Employee_acct`` , defaults in  ``C_BP_Group_Acct``
V       | Vendor          | ``C_BP_Vendor_Acct`` , defaults in  ``C_BP_Group_Acct`` 
CB      | CashBook        | ``C_CashBook_Acct``
CH      | CHarge          | ``C_Charge_Acct``  
`` `` | `` ``       | ``C_Currency_Acct``
`` `` | `` ``       | ``C_InterOrg_Acct``
PJ      | ProJect         | ``C_Project_Acct`` 
T       | Tax             | ``C_Tax_Acct``  
`` `` | `` ``       | ``C_Withholding_Acct``
P       | Product         | ``M_Product_Acct`` , defaults in  ``M_Product_Category_Acct``  
W       | Warehouse       | ``M_Warehouse_Acct`` 

Die meisten Bezeichnungen lehnen sich an die Kontobezeichnung im US-Kontenrahmen AccountingUS.xls an. Dieser Kontenrahmen wird als Referenz in ADempiere gepflegt.

```sql
select * from ad_table where name like '%_Acct'
order by tablename;
:
"C_BankAccount_Acct"
"C_BP_Customer_Acct"
"C_BP_Employee_Acct"
"C_BP_Group_Acct"
"C_BP_Vendor_Acct"
"C_CashBook_Acct"
"C_Charge_Acct"
"C_Currency_Acct"
"C_InterOrg_Acct"
"C_Project_Acct"
"C_Tax_Acct"
"C_Withholding_Acct"
"M_Product_Acct"
"M_Product_Category_Acct"
"M_Warehouse_Acct"
;
-- zugeordnete SKR 03 Konten
select e.value,e.name,e.description 
 , v.c_validcombination_id,v.combination,v.description,v.account_id 
 from c_validcombination v
 join c_elementvalue e on c_elementvalue_id=v.account_id
where v.ad_client_id=1000000
order by e.value --v.c_validcombination_id
;
-- suchen nach commitmentoffset_acct (bzw alle aus c_acctschema_gl)
select e.value,e.name,e.description 
 , v.c_validcombination_id,v.combination,v.description,v.account_id 
 from c_validcombination v
 join c_elementvalue e on c_elementvalue_id=v.account_id
where v.ad_client_id=1000000 
  and v.c_validcombination_id in( 
    select commitmentoffset_acct from c_acctschema_gl where ad_client_id=1000000 )
;
--
select ad_client_id
,commitmentoffset_acct
,commitmentoffsetsales_acct
,currencybalancing_acct
,incomesummary_acct
,intercompanyduefrom_acct
,intercompanydueto_acct
,ppvoffset_acct
,retainedearning_acct
,suspensebalancing_acct
,suspenseerror_acct
 from c_acctschema_gl gl
 where gl.ad_client_id=1000000
 
-- suchen nach w_inventory_acct (bzw alle aus c_acctschema_gl)
select e.value,e.name,e.description 
 , v.c_validcombination_id,v.combination,v.description,v.account_id 
 from c_validcombination v
 join c_elementvalue e on c_elementvalue_id=v.account_id
where v.ad_client_id=1000000 
  and v.c_validcombination_id in( 
    select w_inventory_acct from c_acctschema_default where ad_client_id=1000000 )
;

CREATE TABLE c_acctschema_default
(
...
  w_inventory_acct 
  w_invactualadjust_acct 
  w_differences_acct 
  w_revaluation_acct 
  
  p_revenue_acct 
  p_expense_acct 
  p_asset_acct 
  p_purchasepricevariance_acct 
  p_invoicepricevariance_acct 
  p_tradediscountrec_acct 
  p_tradediscountgrant_acct 
  p_cogs_acct 
  
  c_receivable_acct 
  c_prepayment_acct 
  
  v_liability_acct 
  v_liability_services_acct 
  v_prepayment_acct 
  
  paydiscount_exp_acct 
  writeoff_acct 
  paydiscount_rev_acct 
  unrealizedgain_acct 
  unrealizedloss_acct 
  realizedgain_acct 
  realizedloss_acct 
  withholding_acct 
  
  e_prepayment_acct 
  e_expense_acct 
  
  pj_asset_acct 
  pj_wip_acct 
  
  t_expense_acct 
  t_liability_acct 
  t_receivables_acct 
  t_due_acct 
  t_credit_acct 
  
  b_intransit_acct 
  b_asset_acct 
  b_expense_acct 
  b_interestrev_acct 
  b_interestexp_acct 
  b_unidentified_acct 
  b_unallocatedcash_acct 
  b_paymentselect_acct 
  b_settlementgain_acct 
  b_settlementloss_acct 
  b_revaluationgain_acct 
  b_revaluationloss_acct 
  
  ch_expense_acct | 4900 Sonstige betriebliche Aufwendungen 
  ch_revenue_acct 
  
  unearnedrevenue_acct 
  notinvoicedreceivables_acct 
  notinvoicedrevenue_acct 
  notinvoicedreceipts_acct | "Not invoiced receipts" Default Level 1 -> BP_Group 	3200 Wareneingang 
  
  cb_asset_acct 
  cb_cashtransfer_acct 
  cb_differences_acct 
  cb_expense_acct 
  cb_receipt_acct 
  
  c_receivable_services_acct 
  
  p_inventoryclearing_acct 
  p_costadjustment_acct 
  p_wip_acct 
  p_methodchangevariance_acct 
  p_usagevariance_acct 
  p_ratevariance_acct 
  p_mixvariance_acct 
  p_floorstock_acct 
  p_costofproduction_acct 
  p_labor_acct 
  p_burden_acct 
  p_outsideprocessing_acct 
  p_overhead_acct 
  p_scrap_acct 
  p_averagecostvariance_acct 
```