# 8th Kata -- Third Angle of a Triangle
by _[leidyl000](https://www.codewars.com/users/leidyl000)_

## Task

Explanation here

```js
// You are given two interior angles (in degrees) of a triangle.

Write a function to return the 3rd.

Note: only positive integers will be tested.
```

## Test Examples

```js
DB[:otherangle].multi_insert([
  {a: 1, b: 1}, {a: 42, b: 77}, {a: 81, b: 27}, {a: 45, b: 60}
])
  
results = run_sql

describe :columns do
   it "should return 3 columns" do
    expect(results.columns.count).to eq 3
   end
end

describe :column_names do
   it "should match column names" do
     expect(results.columns[0].to_s).to eq "a" 
     expect(results.columns[1].to_s).to eq "b" 
     expect(results.columns[2].to_s).to eq "res" 
   end
end

compare_with expected do end
```

## Notes



## My solution with comments:

```js
//
SELECT a , b, 180-(a+b) as res from otherangle;
```

## Results

```js
//Time: 1181ms Passed: 10Failed: 0
You have passed all of the tests! :)
```

## Interesting Kata solution:

> by _[amibadatcoding](https://www.codewars.com/users/amibadatcoding)_

```js
//SELECT 
a, 
b, 
180 - CAST(a AS INT) - CAST(b as INT) AS res 
FROM otherangle
```

## Notes about the interesting one:

Use of CAST for making sure res is an INT
---
