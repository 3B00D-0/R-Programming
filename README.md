# The STEM Teacher's Guide to R Programming

Welcome to the STEM Teacher's Guide to R. This repository serves as a comprehensive reference for learning R programming, covering everything from data foundations to statistical analysis, based on the FCI Minia University Data Science curriculum.

## Table of Contents

1. [Chapter 1: The Foundations (أساسيات البيانات)](#chapter-1-the-foundations-أساسيات-البيانات)
2. [Chapter 2: The Grammar of R (قواعد لغة R)](#chapter-2-the-grammar-of-r-قواعد-لغة-r)
3. [Chapter 3: The Toolkit (Operators)](#chapter-3-the-toolkit-operators)
4. [Chapter 4: Organizing Data (Data Structures)](#chapter-4-organizing-data-data-structures)
5. [Chapter 5: Controlling Flow (التحكم في التكرار والقرارات)](#chapter-5-controlling-flow-التحكم-في-التكرار-والقرارات)
6. [Chapter 6: The Toolkit (Functions)](#chapter-6-the-toolkit-functions)
7. [Chapter 7: Handling Real Files (التعامل مع الملفات)](#chapter-7-handling-real-files-التعامل-مع-الملفات)
8. [Chapter 8: The Analyst at Work (الإحصاء والتحليل)](#chapter-8-the-analyst-at-work-الإحصاء-والتحليل)


## Chapter 1: The Foundations (أساسيات البيانات)

Before writing code, we must define **Data**. Data is split into two main types. This is the language you will use to describe your variables.

### 1. Types of Data (أنواع البيانات)

<img width="1024" height="555" alt="types-of-data-1024x555-1" src="https://github.com/user-attachments/assets/89573deb-2035-4074-ba04-dfeab26bf557" />

- **Quantitative (كمي):** Numbers you can count or measure.
    - **Discrete (منفصل):** Whole numbers only.
        - _Classroom Example:_ Number of students (You can't have 2.5 students).
    - **Continuous (مستمر):** Decimals are allowed.
        - _Classroom Example:_ Height (150.5 cm), Weight, Salary.

- **Qualitative (نوعي):** Categories or labels (No math allowed).
    - **Nominal (اسمي):** Categories with **no order**.
        - _Classroom Example:_ Gender (Male/Female), Eye Color.
    - **Ordinal (ترتيبي):** Categories **with a ranking order**.
        - _Classroom Example:_ Ratings (Excellent, Good, Poor), T-Shirt Size (S, M, L).


## Chapter 2: The Grammar of R (قواعد لغة R)

To speak to R, you need to know how to create "words" (Variables) and "sentences" (Assignments).

### 1. R Packages (الحزم البرمجية)

R packages are collections of R functions, sample data, and compiled code. Before you can use special functions, you need to install and load packages.

**Location of packages:** `"C:/Program Files/R/R-3.6.1/library"`

**Working with packages:**

```r
# See all installed packages
library()

# See currently loaded packages
search()

# Install a new package (one time only)
install.packages("XML")

# Load the package (every time you run the script)
library("XML")
```

### 2. Variables (المتغيرات)

A variable is a container. You name it, and you store data inside it.

- **Valid Names (أسماء صحيحة):** `var_name`, `var.name`, `var_name2`
- **Invalid Names (أسماء خاطئة):**
    - `2var_name` (Cannot start with a number)
    - `_var_name` (Cannot start with underscore)
    - `var_name%` (Cannot contain special symbols like %)

#### How to Assign Values (التعيين)

You can use `<-` (Left Arrow) or `=` (Equal sign). The course emphasizes the arrow.

```r
# Assignment using left arrow (Preferred)
variable.2 <- "Learn R Programming"

# Assignment using equal sign
variable.1 = 124

# Printing values
print(variable.1)
cat("variable.2 is", variable.2)
```

**Output:**
```
[1] 124
variable.2 is Learn R Programming
```

### 3. Data Types in R (أنواع البيانات داخل R)

When you store something, R automatically gives it a "Type".

| **Type** | **Arabic** | **Definition** | **Course Example** |
|----------|------------|----------------|-------------------|
| **Numeric** | رقمي | Any number (decimals included). | `12`, `32`, `5432` |
| **Integer** | صحيح | Whole numbers. **Must add 'L'**. | `3L`, `66L`, `2346L` |
| **Character** | نصي | Text. Must use quotes. | `"good"`, `"TRUE"`, `'35.4'` |
| **Logical** | منطقي | True or False. | `TRUE`, `FALSE` |
| **Complex** | مركب | Math with imaginary numbers. | `1+2i` |

#### Checking the Type

Use the `class()` function to ask R "What type is this?".

```r
variable_y <- 124
cat("The data type is", class(variable_y))
```

**Output:**
```
The data type is numeric
```

### 4. Keywords in R (الكلمات المحجوزة)

Keywords are reserved words in R that have special meaning and cannot be used as variable names.

**Control Flow Keywords:**
- `if`, `else`, `for`, `while`, `repeat`, `next`, `break`, `function`, `in`

**Logical Keywords:**
- `TRUE`, `FALSE`

**Special Values:**
- `NULL`, `NA`, `NaN`, `Inf`

### 5. User Input (إدخال البيانات من المستخدم)

You can ask the user to type something using `readline()`.

```r
my.name <- readline(prompt="Enter name: ")
my.age <- readline(prompt="Enter age: ")

# Convert text to number (integer) for math
my.age <- as.integer(my.age)

print(paste("Hi,", my.name, "next year you will be", my.age+1, "years old."))
```

**Output:** (Assuming user types "Mary" and "17")
```
Enter name: Mary
Enter age: 17
[1] "Hi, Mary next year you will be 18 years old."
```

### 6. Dynamic Typing (الأنواع الديناميكية)

R is dynamically typed, meaning you can change a variable's type during program execution.

```r
var <- 123        # Numeric
var <- "text"     # Now Character
var <- TRUE       # Now Logical
```


## Chapter 3: The Toolkit (Operators)

Operators are the symbols used to do math or compare logic.

### 1. Arithmetic Operators (العمليات الحسابية)

Used for math calculations.

```r
a <- c(2, 3.3, 4)
b <- c(11, 5, 3)

print(a + b)   # Addition
print(a - b)   # Subtraction
print(a * b)   # Multiplication
print(a / b)   # Division
print(a %% b)  # Remainder (Modulus) - باقي القسمة
print(a %/% b) # Integer Division (No decimals) - القسمة الصحيحة
print(a ^ b)   # Exponent (Power) - الأس
```

**Output:**
```
[1] 13.0 8.3 7.0       # Addition
[1] -9.0 -1.7 1.0      # Subtraction
[1] 22.0 16.5 12.0     # Multiplication
[1] 0.1818182 0.66 1.333333  # Division
[1] 2.0 3.3 1.0        # Remainder
[1] 0 0 1              # Integer Division
[1] 2048.0 391.3 64.0  # Power
```

### 2. Relational Operators (عمليات المقارنة)

These return `TRUE` or `FALSE`.

```r
a <- c(1, 3, 5)
b <- c(2, 4, 6)

print(a > b)   # Greater than (أكبر من)
print(a < b)   # Less than (أصغر من)
print(a == b)  # Equal to (يساوي - note double =)
print(a != b)  # Not Equal to (لا يساوي)
print(a >= b)  # Greater or Equal
print(a <= b)  # Less or Equal
```

**Output:**
```
[1] FALSE FALSE FALSE  # Greater than
[1] TRUE TRUE TRUE     # Less than
[1] FALSE FALSE FALSE  # Equal to
[1] TRUE TRUE TRUE     # Not Equal to
[1] FALSE FALSE FALSE  # Greater or Equal
[1] TRUE TRUE TRUE     # Less or Equal
```

### 3. Logical Operators (العمليات المنطقية)

Used to combine multiple conditions.

- `&` **(Element-wise AND):** Checks every item in a list.
- `|` **(Element-wise OR):** Checks every item.
- `!` **(NOT):** Reverses the result.
- `&&` **(Single AND):** Checks only the first element (Good for `if` statements).
- `||` **(Single OR):** Checks only the first element.

```r
a <- c(3, 0, TRUE, 2+2i)
b <- c(2, 4, TRUE, 2+3i)

print(a & b)  # Element-wise AND
print(a | b)  # Element-wise OR
print(!a)     # NOT
```

**Output:**
```
[1] TRUE FALSE TRUE TRUE   # AND result
[1] TRUE TRUE TRUE TRUE    # OR result
[1] FALSE TRUE FALSE FALSE # NOT result
```

### 4. Assignment Operators (عمليات التعيين)

Different ways to assign values to variables.

```r
# Leftward assignment
var1 <- 10
var2 <<- 20   # Global assignment

# Rightward assignment
30 -> var3
40 ->> var4   # Global assignment

# Equal sign assignment
var5 = 50
```

### 5. Miscellaneous Operators (أدوات متنوعة)

- `:` **(Sequence):** Creates a series of numbers (e.g., `1:10`).
- `%in%` **(Membership):** Checks if an element belongs to a vector.
- `%*%` **(Matrix Multiplication):** Multiplies a matrix with its transpose.

```r
# Sequence operator
v <- 1:5
print(v)

# Membership operator
print(3 %in% v)  # Returns TRUE

# Matrix Multiplication
M <- matrix(c(2,6,5,1,10,4), nrow=2, ncol=3, byrow=TRUE)
t <- M %*% t(M)
print(t)
```

**Output:**
```
[1] 1 2 3 4 5
[1] TRUE
     [,1] [,2]
[1,]   65   37
[2,]   37  117
```


## Chapter 4: Organizing Data (Data Structures)

R has specific ways to organize groups of data.

### 1. Vectors (المتجهات)

A single row of data. **Must be all the same type**.

```r
# Atomic Vectors
numeric_vector <- c(1, 2, 3, 4, 5)
character_vector <- c("apple", "banana", "orange")
logical_vector <- c(TRUE, FALSE, TRUE)
```

### 2. Lists (القوائم)

A mixed bag. Can hold numbers, text, and logic all at once.

```r
# Creating a list
my_list <- list(name = "John", age = 30, is_student = TRUE)

# Accessing items using the $ sign
print(my_list$name)
```

**Output:**
```
[1] "John"
```

### 3. Arrays (المصفوفات متعددة الأبعاد)

Multi-dimensional structures. The PDF shows 2D examples.

```r
# Create a 2D array (like a matrix but using array syntax)
my_array <- array(data = 1:12, dim = c(3, 4))
print(my_array)
```

**Output:**
```
     [,1] [,2] [,3] [,4]
[1,]    1    4    7   10
[2,]    2    5    8   11
[3,]    3    6    9   12
```

### 4. Matrices (المصفوفات)

A 2-dimensional grid (rows and columns) of the **same data type**.

```r
# Create a 3x3 matrix with numbers 1 to 9
mat <- matrix(1:9, nrow = 3, ncol = 3)
print(mat)
```

**Output:**
```
     [,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
```

**Matrix Indexing:** Access elements using `mat[row, col]`

```
     Col 1  Col 2
Row 1  10    11     mat[1,1]=10, mat[1,2]=11
Row 2  12    13     mat[2,1]=12, mat[2,2]=13
```

### 5. Data Frames (إطارات البيانات)

The most important structure. Like an Excel sheet with columns of different types.

```r
df <- data.frame(
    name = c("Alice", "Bob", "Charlie"),
    age = c(25, 30, 35),
    gender = c("F", "M", "M")
)
print(df)
```

**Output:**
```
     name age gender
1   Alice  25      F
2     Bob  30      M
3 Charlie  35      M
```

### 6. Factors (الفئات)

Used for categorical data (Ordinal/Nominal). It stores text as levels internally to save memory.

```r
data <- c("A", "B", "A", "C")
factor_data <- factor(data)
print(factor_data)
```

**Output:**
```
[1] A B A C
Levels: A B C
```


## Chapter 5: Controlling Flow (التحكم في التكرار والقرارات)

### 1. Decisions (If / Else)

```r
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
```

**Output:**
```
24 is an even number
```

### 2. Switch Statement

Useful for specific choices.

```r
# Example: User chooses "9" for Addition
choice <- "9"
a <- 10
b <- 2

result <- switch(
    choice,
    "9" = cat("Addition =", a + b),
    "12" = cat("Subtraction =", a - b)
)
```

**Output:**
```
Addition = 12
```

### 3. Loops (التكرار)

#### For Loop

Repeat a specific number of times.

```r
fruit <- c('Apple', 'Orange', 'Guava')
for (i in fruit) {
    print(i)
}
```

**Output:**
```
[1] "Apple"
[1] "Orange"
[1] "Guava"
```

#### While Loop

Repeat while a condition is true.

```r
cnt <- 2
while (cnt < 5) {
    print("Hello")
    cnt <- cnt + 1
}
```

**Output:**
```
[1] "Hello"
[1] "Hello"
[1] "Hello"
```

#### Repeat Loop

Repeat forever until a break condition is met.

```r
cnt <- 2
repeat {
    print("Hello")
    cnt <- cnt + 1
    if (cnt > 4) {
        break
    }
}
```

**Output:**
```
[1] "Hello"
[1] "Hello"
[1] "Hello"
```

### 4. Jump Statements (التحكم في الحلقة)

- **Break:** Stops the loop immediately.
- **Next:** Skips the current iteration and jumps to the next one.

```r
x <- 1:5
for (val in x) {
    if (val == 3) {
        next  # Skip printing 3
    }
    print(val)
}
```

**Output:**
```
[1] 1
[1] 2
[1] 4
[1] 5
```


## Chapter 6: The Toolkit (Functions)

A Function (الدالة) is like a machine. You put raw materials in (Arguments), the machine does the work (Body), and it gives you a finished product (Return Value).

### 1. Built-in Functions (أدوات جاهزة)

#### Math Functions (دوال رياضية)

- `abs(x)`: Absolute value.
- `sqrt(x)`: Square root.
- `ceiling(x)`: Round up.
- `floor(x)`: Round down.
- `trunc(x)`: Truncate decimals.
- `round(x, digits=n)`: Round to decimal places.

```r
x <- -4.5
print(abs(x))       # Absolute value
print(ceiling(x))   # Round Up
print(floor(x))     # Round Down
print(sqrt(16))     # Square Root
```

**Output:**
```
[1] 4.5
[1] -4
[1] -5
[1] 4
```

#### String Functions (دوال نصية)

- `substr(x, start, stop)`: Extract text.
- `grep(pattern, x)`: Search for a pattern in text.
- `sub(pattern, replacement, x)`: Replace text (first occurrence).
- `gsub(pattern, replacement, x)`: Replace text (all occurrences).
- `strsplit(x, split)`: Split text into parts.
- `paste(...)`: Combine text pieces.
- `toupper(x)` / `tolower(x)`: Change case.

```r
text <- "GoodMorning"
print(substr(text, 1, 4))        # Get first 4 letters
print(toupper("hello"))          # Make capital
print(paste("Data", "Science"))  # Combine words

# Replacement example
st1 <- "England is beautiful"
print(sub("England", "UK", st1))
```

**Output:**
```
[1] "Good"
[1] "HELLO"
[1] "Data Science"
[1] "UK is beautiful"
```

#### Statistical Functions (دوال إحصائية)

- `mean(x)`: The Average (المتوسط).
- `median(x)`: The Middle Value (الوسيط).
- `var(x)`: Variance (التباين).
- `sd(x)`: Standard Deviation (الانحراف المعياري).
- `range(x)`: Gives the Min and Max values.
- `sum(x)`: Adds all numbers together.
- `min(x)`, `max(x)`: Minimum and maximum values.

#### Graphics Functions (دوال الرسوم البيانية)

- `plot(x, y, type=...)`: Creates various types of plots.
    - `type="p"`: Points (Scatter plot).
    - `type="l"`: Lines (Line plot).

```r
x <- c(1, 2, 3, 4, 5)
y <- c(2, 4, 6, 8, 10)

# Scatter Plot
plot(x, y, type="p", main="Scatter Plot", xlab="X", ylab="Y", col="blue")

# Line Plot
plot(x, y, type="l", main="Line Plot", xlab="X", ylab="Y", col="red")
```

### 2. User-Defined Functions (إنشاء دالة خاصة)

If you need a specific tool that R doesn't have, you can build it.

**Structure:**
```r
function_name <- function(arg1, arg2) {
    # Body: What the function does
    result <- arg1 + arg2
    return(result)
}
```

**Example: Creating a function to print squares of numbers**

```r
new.function <- function(a) {
    for(i in 1:a) {
        b <- i^2
        print(b)
    }
}

# Calling the function with 5
new.function(5)
```

**Output:**
```
[1] 1
[1] 4
[1] 9
[1] 16
[1] 25
```


## Chapter 7: Handling Real Files (التعامل مع الملفات)

In real data analysis, you don't type data manually; you load it from files.

### 1. Working Directory (مسار العمل)

Before reading a file, R needs to know which folder to look in.

- `getwd()`: Get Working Directory (Where am I now?).
- `setwd("path")`: Set Working Directory (Go to this folder).

```r
# Check current directory
print(getwd())

# Example output on Windows:
# [1] "C:/Program Files/R/R-3.6.1/library"

# Change directory
# setwd("C:/Users/Student/Documents")
```

### 2. CSV Files (ملفات مفصولة بفواصل)

This is the most common format for data.

**Reading:** Use `read.csv()`.

```r
data <- read.csv("record.csv")
print(data)
```

**Example Output:**
```
  id    name salary start_date       dept
1  1 Shubham  613.3 2012-01-01         IT
2  2  Arpita  525.2 2013-09-23 Operations
```

**Analyzing CSV Data:**

```r
# Get column names
print(colnames(data))

# Get structure
str(data)

# Get summary statistics
summary(data)

# Filter: Get employees who joined after 2014
details <- subset(data, as.Date(start_date) > as.Date("2014-01-01"))
```

**Writing:** Use `write.csv()` to save your analysis to a new file.

```r
# Filter data
details <- subset(data, as.Date(start_date) > as.Date("2014-01-01"))

# Save to new file (without row numbers)
write.csv(details, "output.csv", row.names = FALSE)
```

### 3. Excel Files (ملفات إكسل)

R needs a special package called `xlsx` to read Excel files.

```r
# 1. Install (One time only)
install.packages("xlsx")

# 2. Load the package
library("xlsx")

# 3. Read Excel file
data <- read.xlsx("employee.xlsx", sheetIndex = 1)
print(data)

# 4. Write to Excel file
write.xlsx(data, "output.xlsx", sheetName = "Sheet1", row.names = FALSE)
```

### 4. JSON Files (ملفات جيسون)

JSON stands for JavaScript Object Notation. Use the `rjson` package.

```r
# Install and load
install.packages("rjson")
library("rjson")

# Read JSON file
result <- fromJSON(file = "input.json")
print(result)

# Convert to Data Frame
data.frame <- as.data.frame(result)
```

### 5. XML Files (ملفات إكس إم إل)

XML stands for Extensible Markup Language. Use the `XML` package.

```r
# Install and load
install.packages("XML")
library("XML")

# Parse XML file
result <- xmlParse(file = "input.xml")
print(result)

# Get root node
rootnode <- xmlRoot(result)

# Convert to Data Frame
xmldataframe <- xmlToDataFrame("input.xml")
print(xmldataframe)
```


## Chapter 8: The Analyst at Work (الإحصاء والتحليل)

Now we analyze the data to find patterns.

### 1. Descriptive Statistics (الإحصاء الوصفي)

Summarizing your data with single numbers.

#### A. Central Tendency (نزعة مركزية)

- **Mean (المتوسط):** The average.
- **Median (الوسيط):** The exact middle number.
- **Mode (المنوال):** The most frequently occurring value.

**Important Note:** R's built-in `mode()` function does NOT calculate the statistical mode. You must create a custom function.

```r
data <- c(10, 20, 30, 40, 50)

# Mean
print(mean(data))

# Median
print(median(data))

# Custom Mode Function
mode <- function(x) {
    ux <- unique(x)
    ux[which.max(tabulate(match(x, ux)))]
}
print(mode(data))
```

**Output:**
```
[1] 30        # Mean
[1] 30        # Median
[1] 10        # Mode (first value in this case)
```

#### B. Dispersion (التشتت)

How "spread out" is the data?

- **Variance (σ²):** How far numbers are from the mean.
- **Standard Deviation (σ):** The average distance from the mean (square root of variance).
- **Range:** Max minus Min.
- **Interquartile Range (IQR):** The range of the middle 50% of data.

```r
data <- c(10, 20, 30, 40, 50)

print(var(data))      # Variance
print(sd(data))       # Standard Deviation
print(range(data))    # Min and Max
print(IQR(data))      # Interquartile Range
```

**Output:**
```
[1] 250         # Variance
[1] 15.81139    # Standard Deviation
[1] 10 50       # Range
[1] 20          # IQR
```

#### C. Percentiles and Quartiles (النسب المئوية والربعيات)

- **Percentile:** The value below which a percentage of data falls.
- **Quartiles:** Q1 (25%), Q2 (50% = Median), Q3 (75%)

```r
data <- c(10, 20, 30, 40, 50)

# Get specific percentiles
print(quantile(data, 0.25))  # 25th Percentile (Q1)
print(quantile(data, 0.50))  # 50th Percentile (Q2 = Median)
print(quantile(data, 0.75))  # 75th Percentile (Q3)
```

#### D. Interquartile Range (IQR) and Outliers

**IQR = Q3 - Q1**

Outliers are values that fall outside:
- **Lower Bound:** Q1 - 1.5 × IQR
- **Upper Bound:** Q3 + 1.5 × IQR

```r
data <- c(10, 20, 30, 40, 50, 100)  # 100 might be an outlier

Q1 <- quantile(data, 0.25)
Q3 <- quantile(data, 0.75)
IQR_value <- IQR(data)

# Calculate outlier boundaries
lower_bound <- Q1 - 1.5 * IQR_value
upper_bound <- Q3 + 1.5 * IQR_value

cat("Lower Bound:", lower_bound, "\n")
cat("Upper Bound:", upper_bound, "\n")

# Find outliers
outliers <- data[data < lower_bound | data > upper_bound]
print(outliers)
```

#### E. Skewness (الالتواء)

Skewness measures how much the distribution deviates from normal.

- **Normal Distribution:** Mean = Median = Mode
- **Right Skewed (Positive):** Mode < Median < Mean
- **Left Skewed (Negative):** Mean < Median < Mode

### 2. Inferential Statistics (الإحصاء الاستنتاجي)

Testing hypotheses (Testing a guess).

#### T-Test (اختبار T)

Compares means to see if they are significantly different.

**Types:**
1. **One Sample T-Test:** Compare sample mean to a known value.
2. **Paired Sample T-Test:** Compare two related samples.
3. **Independent T-Test:** Compare two independent groups.

```r
# One Sample T-Test
# Test if the mean is significantly different from 30
data <- c(25, 28, 31, 35, 29)
t.test(data, mu = 30)

# Independent T-Test (Equal variance assumed)
group1 <- c(23, 25, 27, 29)
group2 <- c(30, 32, 35, 37)
t.test(group1, group2, var.equal = TRUE)

# Independent T-Test (Equal variance NOT assumed)
t.test(group1, group2, var.equal = FALSE)
```

#### Chi-Square Test (اختبار مربع كاي)

Used for categorical data to test relationships between variables.

```r
# Example: Relationship between car type and safety
# Create a contingency table
car_data <- table(car_type, safety_rating)

# Perform Chi-Square test
chisq.test(car_data)
```

### 3. Correlation (الارتباط)

Measures the relationship between two variables.

**Correlation Coefficient (r):**
- **+1:** Perfect positive correlation (both increase together).
- **-1:** Perfect negative correlation (one increases, other decreases).
- **0:** No relationship.

```r
x <- c(1, 2, 3, 4, 5)
y <- c(2, 4, 6, 8, 10)

# Calculate Correlation
cor_value <- cor(x, y)
print(cor_value)
```

**Output:**
```
[1] 1
```
(This means a perfect positive relationship)

### 4. Regression (الانحدار)

Predicting one variable based on another using a formula: **y = b₀ + b₁x**

```r
x <- c(1, 2, 3, 4, 5)
y <- c(2, 4, 6, 8, 10)

# Create a linear model
model <- lm(y ~ x)

# View model summary
summary(model)

# Make predictions
new_x <- data.frame(x = c(6, 7))
predictions <- predict(model, new_x)
print(predictions)
```

**Understanding the Output:**
- **Coefficients:** Shows the intercept (b₀) and slope (b₁).
- **R-squared:** Explains how much variance in y is explained by x (closer to 1 is better).
- **p-value:** Tests if the relationship is statistically significant (< 0.05 is good).

---

---

## Additional Resources

### Installation Guide

1. **Download R:** https://cloud.r-project.org/bin/windows/base/
2. **Download RStudio:** https://posit.co/download/rstudio-desktop/
3. **Online R Tools:**
   - RStudio Cloud
   - Google Colab (with R kernel)
   - repl.it

### Useful R Commands Reference

```r
# Help and Documentation
?function_name      # Get help on a function
help(topic)         # Search help
example(function)   # See examples

# Working with Data
head(data)          # View first 6 rows
tail(data)          # View last 6 rows
str(data)           # Structure of data
summary(data)       # Summary statistics
dim(data)           # Dimensions (rows, cols)
names(data)         # Column names

# Data Manipulation
subset(data, condition)     # Filter rows
data$new_col <- values      # Add column
data[, c("col1", "col2")]   # Select columns

# Basic Plotting
hist(data)          # Histogram
boxplot(data)       # Box plot
barplot(data)       # Bar chart
```

---

## Practice Problems

### Problem 1: Data Types
Create variables of each data type and verify using `class()`.

### Problem 2: Operators
Calculate the following:
- Is 127 divisible by 7?
- What is 2^10?
- Is 50 in the vector c(10, 20, 30, 40, 50)?

### Problem 3: Loops
Write a for loop that prints all even numbers from 1 to 20.

### Problem 4: Functions
Create a function that calculates the area of a circle given the radius.

### Problem 5: Statistics
Given data: c(12, 15, 18, 20, 22, 25, 28, 30)
- Calculate mean, median, and standard deviation
- Identify any outliers using the IQR method

---

## Summary

This guide covers the complete R Programming curriculum from FCI Minia University's Data Science course. It includes:

- **Data Foundations:** Understanding variable types
- **R Grammar:** Variables, data types, and packages
- **Operators:** Arithmetic, relational, logical operations
- **Data Structures:** Vectors, lists, matrices, data frames, factors
- **Control Flow:** Conditionals and loops
- **Functions:** Built-in and user-defined
- **File Handling:** CSV, Excel, JSON, XML
- **Statistical Analysis:** Descriptive and inferential statistics

For questions or contributions, please open an issue on GitHub.

---

**Course Reference:** FCI Minia University - Data Science Labs [1-9]  
**Last Updated:** December 2024
