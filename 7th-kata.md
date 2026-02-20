# 7th Kata -- Disemvowel Trolls

by _[leidyl000](https://www.codewars.com/users/leidyl000)_

## Task

Explanation here

```js
// Trolls are attacking your comment section!

A common way to deal with this situation is to remove all of the vowels from the trolls' comments, neutralizing the threat.

Your task is to write a function that takes a string and return a new string with all vowels removed.

For example, the string "This website is for losers LOL!" would become "Ths wbst s fr lsrs LL!".

Note: for this kata y isn't considered a vowel.
```

## Test Examples

```js
DB[:disemvowel].multi_insert([
  {str: "This website is for losers LOL!"}, 
  {str: "No offense but,\nYour writing is among the worst I've ever read"}, 
  {str: "What are you, a communist?"}
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

Learned function REGEXP_REPLACE.

## My solution with comments:

```js
//
SELECT
    str, 
    REGEXP_REPLACE(str, '[aeiouAEIOU]', '', 'g') as res
FROM disemvowel;
```

## Results

```js
//Time: 1086ms Passed: 8 Failed: 0
You have passed all of the tests! :)
```

## Interesting Kata solution:

> by _[tim1188](https://www.codewars.com/users/tim1188)_

```js
//SELECT str, translate(str, 'aeiouAEIOU', '') as res FROM disemvowel;
```

## Notes about the interesting one:

Use of function TRANSLATE
---
