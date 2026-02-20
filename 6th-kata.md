# 6th Kata -- GROCERY STORE: Logistic Optimisation

by _[leidyl000](https://www.codewars.com/users/leidyl000)_

## Task

Explanation here

```js
// You are the owner of the Grocery Store. All your products are in the database, that you have created after CodeWars SQL excercises!:)

You have reached a conclusion that you waste to much time because you have too many different warehouses to visit each week.

You have to find out how many different types of product you buy from each producer. If you take only few items from some of them you will stop going there again and save the gasoline:)

In the results show producer and count_products_types which you buy from him.

Order the result by count_products_types (DESC) then by producer (ASC) in case there are duplicated amounts
```

## Test Examples

```js
results = run_sql

describe :query do
  describe :syntax do
    it "should contain SELECT" do
      expect($sql.upcase).to include("SELECT")
    end
    
    it "should contain GROUP BY" do
      expect($sql.upcase).to include("GROUP BY")
    end
    
    it "should order results" do
      expect($sql.upcase).to include("ORDER BY")
    end
  end

  describe :columns do
    it "should return 2 columns" do
      expect(results.first.keys.count).to eq 2
    end
    
    it "should contain count_products_types column" do
      expect(results.first.keys).to include(:count_products_types)
    end
    
    it "should contain producer column" do
      expect(results.first.keys).to include(:producer)
    end
  end
end
```

## Notes

Learned to order by 2 different columns

## My solution with comments:

```js
//
select producer, COUNT(name) as count_products_types
from products
group by producer order by count_products_types desc, producer asc;
```

## Results

```js
//Time: 3277ms Passed: 6Failed: 0
You have passed all of the tests! :)
```

## Interesting Kata solution:

> by _[zygfryd32](https://www.codewars.com/users/zygfryd32)_

```js
//SELECT count(*) AS count_products_types, producer
FROM products
GROUP BY producer
ORDER BY 1 DESC, 2;
```

## Notes about the interesting one:

Using the number of the column instead of the name.

---
