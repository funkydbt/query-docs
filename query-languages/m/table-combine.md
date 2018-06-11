---
title: "Table.Combine | Microsoft Docs"
ms.date: 5/22/2018
ms.prod: power-query
ms.reviewer: owend
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# Table.Combine
<code>Table.Combine(<b>tables</b> as list, optional <b>columns</b> as any) as table</code>

##About
Returns a table that is the result of merging a list of tables, <code>tables</code>. The resulting table will have a row type structure defined by <code>columns</code> or by a union of the input types if <code>columns</code> is not specified.

## Example 1
Merge the three tables together.

<code>Table.Combine({Table.FromRecords({[CustomerID = 1, Name = "Bob", Phone = "123-4567"]}), Table.FromRecords({[CustomerID = 2, Name = "Jim", Phone = "987-6543"] }),Table.FromRecords({[CustomerID = 3, Name = "Paul", Phone = "543-7890"]})})</code>

<table> <tr> <th>CustomerID</th> <th>Name</th> <th>Phone</th> </tr> <tr> <td>1</td> <td>Bob</td> <td>123-4567</td> </tr> <tr> <td>2</td> <td>Jim</td> <td>987-6543</td> </tr> <tr> <td>3</td> <td>Paul</td> <td>543-7890</td> </tr> </table>

## Example 2
Merge three tables with different structures.

<code>Table.Combine({Table.FromRecords({[Name="Bob",Phone="123-4567"]}), Table.FromRecords({[Fax="987-6543", Phone="838-7171"] }),Table.FromRecords({[Cell = "543-7890"]})})</code>

<table> <tr> <th>Name</th> <th>Phone</th> <th>Fax</th> <th>Cell</th> </tr> <tr> <td>Bob</td> <td>123-4567</td> <td></td> <td></td> </tr> <tr> <td></td> <td>838-7171</td> <td>987-6543</td> <td></td> </tr> <tr> <td></td> <td></td> <td></td> <td>543-7890</td> </tr> </table>

## Example 3
Merge two tables and project onto the given type.

<code>Table.Combine({Table.FromRecords({[Name="Bob",Phone="123-4567"]}), Table.FromRecords({[Fax="987-6543", Phone="838-7171"] }),Table.FromRecords({[Cell = "543-7890"]})}, {"CustomerID", "Name"})</code>

<table> <tr> <th>CustomerID</th> <th>Name</th> </tr> <tr> <td></td> <td>Bob</td> </tr> <tr> <td></td> <td></td> </tr> <tr> <td></td> <td></td> </tr> </table>
  