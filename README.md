# Learn what matters - Ruby

## Hello World Program

```ruby
print "Hello World"  #=> Hello World
puts "Hello World"   #=> Hello World

# notes:
#=> puts adds new line ('\n') after the output
```

## Basic Data Types

```ruby
# numbers
puts 2 ** 3    #=> 8
puts 5 / 2     #=> 2, not 2.5
puts 5 / 2.0   #=> 2.5

# converting number types
puts 2.to_f    #=> 2.0
puts 2.5.to_i  #=> 2


# strings
puts "Hello " + "World"        #=> Hello World
puts "Hello " << "World"       #=> Hello World
puts "Hello ".concat("World")  #=> Hello World

# string interpolation
world_text = "World"

puts "Hello #{world_text}"    #=> Hello World
puts "Hello " << world_text   #=> Hello World

# string methods
puts "hello".capitalize        #=> Hello
puts "hello".upcase            #=> HELLO
puts "HELLO".downcase          #=> hello
puts "  hello  ".strip         #=> hello
puts "hello".index('e')        #=> 1
puts "hello".include?('e')     #=> true
puts "hello".length            #=> 5
puts "hello".reverse           #=> olleh
puts "hello"[1...3]            #=> el
print "hello world".split       #=> ["hello", "world"]
puts
print "hello world".split(' ')  #=> ["hello", "world"]
puts
print "hello".split('')         #=> ["h", "e", "l", "l", "o"]
puts

# converting to string
puts 5.to_s                     #=> "5"
puts nil.to_s                   #=> ""
puts :symbol.to_s               #=> "symbol"


# symbols
symbol = :apple

string = "hello"
symbol_from_string = string.to_sym

puts "string" == "string"                      #=> true
puts symbol.object_id == symbol.object_id      #=> true
puts "string".object_id == "string".object_id  #=> false


# booleans
puts true    #=> true
puts false   #=> false

# notes:
#=> strings are mutable, while symbols are immutable in Ruby
```

## Variables

```ruby
name = "Abhishek"
age = 24

puts name    #=> Abhishek
puts age     #=> 24

name2 = name
name2.upcase!

puts name    #=> ABHISHEK
puts name2   #=> ABHISHEK


# notes:
=begin 
1. variables are references in Ruby
2. In Ruby, the exclamation mark (!) at the end of a method typically indicates that the method is destructive.
   A destructive method modifies the object it is called on, rather than returning a new object.
3. $variable_name   #=> Global
   @variable_name   #=> Instance
   @@variable_name  #=> Class
   variable_name    #=> Local or Block 
=end
```

## User Inputs

```ruby
print "Enter your name: "
username = gets         #=> "Abhishek\n"
username = gets.chomp   #=> "Abhishek"
puts username

print "Enter your age: "
user_age = gets.chomp.to_i
puts "Your age is ".concat(user_age)
```

## Operators

```ruby
# math operators
puts 2 + 3    #=> 5
puts 2 - 1    #=> 1
puts 2 * 3    #=> 6
puts 4 / 2    #=> 2
puts 2 ** 3   #=> 8
puts 4 % 2    #=> 0


# comparison operators
puts 4 == 4   #=> true
puts 6 != 3   #=> true
puts 6 < 7    #=> true
puts 7 > 8    #=> false
puts 7 <= 8   #=> true
puts 6 >= 5   #=> true


```

## Conditional Statements

```ruby
age = 15

if age >= 18
    puts "You are adult"
elsif age == 16
    puts "You will be an adult after two years!!!"  
else
    puts "You are not an adult, more than two years to go..."
end
```

## Switch Cases
```ruby
# cases
print "Input a number: "
user_input = gets.chomp.to_i

case user_input
when 1
    puts "Its Monday"
when 2
    puts "Its Tuesday"
when 3
    puts "Its Wednesday"
end
```

## Ternary Statements

```ruby
name = "Hellen"
name2 = "Hellen"

name3 = (name == name2) ? "Thomas" : "Unknown"

puts name3    #=> Thomas
```

## Loops

```ruby
# while loop
i = 0
while i < 5 do                       #=> 0 1 2 3 4
 print i.to_s + " "
 i += 1
end


# for loop
for i in 0..3                        #=> 0 1 2 3
    print i.to_s + " "
end

for i in 0...3                       #=> 0 1 2
    print i.to_s + " "
end

num = 36
sqrt_of_num = Math.sqrt(num).to_i

for i in 0.step(sqrt_of_num, 2)      #=> 0 2 4 6
    print i.to_s + " "
end

for i in 3.step(0, -1)               #=> 3 2 1 0
    print i.to_s + " "
end


# until loop
i = 0
until i >= 5 do                      #=> 0 1 2 3 4
 print i.to_s + " "
 i += 1
end


# notes:
#=> until loop is opposite of while loop
```

## Break and Next

```ruby
# break
for i in 1..10    #=> 1 2 3 4 5 6
    if i == 7
        break
    end
    print i.to_s + " "
end

puts   #=> \n


# next
for i in 1..10    #=> 1 2 3 4 5 6 8 9 10
    if i == 7
        next
    end
    print i.to_s + " "
end
```

## Arrays

```ruby
arr1 = [1, 2, 3, 4, 5]
arr2 = [1, 2, 3, "Hello", "World"]

Array.new                  #=> []
Array.new(3)               #=> [nil, nil, nil]
Array.new(3, true)         #=> [true, true, true]

# accessing elements
puts arr1[0]    #=> 1
puts arr1[4]    #=> 5
puts arr1[-2]   #=> 4

puts arr1.first          #=> 1
print arr1.first(2)      #=> [1, 2]
puts
print arr1.last(2)       #=> [4, 5]
puts

# adding and removing elements
arr1 << 6
print arr1    #=> [1, 2, 3, 4, 5, 6]
puts

arr1.push(7)
print arr1    #=> [1, 2, 3, 4, 5, 6, 7]
puts

arr1.push(8, 9)
print arr1    #=> [1, 2, 3, 4, 5, 6, 7, 8, 9]
puts

arr1.pop
print arr1    #=> [1, 2, 3, 4, 5, 6, 7, 8]
puts

arr1.unshift(0)
print arr1    #=> [0, 1, 2, 3, 4, 5, 6, 7, 8]
puts

arr1.shift
print arr1    #=> [1, 2, 3, 4, 5, 6, 7, 8]
puts

# array methods
puts arr1.length         #=> 8
puts arr1.include?(3)    #=> true
print arr1.reverse       #=> [8, 7, 6, 5, 4, 3, 2, 1]
puts
```

## Hashes

```ruby
# creating hashes
my_hash = {
  "a random word" => "ahoy",
  "Dorothy's math test score" => 94,
  "an array" => [1, 2, 3],
  "an empty hash within a hash" => {}
}

my_hash = Hash.new
puts my_hash               #=> {}

my_hash = { 
    9 => "nine", 
    :six => 6 
}

# accessing values
puts my_hash[9]          #=> nine
puts my_hash[:six]       #=> 6
puts my_hash["hiking"]   #=> nil

# adding and changing data
my_hash[5] = "five"
my_hash[:six] = 6.0
puts my_hash              #=> { 9 => "nine", :six => 6.0, 5 => "five" }

my_hash.delete(5)
puts my_hash              #=> { 9 => "nine", :six => 6.0 }

# hashes methods
print my_hash.keys        #=> [9, :six]
puts
print my_hash.values      #=> ["nine", 6.0]
puts
```

## Methods

```ruby
# creating methods
def greeting(name = "Abhishek")
    return "Good morning, #{name}!"
end

puts greeting               #=> Good morning, Abhishek!
puts greeting("Animesh")    #=> Good morning, Animesh!

# predicate methods
puts 5.even?              #=> false
puts 17.odd?              #=> true
puts 12.between?(10, 15)  #=> true


#=> notes:
=begin
1. You will sometimes encounter built-in Ruby methods that have a question mark (?) at the end of their name, such as even?, odd?, and between?.
   These are all predicate methods, which is a naming convention that Ruby uses for methods that return a Boolean.
=end
```

## Nested Collections

```ruby
# creating nested array
Array.new(3) { Array.new(2) }        #=> [[nil, nil], [nil, nil], [nil, nil]]
Array.new(3) { Array.new(2) { 0 } }  #=> [[0, 0], [0, 0], [0, 0]]


# creating nested hashes
vehicles = {
  alice: { year: 2019, make: "Toyota", model: "Corolla" },
  blake: { year: 2020, make: "Volkswagen", model: "Beetle" },
  caleb: { year: 2020, make: "Honda", model: "Accord" }
}


#=> notes:
#=> Always use dig(i, j) to retrieve elements from a nested collection, as it will return nil if the requested element does not exist.
```

## Classes and Objects

```ruby
# class
class Person

    # instance variables
    @name
    @age
    @height

    # class variables
    @@count = 0

    # constructor
    def initialize(name, age)
        @name = name
        @age = age
        Person.update_objects_count();
    end

    # methods
    def get_name()
        return @name
    end

    def self.update_objects_count() 
        @@count += 1
    end

    def self.display_objects_count()
        puts "Object created so far are: #{@@count}"
    end
end

person1 = Person.new("Abhishek Pandey", 27)

puts person1.get_name()         #=> Abhishek Pandey
Person.display_objects_count()  #=>  Object created so far are: 1
```
