---
title: "Table.Sort | Microsoft Docs"
ms.date: 4/16/2018
ms.prod: power-query
ms.reviewer: owend
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# Table.Sort

  
## About  
Sorts the rows in a table using a comparisonCriteria or a default ordering if one is not specified.  
  
```  
Table.Sort(table as table, optional comparisonCriteria as any) as table  
```  
  
## Arguments  
  
|Argument|Description|  
|------------|---------------|  
|table|The Table to modify.|  
|optional comparisonCriteria|Sort comparison criteria.|  
  
## <a name="__toc360789717"></a>Remarks  
  
-   Table.Sort is similar to List.Sort but requires a table as input.  
  
## Examples  
  
```  
Table.Sort(  
  
    Table.FromRecords(  
  
{  
  
      [OrderID = 1, CustomerID = 1, Item = "Fishing rod", Price = 100.0],  
  
      [OrderID = 2, CustomerID = 1, Item = "1 lb. worms", Price = 5.0],  
  
      [OrderID = 3, CustomerID = 2, Item = "Fishing net", Price = 25.0],  
  
      [OrderID = 4, CustomerID = 3, Item = "Fish tazer", Price = 200.0],  
  
      [OrderID = 5, CustomerID = 3, Item = "Bandaids", Price = 2.0],  
  
      [OrderID = 6, CustomerID = 1, Item = "Tackle box", Price = 20.0],  
  
      [OrderID = 7, CustomerID = 5, Item = "Bait", Price = 3.25],  
  
      [OrderID = 8, CustomerID = 5, Item = "Fishing Rod", Price = 100.0],  
  
      [OrderID = 9, CustomerID = 6, Item = "Bait", Price = 3.25]  
  
}  
  
),  
  
        {{"CustomerID", Order.Ascending}, "OrderID"})  
```  
  
|OrderID|CustomerID|Item|Price|  
|-----------|--------------|--------|---------|  
|1|1|Fishing rod|100|  
|2|1|1 lb. worms|5|  
|6|1|Tackle box|20|  
|3|2|Fishing net|25|  
|4|3|Fish tazer|200|  
|5|3|Bandaids|2|  
|7|5|Bait|3.25|  
|8|5|Fishing Rod|100|  
|9|6|Bait|3.25|  
  