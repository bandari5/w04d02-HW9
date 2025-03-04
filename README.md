# Ruby Map Practice

![ARRAYS](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQVWBMdo6Ac3moY3tPnzMsFVnOscOR03SxkZ4sPGGhsWoQrYMPZ9g)

## 1. Return an array of each Student's full name, upper-cased

```rb

students = [
  {
      first_name: 'Abdulrahman',
      last_name: 'Alsulami'
  },
  {
      first_name: 'Leena',
      last_name: 'Yaseen',
  },
  {
      first_name: 'Sara',
      last_name: 'Alraddadi',
  }
]

upper_case_full_names = []

```

### Answer

```rb
ABDULRAHHMAN ALSULAMI
LEENA YASEEN
SARA ALRADDADI
```


students = [
   {
       first_name: 'Abdulrahman',
       last_name: 'Alsulami'
   },
   {
       first_name: 'Leena',
       last_name: 'Yaseen',
   },
   {
       first_name: 'Sara',
       last_name: 'Alraddadi',
   }
 ]

  upper_case_full_names = []

  for fullNames in students 
     upper_case_full_names.push(fullNames[:first_name].upcase+" "+fullNames[:last_name].upcase)
 end
 p upper_case_full_names

## 2. Find the first order for each user

```rb

users = [
  {
      name: 'Bandar',
      orders: [
          {
              description: 'a bike'
          }
      ]
  },
  {
      name: 'Hatim',
      orders: [
          {
              description: 'bees'
          },
          {
              description: 'fishing rod'
          }
      ]
  },
  {
      name: 'Mohammed',
      orders: [
          {
              description: 'a MacBook'
          },
          {
              description: 'The West Wing DVDs'
          },
          {
              description: 'headphones'
          },
          {
              description: 'a kitten'
          }
      ]
  }
]

first_order_for_each_user = []

```

### Answer

```rb

{:description=>"a bike"}
{:description=>"bees"}
{:description=>"a MacBook"}

```

$users = [
   {
       name: 'Bandar',
       orders: [
           {
               description: 'a bike'
           }
       ]
   },
   {
       name: 'Hatim',
       orders: [
           {
               description: 'bees'
           },
           {
               description: 'fishing rod'
           }
       ]
   },
   {
       name: 'Mohammed',
       orders: [
           {
               description: 'a MacBook'
           },
           {
               description: 'The West Wing DVDs'
           },
           {
               description: 'headphones'
           },
           {
               description: 'a kitten'
           }
       ]
   }
 ]

  def first_order_for_each_user
     $users.each do |key|
     puts key[:orders][0]
   end
 end

  first_order_for_each_user

## 3. Find the average amount spent on coffee, per transaction, for each person

```rb

people = [
  {
      name: 'Sarah',
      transactions: [
          {
              type: 'COFFEE',
              amount: 7.43
          },
          {
              type: 'TACOS',
              amount: 14.65
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  },
  {
      name: 'Bandari',
      transactions: [
          {
              type: 'BIKES',
              amount: 800.00
          },
          {
              type: 'TACOS',
              amount: 14.65
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  },
  {
      name: 'Safwan',
      transactions: [
          {
              type: 'COFFEE',
              amount: 7.43
          },
          {
              type: 'COFFEE',
              amount: 100.00
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  }
]


coffee_average_per_person = []

```

### Answer

```rb

{:name=>"Sarah", :coffee_average=>5.93}
{:name=>"Bandari", :coffee_average=>4.43}
{:name=>"Safwan", :coffee_average=>37.28666666666667}

```
people = [
   {
       name: 'Sarah',
       transactions: [
           {
               type: 'COFFEE',
               amount: 7.43
           },
           {
               type: 'TACOS',
               amount: 14.65
           },
           {
               type: 'COFFEE',
               amount: 4.43
           }
       ]
   },
   {
       name: 'Bandari',
       transactions: [
           {
               type: 'BIKES',
               amount: 800.00
           },
           {
               type: 'TACOS',
               amount: 14.65
           },
           {
               type: 'COFFEE',
               amount: 4.43
           }
       ]
   },
   {
       name: 'Safwan',
       transactions: [
           {
               type: 'COFFEE',
               amount: 7.43
           },
           {
               type: 'COFFEE',
               amount: 100.00
           },
           {
               type: 'COFFEE',
               amount: 4.43
           }
       ]
   }
 ]

 
  coffee_average_per_person = []

 
  coffee_average_per_person = people.map do |per|

      people = []
  per[:transactions].map do |trans|
        if trans[:type] == 'COFFEE'
           people.push(trans[:amount])
      end
   end

       { 
        name: per[:name] , 
       coffee_average: people.reduce(:+) / people.length 
       }
     end

      puts coffee_average_per_person

## 4. Find the most expensive product for each store, with the store name:

```rb

stores = [
  {
      store_name: 'Jarir',
      products: [
          {
              description: 'Titanium',
              price: 9384.33
          },
          {
              description: 'Gold',
              price: 345.54
          }
      ]
  },
  {
      store_name: 'Tamimi',
      products: [
          {
              description: 'Silver',
              price: 654.44
          },
          {
              description: 'Ruby',
              price: 323.43
          }
      ]
  },
  {
      store_name: 'Souq',
      products: [
          {
              description: 'Opal',
              price: 345.43
          },
          {
              description: 'Sapphire',
              price: 899.33
          }
      ]
  }
]

most_expensive_products_by_store = []

```

### Answer

```rb

{:store_name=>"Jarir", :most_expensive_product=>{:description=>"Titanium", :price=>9384.33}}
{:store_name=>"Tamimi", :most_expensive_product=>{:description=>"Silver", :price=>654.44}}
{:store_name=>"Souq", :most_expensive_product=>{:description=>"Sapphire", :price=>899.33}}

```
stores = [
   {
       store_name: 'Jarir',
       products: [
           {
               description: 'Titanium',
               price: 9384.33
           },
           {
               description: 'Gold',
               price: 345.54
           }
       ]
   },
   {
       store_name: 'Tamimi',
       products: [
           {
               description: 'Silver',
               price: 654.44
           },
           {
               description: 'Ruby',
               price: 323.43
           }
       ]
   },
   {
       store_name: 'Souq',
       products: [
           {
               description: 'Opal',
               price: 345.43
           },
           {
               description: 'Sapphire',
               price: 899.33
           }
       ]
   }
 ]

  most_expensive_products_by_store = []

  most_expensive_products_by_store = stores.map do |name_store|
     expensive_product = name_store[:products].max_by do |product|
         product[:price]
     end  

      {
       name: name_store[:store_name] ,
       price: expensive_product[:price]
     }
 end 

  puts most_expensive_products_by_store

# Bonus

Write an infinite loop that will make you add all the your friends in the students list and after each add will ask if you want to quit the loop (yes/no) if the user choose no print all the students array

### Answer

```

add a student
Amal Algregri
Do you want to continue ? (y/n)
y
add a student
Hanin Nouh
Do you want to continue ? (y/n)
y
add a student

```
