---
tags:
  - Learning/Backend/Scratch
---
1. **Storage Layer**:
    - Implement a basic file system for storing data (e.g., append-only logs, B-trees).
2. **Query Parsing**:
    - Parse basic SQL-like queries.
3. **Indexing**:
    - Build simple indexes (e.g., hash maps, B-trees) to improve query performance.
4. **Concurrency**:
    - Use Go's goroutines and channels for handling multiple queries simultaneously.
5. **Transactions**:
    - Implement ACID properties (start simple with atomic writes).


# Row vs Column oriented Layouts

Databases store data either by rows (e.g., all fields for a record together) or by columns (e.g., all values for a column together). Row-oriented storage is efficient for transactional systems, while column-oriented is better for analytics.

## Example

| ID  | Name  | Age | City        |
| --- | ----- | --- | ----------- |
| 1   | Alice | 30  | New York    |
| 2   | Bob   | 25  | Los Angeles |
### Row Oriented

Storage in Binary file
`[1, Alice, 30, New York][2, Bob, 25, Los Angeles]`

### Column Oriented
Storage in Binary file
`[1, 2] [Alice, Bob] [30, 25] [New York, Los Angeles]`

## When to use **COLUMNAR** Database
1. Queries that involve only a few columns
2. Clustering queries against a huge amount of data (Data science)
3. Compression but column-wise only

## Advantages of **COLUMNAR** Databases

