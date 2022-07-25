---
title: ASP.NET-001-DataTable
date: 2022-06-14 16:55:02
tags:
---
首先建立一個DataTable

```
DataTable dt = new DataTable();
```

建立一欄,名稱為BookName,資料類型為string

```
DataColumn dc = new DataColumn();
dc.DataType = typeof(string);
dc.ColumnName = "BookName";
dt.Columns.Add(dc);
```

建立另一欄為,名稱為Price,資料類型為int

```
DataColumn dc = new DataColumn();
dc.DataType = typeof(int);
dc.ColumnName = "Price";
dt.Columns.Add(dc);
```

建立一列資料

```
DataRow newDataRow = dt.NewRow();
newDataRow["BookName"] = "C# Cookbook";
newDataRow["Price"] = 50;
dt.Rows.Add(newDataRow);
```

建立另一列資料

```
newDataRow = dt.NewRow();
newDataRow["BookName"] = "ASP.NET Cookbook";
newDataRow["Price"] = 40;
dt.Rows.Add(newDataRow);
```

建立的DataTable資料如下

![DataTable-01](/images/DataTable-01.PNG)



完整代碼如下

```
void Main()
{
    //建立一個DataTable
    DataTable dt = new DataTable();

    //建立一欄,名稱為BookName
    DataColumn dc = new DataColumn();
    dc.DataType = typeof(string);
    dc.ColumnName = "BookName";
    dt.Columns.Add(dc);
    
    //建立一欄,名稱為Price
    dc = new DataColumn();
    dc.DataType = typeof(int);
    dc.ColumnName = "Price";
    dt.Columns.Add(dc);
    
    //建立一列
    DataRow newDataRow = dt.NewRow();
    newDataRow["BookName"] = "C# Cookbook";
    newDataRow["Price"] = 50;
    dt.Rows.Add(newDataRow);
    
    newDataRow = dt.NewRow();
    newDataRow["BookName"] = "ASP.NET Cookbook";
    newDataRow["Price"] = 40;
    dt.Rows.Add(newDataRow);
    
    dt.Dump();
}
```