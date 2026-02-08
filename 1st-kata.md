# 1st Kata -- Is it a palindrome?

by _[leidyl000](https://www.codewars.com/users/leidyl000)_

## Task

Explanation here

```js
// Write a function that checks if a given string (case insensitive) is a palindrome.
```

## Test Examples

```js
//DB[:ispalindrome].multi_insert([
  {str: "a"}, 
  {str: "aba"}, 
  {str: "Abba"},
  {str: "hello"}, 
  {str: "Bob"}, 
  {str: "Madam"},
  {str: "AbBa"}, 
  {str: "a"}
])
  
results = run_sql

describe :columns do
   it "should return 2 columns" do
    expect(results.columns.count).to eq 2
   end
end

describe :column_names do
   it "should match column names" do
     expect(results.columns[0].to_s).to eq "str" 
     expect(results.columns[1].to_s).to eq "res" 
   end
end

compare_with expected do end
```

## Notes

Notes here

## My solution with comments:

```js
//Learned how to use LOWER and REVERSE function; practiced CASE Expression, in SQL
Select str,
CASE when LOWER(str) = REVERSE(LOWER(str)) then true
            ELSE false 
            END as res
FROM ispalindrome;
```

## Results

```js
//Time: 1191ms Passed: 8Failed: 0
You have passed all of the tests! :)
```

## Interesting Kata solution:

> by _[DiegoCol93](https://www.codewars.com/users/DiegoCol93)_

```js
//SELECT str, CASE WHEN str ILIKE REVERSE (str)
  THEN TRUE ELSE FALSE END AS res
FROM ispalindrome
```

## Notes about the interesting one:

ILIKE function 

---
