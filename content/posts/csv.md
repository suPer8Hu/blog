---
title : 'CSV'
date : 2023-12-17T20:32:54-06:00
draft : false
author : Hu
tags : ["UW-Madiosn", "CS400", "csv"]
categories: ["Courses"]
---

### **CSV Formatted Data**  

Comma-separated values (CSV) is a text file format that uses commas to separate values. A CSV file stores tabular data (numbers and text) in plain text, where each line of the file typically represents one data record. Each record consists of the same number of fields, and these are separated by commas in the CSV file. If the field delimiter itself may appear within a field, fields can be surrounded with quotation marks

**Example**  
  
| Year | Make | Model | Description | Price |  
|:---  |:---: |:---:  |    :---:    |  :--- |  
|1997  | Ford | E350  |ac, abs, moon|3000.00|
|1999  | Chevy| Venture "Extended Edition"  | |4900.00|
|1999  | Chevy| Venture "Extended Edition, Very Large"  | |5000.00|
|1996  | Jeep | Grand Cherokee |MUST SELL! air, moon roof, loaded|3000.00|  

The above table of data may be represented in CSV format as follows:

```
Year,Make,Model,Description,Price
1997,Ford,E350,"ac, abs, moon",3000.00
1999,Chevy,"Venture ""Extended Edition""","",4900.00
1999,Chevy,"Venture ""Extended Edition, Very Large""","",5000.00
1996,Jeep,Grand Cherokee,"MUST SELL!
air, moon roof, loaded",4799.00
```  
**Basic rule**  
1.Basic Structure: CSV is a simple file format used to store tabular data, such as a spreadsheet or database. Each line in a CSV file corresponds to a row in the table, and each field in that row or line is separated by a comma.

2.Headers: The first line often contains headers, which are the names of the columns. In the example provided, the headers are "Year", "Make", "Model", "Description", and "Price".

3.Commas as Separators: Fields are separated by commas. This is clear in the CSV representation where each value in the table is separated by a comma in the CSV data.

*4.Handling Commas within Fields: If a field itself contains a comma, the field is enclosed in double quotes. In the example, the description for the 1999 Chevy Venture includes a comma, so it is written as "Venture ""Extended Edition, Very Large""".*

*5.Handling Quotes within Fields: If a field contains a double quote character, that character is escaped by placing another double quote in front of it. In the same description for the 1999 Chevy Venture, the double quotes around "Extended Edition" are escaped by doubling them: "".*

6.Numbers and Text: Numeric fields, like "Price", are generally not quoted in CSV, but they can be. Text fields, especially those that may contain spaces or special characters, are often enclosed in double quotes.

7.End of Line: Each line ends with a line break, which signifies the end of a row in the CSV data.

8.Consistency: Each row should have the same number of fields, to maintain consistency across the table structure. If a field is empty, the commas still need to be in place to indicate the missing data.

9.Whitespace: Whitespace around comma separators is generally ignored, and fields are trimmed of whitespace at the beginning and end when they are read into a program.

10.Special Characters: For characters like line breaks or other control characters within fields, the entire field should be enclosed in double quotes.  

1.基本结构：CSV是一种简单的文件格式，用于存储表格数据，如电子表格或数据库。CSV文件中的每一行对应表格中的一行，每个行中的字段由逗号分隔。

2.表头：文件的第一行通常包含表头，即列的名称。在提供的示例中，表头是"Year"（年份）、"Make"（制造商）、"Model"（型号）、"Description"（描述）和"Price"（价格）。

3.逗号作为分隔符：字段之间用逗号分隔。在CSV数据表示中，表格中的每个值都由CSV数据中的逗号分隔。

*4.处理字段中的逗号：如果字段本身包含逗号，则该字段用双引号括起来。在示例中，1999年的Chevy Venture的描述包含逗号，因此写为"Venture ""Extended Edition, Very Large"""。*

*5.处理字段中的引号：如果字段包含双引号字符，则通过在它前面放置另一个双引号来转义该字符。在同一描述中，围绕"Extended Edition"的双引号通过加倍来转义：""。*

6.数字和文本：像"Price"这样的数字字段通常不会加引号，但也可以加。特别是可能包含空格或特殊字符的文本字段，通常会用双引号括起来。

7.行尾：每行结束时有一个换行符，表示CSV数据中行的结束。

8.一致性：每行应该有相同数量的字段，以保持表结构的一致性。如果字段为空，仍然需要逗号来表示数据缺失。

9.空白字符：逗号分隔符周围的空白通常会被忽略，当字段被读入程序时，会去除字段开始和结束处的空白。

10.特殊字符：对于字段内的换行符或其他控制字符，整个字段应该用双引号括起来。