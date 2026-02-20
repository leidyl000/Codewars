# 5th Kata -- Keep Hydrated!

by _[leidyl000](https://www.codewars.com/users/leidyl000)_

## Task

Explanation here

```js
// Nathan loves cycling.

Because Nathan knows it is important to stay hydrated, he drinks 0.5 litres of water per hour of cycling.

You get given the time in hours and you need to return the number of litres Nathan will drink, rounded down.
```

## Test Examples

```js
DB.create_table :cycling do
  primary_key :id
  Float :hours
end

items = DB[:cycling] # Create a dataset

# Populate the table
5.times do
  num= Faker::Commerce.price
  items.insert(hours:  num)
end

describe :columns do
   it "should return 3 columns" do
    expect(results.columns.count).to eq 3
   end
end

describe :column_names do
   it "should match column names" do
    expect(results.columns[0].to_s).to eq "id"
    expect(results.columns[1].to_s).to eq "hours"
    expect(results.columns[2].to_s).to eq "liters"
   end
end
```

## Notes

Learned function FLOOR.

## My solution with comments:

```js
//
SELECT id, hours, FLOOR (Hours*0.5) as liters FROM cycling
```

## Results

```js
//Time: 1482ms Passed: 3Failed: 0
You have passed all of the tests! :)
```

## Interesting Kata solution:

> by _[jarvis](https://www.codewars.com/users/jarvis)_

```js
//SELECT id, hours, trunc(hours * 0.5) AS liters FROM cycling
```

## Notes about the interesting one:

Use of trunc

---
