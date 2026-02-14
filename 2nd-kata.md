# 2nd Kata -- MakeUpperCase

by _[leidyl000](https://www.codewars.com/users/leidyl000)_

## Task

Explanation here

```js
// Write a function which converts the input string to uppercase.
```

## Test Examples

```js
//DB[:makeuppercase].multi_insert([
  {s: "hello"}, {s: "hello world"}, {s: "hello world !"}, {s: "heLlO wORLd !"}, {s: "1,2,3 hello world!"}  
])

$LETTERS = "abcdefgh ijklmnopq rstuvwxyz ABCDEFGHIJ QLMNOPQRSTUVWXYZ 1234567890!"

def randgen()
  (0..rand(99) + 1).map{|x| $LETTERS[rand($LETTERS.length)]}.join
end
  
DB[:makeuppercase].multi_insert(Array.new(100) do
  {s: randgen()} end  
)
  
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

Notes here

## My solution with comments:

```js
//--Learned how to use UPPER in SQL

select s, UPPER(s)as res from makeuppercase;
```

## Results

```js
//Time: 1129ms Passed: 8Failed: 0
You have passed all of the tests! :)
```

## Interesting Kata solution:

> by _[dfhwze](https://www.codewars.com/users/dfhwze)_

```js
//select s, upper(s) res from makeuppercase;
```

## Notes about the interesting one:

The lack of "as" to return the column witha different name.

---
