The STEM Teacher’s Guide to R Programming

Welcome to the STEM Teacher's Guide to R. This repository serves as a comprehensive reference for learning R programming, covering everything from data foundations to statistical analysis.

Table of Contents

Chapter 1: The Foundations (أساسيات البيانات)

Chapter 2: The Grammar of R (قواعد لغة R)

Chapter 3: The Toolkit (Operators)

Chapter 4: Organizing Data (Data Structures)

Chapter 5: Controlling Flow (التحكم في التكرار والقرارات)

Chapter 6: The Toolkit (Functions)

Chapter 7: Handling Real Files (التعامل مع الملفات)

Chapter 8: The Analyst at Work (الإحصاء والتحليل)

Chapter 1: The Foundations (أساسيات البيانات)

Before writing code, we must define Data. Data is split into two main types. This is the language you will use to describe your variables.

1. Types of Data (أنواع البيانات)

Quantitative (كمي): Numbers you can count or measure.

Discrete (منفصل): Whole numbers only.

Classroom Example: Number of students (You can't have 2.5 students).

Continuous (مستمر): Decimals are allowed.

Classroom Example: Height (150.5 cm), Weight, Salary.

Qualitative (نوعي): Categories or labels (No math allowed).

Nominal (اسمي): Categories with no order.

Classroom Example: Gender (Male/Female), Eye Color.

Ordinal (ترتيبي): Categories with a ranking order.

Classroom Example: Ratings (Excellent, Good, Poor), T-Shirt Size (S, M, L).

Chapter 2: The Grammar of R (قواعد لغة R)

To speak to R, you need to know how to create "words" (Variables) and "sentences" (Assignments).

1. Variables (المتغيرات)

A variable is a container. You name it, and you store data inside it.

Valid Names (أسماء صحيحة): var_name, var.name, var_name2

Invalid Names (أسماء خاطئة):

2var_name (Cannot start with a number)

_var_name (Cannot start with underscore)

var_name% (Cannot contain special symbols like %)

How to Assign Values (التعيين)

You can use <- (Left Arrow) or = (Equal sign). The course emphasizes the arrow.

# Assignment using arrow (Preferred)
variable.2 <- "Learn R Programming"

# Assignment using equal sign
variable.1 = 124

# Printing values
print(variable.1)
cat("variable.2 is", variable.2)


Output:

[1] 124
variable.2 is Learn R Programming


2. Data Types in R (أنواع البيانات داخل R)

When you store something, R automatically gives it a "Type".

Type

Arabic

Definition

Course Example

Numeric

رقمي

Any number (decimals included).

12, 32, 5432

Integer

صحيح

Whole numbers. Must add 'L'.

3L, 66L, 2346L

Character

نصي

Text. Must use quotes.

"good", "TRUE", '35.4'

Logical

منطقي

True or False.

TRUE, FALSE

Complex

مركب

Math with imaginary numbers.

1+2i

Checking the Type

Use the class() function to ask R "What type is this?".

variable_y <- 124
cat("The data type is", class(variable_y)) 


Output:

The data type is numeric


3. User Input (إدخال البيانات من المستخدم)

You can ask the user to type something using readline().

my.name <- readline(prompt="Enter name: ")
my.age <- readline(prompt="Enter age: ")

# Convert text to number (integer) for math
my.age <- as.integer(my.age)

print(paste("Hi,", my.name, "next year you will be", my.age+1))


Output: (Assuming user types "Mary" and "17")

Enter name: Mary
Enter age: 17
[1] "Hi, Mary next year you will be 18 years old."


Chapter 3: The Toolkit (Operators)

Operators are the symbols used to do math or compare logic.

1. Arithmetic Operators (العمليات الحسابية)

Used for math calculations.

a <- c(2, 3.3, 4)
b <- c(11, 5, 3)

# Addition (+)
print(a + b)  

# Subtraction (-)
print(a - b)

# Multiplication (*)
print(a * b)

# Division (/)
print(a / b)

# Remainder / Modulus (%%) - باقي القسمة
# Example: 5 divided by 2 is 2 with remainder 1
print(a %% b) 

# Integer Division (%/%) - القسمة الصحيحة (بدون كسور)
print(a %/% b)

# Exponent / Power (^) - الأس
print(a ^ b)


Output:

[1] 13.0 8.3 7.0          
[1] -9.0 -1.7 1.0         
[1] 22.0 16.5 12.0        
[1] 0.18 0.66 1.33        
[1] 2.0 3.3 1.0           
[1] 0 0 1                 
[1] 2048.0 391.3 64.0     


2. Relational Operators (عمليات المقارنة)

These return TRUE or FALSE.

a <- c(1, 3, 5)
b <- c(2, 4, 6)

print(a > b)   # Greater than (أكبر من)
print(a < b)   # Less than (أصغر من)
print(a == b)  # Equal to (يساوي - note double =)
print(a != b)  # Not Equal to (لا يساوي)
print(a >= b)  # Greater or Equal
print(a <= b)  # Less or Equal


Output:

[1] FALSE FALSE FALSE    
[1] TRUE TRUE TRUE       
[1] FALSE FALSE FALSE    
[1] TRUE TRUE TRUE       


3. Logical Operators (العمليات المنطقية)

Used to combine multiple conditions.

& (AND - Element-wise): Checks every single item in a list.

| (OR - Element-wise): Checks every single item.

! (NOT): Reverses the result.

a <- c(3, 0, TRUE, 2+2i)
b <- c(2, 4, TRUE, 2+3i)

print(a & b)  # Returns TRUE only if BOTH are true
print(a | b)  # Returns TRUE if AT LEAST ONE is true
print(!a)     # Flips TRUE to FALSE


Output:

[1] TRUE FALSE TRUE TRUE  
[1] TRUE TRUE TRUE TRUE   
[1] FALSE TRUE FALSE FALSE 


Chapter 4: Organizing Data (Data Structures)

R has specific ways to organize groups of data.

1. Vectors (المتجهات)

A single row of data. Must be all the same type.

# Numeric Vector
numeric_vector <- c(1, 2, 3, 4, 5)

# Character Vector
character_vector <- c("apple", "banana", "orange")

# Logical Vector
logical_vector <- c(TRUE, FALSE, TRUE)


2. Lists (القوائم)

A mixed bag. Can hold numbers, text, and logic all at once.

# Creating a list
my_list <- list(name = "John", age = 30, is_student = TRUE)

# Accessing items using the $ sign
print(my_list$name)


Output:

[1] "John"


3. Matrices (المصفوفات)

A grid (rows and columns) of the same data type.

# Create a 3x3 matrix with numbers 1 to 9
mat <- matrix(1:9, nrow = 3, ncol = 3)
print(mat)


Output:

     [,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9


4. Data Frames (إطارات البيانات)

The most important structure. Like an Excel sheet with columns of different types.

# Create a data frame
df <- data.frame(
    name = c("Alice", "Bob", "Charlie"),
    age = c(25, 30, 35),
    gender = c("F", "M", "M")
)
print(df)


Output:

     name age gender
1   Alice  25      F
2     Bob  30      M
3 Charlie  35      M


5. Factors (الفئات)

Used for categorical data (Ordinal/Nominal). It stores text as levels (numbers) internally to save memory.

data <- c("A", "B", "A", "C")
factor_data <- factor(data)
print(factor_data)


Output:

[1] A B A C
Levels: A B C


Chapter 5: Controlling Flow (التحكم في التكرار والقرارات)

1. Decisions (If / Else)

x <- 24

if (is.integer(x)) {
    print("x is an Integer")
}

# Checking Even or Odd (Using Modulus %%)
if (x %% 2 == 0) {
    cat(x, "is an even number")
} else {
    cat(x, "is an odd number")
}


Output:

24 is an even number


Switch Statement

Useful for menus or specific choices.

# Example: User chooses "9" for Addition
choice <- "9" 
a <- 10
b <- 2

result <- switch(
    choice,
    "9" = cat("Addition =", a + b),
    "12" = cat("Subtraction =", a - b)
)


Output:

Addition = 12


2. Loops (التكرار)

For Loop

Repeat a specific number of times.

fruit <- c('Apple', 'Orange', 'Guava')
for (i in fruit) {
    print(i)
}


Output:

[1] "Apple"
[1] "Orange"
[1] "Guava"


While Loop

Repeat while a condition is true.

cnt <- 2
while (cnt < 5) {
    print("Hello")
    cnt <- cnt + 1
}


Output:

[1] "Hello"
[1] "Hello"
[1] "Hello"


Repeat Loop with Break

Repeat forever until you tell it to stop.

cnt <- 2
repeat {
    print("Hello")
    cnt <- cnt + 1
    
    # Stop condition
    if (cnt > 4) {
        break
    }
}


Output:

[1] "Hello"
[1] "Hello"
[1] "Hello"


Next Statement

Skip the current round and move to the next.

x <- 1:5
for (val in x) {
    if (val == 3) {
        next  # Skip printing 3
    }
    print(val)
}


Output:

[1] 1
[1] 2
[1] 4
[1] 5


Chapter 6: The Toolkit (Functions)

A Function (الدالة) is like a machine. You put raw materials in (Arguments), the machine does the work (Body), and it gives you a finished product (Return Value).

1. Built-in Functions (أدوات جاهزة)

R has many tools ready for you to use.

Math Functions (دوال رياضية)

abs(x): Returns the absolute (positive) value.

sqrt(x): Returns the square root.

ceiling(x): Rounds up to the nearest integer.

floor(x): Rounds down to the nearest integer.

trunc(x): Cuts off the decimals (truncates).

round(x, digits=n): Rounds to a specified number of decimal places.

x <- -4
print(abs(x))      

x <- 4.5
print(ceiling(x))  

x <- 2.5
print(floor(x))    

x <- 3.14159
print(round(x, digits=2)) 


Output:

[1] 4
[1] 5
[1] 2
[1] 3.14


String Functions (دوال نصية)

substr(x, start, stop): Extracts a piece of text.

paste(..., sep=""): Glues text pieces together.

toupper(x) / tolower(x): Converts text to UPPERCASE or lowercase.

a <- "987654321"
print(substr(a, 3, 3))    

print(paste('one', 2, 'three')) 

st1 <- "shuBHAm"
print(toupper(st1)) 


Output:

[1] "7"
[1] "one 2 three"
[1] "SHUBHAM"


Statistical Functions (دوال إحصائية)

mean(x): The Average (المتوسط).

median(x): The Middle Value (الوسيط).

sd(x): Standard Deviation (الانحراف المعياري).

range(x): Gives the Min and Max values.

sum(x): Adds all numbers together.

a <- c(0:10, 40)
print(mean(a))    
print(sd(a))      
print(median(a))  
print(sum(a))     


Output:

[1] 7.916667
[1] 10.58694
[1] 5.5
[1] 95


2. User-Defined Functions (إنشاء دالة خاصة)

If you need a specific tool that R doesn't have, you can build it.

Structure:

function_name <- function(arg1, arg2) {
   # Body: What the function does
   return_value
}


Course Example: Printing Squares

new.function <- function() {
    for(i in 1:5) {
        print(i^2)
    }
}
new.function()


Output:

[1] 1
[1] 4
[1] 9
[1] 16
[1] 25


Chapter 7: Handling Real Files (التعامل مع الملفات)

In real data analysis, you don't type data manually; you load it from files.

1. Where are my files? (مسار العمل)

Before reading a file, R needs to know which folder to look in.

getwd(): Get Working Directory (Where am I now?).

setwd("path"): Set Working Directory (Go to this folder).

print(getwd())
# setwd("C:/Users/ajeet") 


Output:

[1] "C:/Users/ajeet/R"


2. CSV Files (ملفات مفصولة بفواصل)

This is the most common format for data.

Reading: Use read.csv().

# Reading a file named "record.csv"
data <- read.csv("record.csv")
print(data)


Output: (Example)

  id    name salary start_date        dept
1  1 Shubham  613.3 2012-01-01          IT
2  2  Arpita  525.2 2013-09-23 Operations


Writing: Use write.csv() to save your analysis to a new file.

# Filter: Get employees who joined after 2014
details <- subset(data, as.Date(start_date) > as.Date("2014-01-01"))

# Save to new file
write.csv(details, "output.csv")


3. Excel Files (ملفات إكسل)

R needs a special package called xlsx to read Excel files.

Install: install.packages("xlsx")

Load: library("xlsx")

Read: read.xlsx("filename.xlsx", sheetIndex = 1)

library("xlsx")
excel_data <- read.xlsx("employee.xlsx", sheetIndex = 1)
print(excel_data)


4. JSON & XML Files

JSON: Use the rjson package and fromJSON() function.

XML: Use the XML package and xmlToDataFrame() function.

Chapter 8: The Analyst at Work (الإحصاء والتحليل)

Now we analyze the data to find patterns.

1. Descriptive Statistics (الإحصاء الوصفي)

Summarizing your data with single numbers.

Central Tendency: Mean (Average), Median (Middle), Mode (Most frequent).

Dispersion: Variance (Spread), Standard Deviation (Avg distance from mean), Range (Max - Min).

Course Example:

data <- c(10, 20, 30, 40, 50)

print(mean(data))
print(median(data))
print(sd(data))


Output:

[1] 30       
[1] 30       
[1] 15.81139 


2. Inferential Statistics (الإحصاء الاستنتاجي)

Testing hypotheses.

T-Test (اختبار T)
Compares two groups to see if they are actually different.

# Compare spending in Cleveland vs New York
# var.equal = TRUE means we assume variances are equal
t.test(Spenders.Cleve, Spenders.NY, var.equal = TRUE)


Chi-Square Test (مربع كاي)
Used for categorical data.

# 'car_data' is a table of categories
chisq.test(car_data)


3. Correlations (الارتباط)

Do two things move together?

+1: Perfect Positive.

-1: Perfect Negative.

0: No relation.

x <- c(1, 2, 3, 4, 5)
y <- c(2, 4, 6, 8, 10)

# Calculate Correlation
cor(x, y) 


Output:

[1] 1


4. Regression (الانحدار)

Predicting one variable based on another ($y = b_0 + b_1x$).

# Create a linear model (lm)
model <- lm(y ~ x)
summary(model)


Output:

Call:
lm(formula = y ~ x)

Coefficients:
(Intercept)            x  
  1.589e-15    2.000e+00  
