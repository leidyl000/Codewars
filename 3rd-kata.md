# 3rd Kata -- Quarter of the year

by _[leidyl000](https://www.codewars.com/users/leidyl000)_

## Task

Explanation here

```js
// Given a month as an integer from 1 to 12, return to which quarter of the year it belongs as an integer number.
```

## Test Examples

```js
//DB[:quarterof].multi_insert([
  {month: 3}, 
  {month: 8},
  {month: 11}
])

results = run_sql

describe :columns do
   it "should return 2 columns" do
    expect(results.columns.count).to eq 2
   end
end

describe :column_names do
   it "should match column names" do
     expect(results.columns[0].to_s).to eq "month" 
     expect(results.columns[1].to_s).to eq "res" 
   end
end

compare_with expected do end
```

## Notes

Learned funtion BETWEEN; practiced CASE.

## My solution with comments:

```js
//

select month,
case 
when month between 1 and 3 then 1
when month between 4 and 6 then 2
when month between 7 and 9 then 3
else 4
end as res
from quarterof;
```

## Results

```js
//Time: 1271ms Passed: 8Failed: 0
You have passed all of the tests! :)
```

## Interesting Kata solution:

> by _[rimskayama](https://www.codewars.com/users/rimskayama)_

```js
//SELECT month, CAST(CEILING(month / 3.0) AS INT) AS res 
FROM quarter
```

## Notes about the interesting one:

The use of CAST and CEILING

---
