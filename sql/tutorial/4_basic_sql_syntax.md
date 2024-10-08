# Basic SQL Syntax

## SQL keywords:

- SQL keywords là các từ đã được định nghĩa sẵn trong SQL để thực hiện các tác vụ cụ thể.
- Các từ khóa quan trọng: SELECT, INSERT, UPDATE, DELETE, CREATE, ALTER, DROP, FROM, WHERE, và JOIN.

## Các câu lệnh SQL thông dụng:

### 1. SELECT

Câu lệnh `SELECT` được sử dụng để truy vấn dữ liệu từ một bảng cơ sở dữ liệu.

```sql
SELECT column1, column2, ...
FROM table_name;
```

### 2. SELECT DISTINCT

Câu lệnh `SELECT DISTINCT` được sử dụng để trả về các giá trị khác nhau trong một cột.

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

### 3. WHERE

Câu lệnh WHERE được sử dụng để lọc các bản ghi dựa trên các điều kiện cụ thể.

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### 4. AND, OR, NOT

Các toán tử AND, OR, NOT được sử dụng để kết hợp các điều kiện trong mệnh đề WHERE.

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2;

SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2;

SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```

### 5. ORDER BY

Câu lệnh ORDER BY được sử dụng để sắp xếp kết quả truy vấn theo thứ tự tăng dần hoặc giảm dần.

```
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC|DESC];
```

### 6. INSERT INTO

Câu lệnh INSERT INTO được sử dụng để thêm một bản ghi mới vào bảng.

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

### 7. UPDATE

Câu lệnh UPDATE được sử dụng để cập nhật các bản ghi hiện có trong bảng.

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### 8. DELETE

Câu lệnh DELETE được sử dụng để xóa các bản ghi hiện có trong bảng.

```
DELETE FROM table_name
WHERE condition;
```

### 9. CREATE TABLE

Câu lệnh CREATE TABLE được sử dụng để tạo một bảng mới.

```
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);
```

### 10. ALTER TABLE

Câu lệnh ALTER TABLE được sử dụng để thêm, xóa hoặc sửa đổi các cột trong bảng.

```sql
ALTER TABLE table_name
ADD column_name datatype;

ALTER TABLE table_name
DROP COLUMN column_name;

ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```

### 11. DROP TABLE

Câu lệnh DROP TABLE được sử dụng để xóa một bảng hiện có.

```sql
DROP TABLE table_name;
```

### 12. JOINS

Các phép nối JOIN được sử dụng để kết hợp các hàng từ hai hoặc nhiều bảng dựa trên một cột chung giữa chúng.

Ghi chú

- INNER JOIN và JOIN thường được sử dụng thay thế nhau vì chúng hoạt động giống nhau.

- Không phải tất cả các hệ quản trị cơ sở dữ liệu đều hỗ trợ FULL JOIN và NATURAL JOIN.


#### a.INNER JOIN

Trả về các hàng có giá trị phù hợp trong cả hai bảng.

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

#### b.LEFT JOIN (or LEFT OUTER JOIN)

Trả về tất cả các hàng từ bảng bên trái, và các hàng phù hợp từ bảng bên phải. Nếu không có sự phù hợp, kết quả là NULL từ bảng bên phải.

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```

#### c.RIGHT JOIN (or RIGHT OUTER JOIN)

Trả về tất cả các hàng từ bảng bên phải, và các hàng phù hợp từ bảng bên trái. Nếu không có sự phù hợp, kết quả là NULL từ bảng bên trái.

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```

#### d.FULL OUTER JOIN

Trả về các hàng khi có sự phù hợp trong một trong các bảng. Nếu không có sự phù hợp, kết quả là NULL từ bảng không có sự phù hợp.

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

#### e.CROSS JOIN

Kết hợp tất cả các bản ghi từ bảng này với tất cả các bản ghi từ bảng khác (sản phẩm Cartesian).

```sql
SELECT a.column1, b.column2
FROM table1 a
CROSS JOIN table2 b;
```

#### f. CARTESIAN JOIN

Là một loại CROSS JOIN, tạo ra sản phẩm Cartesian của hai bảng. Mỗi hàng của bảng đầu tiên kết hợp với mỗi hàng của bảng thứ hai.

```sql
SELECT a.column1, b.column2
FROM table1 a, table2 b;
```

#### g.SELF JOIN

Kết hợp một bảng với chính nó. Sử dụng trong trường hợp bạn cần so sánh dữ liệu trong cùng một bảng.

```sql
SELECT a.column1, b.column2
FROM table1 a
INNER JOIN table1 b ON a.common_column = b.common_column;
```

#### h.NATURAL JOIN

Tự động kết hợp các bảng dựa trên các cột có cùng tên và kiểu dữ liệu trong cả hai bảng.

```sql
SELECT *
FROM table1
NATURAL JOIN table2;
```
