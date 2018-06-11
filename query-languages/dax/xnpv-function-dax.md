---
title: "XNPV Function (DAX) | Microsoft Docs"
ms.prod: dax
ms.date: 5/22/2018
ms.reviewer: owend
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# XNPV Function (DAX)
  
Returns the present value for a schedule of cash flows that is not necessarily periodic.  
  
## Syntax  
  
```  
XNPV(<table>, <values>, <dates>, <rate>)  
```  
  
#### Parameters  
  
|Term|Definition|  
|--------|--------------|  
|table|A table for which the values and dates expressions should be calculated.|  
|values|An expression that returns the cash flow value for each row of the table.|  
|dates|An expression that returns the cash flow date for each row of the table.|  
|rate|The discount rate to apply to the cash flow for each row of the table.|  
  
## Return Value  
Net present value.  
  
## Remarks  
The value is calculated as the following summation:  
  
![XNPV Formula](media/dax-xnpv-formula.png)  
  
The series of cash flow values must contain at least one positive number and one negative number.  
  
## Example  
The following calculates the present value of the CashFlows table:  
  
```  
Present value := XNPV( CashFlows, [Payment], [Date], 0.09 )  
```  
  
|Date|Payment|  
|--------|-----------|  
|1/1/2014|-10000|  
|3/1/2014|2750|  
|10/30/2014|4250|  
|2/15/2015|3250|  
|4/1/2015|2750|  
  
Present value = 2086.65  
  