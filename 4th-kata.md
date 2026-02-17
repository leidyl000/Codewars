# 3rd Kata -- Remove First and Last Character

by _[leidyl000](https://www.codewars.com/users/leidyl000)_

## Task

Explanation here

```js
// Your goal is to write a function that removes the first and last characters of a string. You're given one parameter, the original string.
```

## Test Examples

```js
//DB[:removechar].multi_insert([
  {s: "eloquent"}, {s: "country"}, {s: "person"}, {s: "place"}, {s: "ok"}, {s: "ooopsss"}
])
  
results = run_sql

describe :columns do
   it "should return 2 columns" do
    expect(results.columns.count).to eq 2
   end
end

describe :column_names do
   it "should match column names" do
     expect(results.columns[0].to_s).to eq "s" 
     expect(results.columns[1].to_s).to eq "res" 
   end
end

compare_with expected do end
```

## Notes

Learned funtion SUBSTRING.

## My solution with comments:

```js
//
select s, 
SUBSTRING(s, 2, LENGTH(s) - 2) AS res
FROM removechar;
```

## Results

```js
//Time: 1213ms Passed: 8Failed: 0
You have passed all of the tests! :)
```

## Interesting Kata solution:

> by _[gRubies](https://www.codewars.com/users/gRubies)_

```js
//select s, substring(s from '^.(.*).$') res
from removechar
```

## Notes about the interesting one:

Use of '^. -ignore the first character- (.* -capture everything in between-).$'-ignore the last character-.

---
