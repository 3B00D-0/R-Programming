The STEM Teacher’s Guide to R ProgrammingWelcome to the STEM Teacher's Guide to R. This repository serves as a comprehensive reference for learning R programming, covering everything from data foundations to statistical analysis, based on the University Data Science curriculum.Table of ContentsChapter 1: The Foundations (أساسيات البيانات)Chapter 2: The Grammar of R (قواعد لغة R)Chapter 3: The Toolkit (Operators)Chapter 4: Organizing Data (Data Structures)Chapter 5: Controlling Flow (التحكم في التكرار والقرارات)Chapter 6: The Toolkit (Functions)Chapter 7: Handling Real Files (التعامل مع الملفات)Chapter 8: The Analyst at Work (الإحصاء والتحليل)Chapter 1: The Foundations (أساسيات البيانات)Before writing code, we must define Data. Data is split into two main types. This is the language you will use to describe your variables.1. Types of Data (أنواع البيانات)Quantitative (كمي): Numbers you can count or measure.Discrete (منفصل): Whole numbers only.Classroom Example: Number of students (You can't have 2.5 students).Continuous (مستمر): Decimals are allowed.Classroom Example: Height (150.5 cm), Weight, Salary.Qualitative (نوعي): Categories or labels (No math allowed).Nominal (اسمي): Categories with no order.Classroom Example: Gender (Male/Female), Eye Color.Ordinal (ترتيبي): Categories with a ranking order.Classroom Example: Ratings (Excellent, Good, Poor), T-Shirt Size (S, M, L).Chapter 2: The Grammar of R (قواعد لغة R)To speak to R, you need to know how to create "words" (Variables) and "sentences" (Assignments).1. Variables (المتغيرات)A variable is a container. You name it, and you store data inside it.Valid Names (أسماء صحيحة): var_name, var.name, var_name2Invalid Names (أسماء خاطئة):2var_name (Cannot start with a number)_var_name (Cannot start with underscore)var_name% (Cannot contain special symbols like %)How to Assign Values (التعيين)You can use <- (Left Arrow) or = (Equal sign). The course emphasizes the arrow.# Assignment using left arrow (Preferred)
variable.2 <- "Learn R Programming"

# Assignment using equal sign
variable.1 = 124

# Assignment using right arrow (Valid in R)
133 -> variable.3

# Printing values
print(variable.1)
cat("variable.2 is", variable.2)
print(variable.3)
2. Data Types in R (أنواع البيانات داخل R)When you store something, R automatically gives it a "Type".TypeArabicDefinitionCourse ExampleNumericرقميAny number (decimals included).12, 32, 5432IntegerصحيحWhole numbers. Must add 'L'.3L, 66L, 2346LCharacterنصيText. Must use quotes."good", "TRUE", '35.4'LogicalمنطقيTrue or False.TRUE, FALSEComplexمركبMath with imaginary numbers.1+2iRawخامHolds raw bytes.charToRaw("Hello")Checking the TypeUse the class() function to ask R "What type is this?".variable_y <- 124
cat("The data type is", class(variable_y)) 
3. R Packages (الحزم البرمجية)R uses "packages" to extend its functionality (like adding Excel support).# 1. Install a package (One time only)
# install.packages("XML")

# 2. Load the package (Every time you run the script)
library("XML")
4. User Input (إدخال البيانات من المستخدم)You can ask the user to type something using readline().my.name <- readline(prompt="Enter name: ")
my.age <- readline(prompt="Enter age: ")

# Convert text to number (integer) for math
my.age <- as.integer(my.age)

print(paste("Hi,", my.name, "next year you will be", my.age+1))
Chapter 3: The Toolkit (Operators)Operators are the symbols used to do math or compare logic.1. Arithmetic Operators (العمليات الحسابية)Used for math calculations.a <- c(2, 3.3, 4)
b <- c(11, 5, 3)

print(a + b)   # Addition
print(a - b)   # Subtraction
print(a * b)   # Multiplication
print(a / b)   # Division
print(a %% b)  # Remainder (Modulus)
print(a %/% b) # Integer Division (No decimals)
print(a ^ b)   # Exponent (Power)
2. Relational Operators (عمليات المقارنة)These return TRUE or FALSE.a <- c(1, 3, 5)
b <- c(2, 4, 6)

print(a > b)   # Greater than
print(a < b)   # Less than
print(a == b)  # Equal to (Note double =)
print(a != b)  # Not Equal to
print(a >= b)  # Greater or Equal
print(a <= b)  # Less or Equal
3. Logical Operators (العمليات المنطقية)Used to combine multiple conditions.& (Element-wise AND): Checks every item in a list.| (Element-wise OR): Checks every item.! (NOT): Reverses the result.&& (Single AND): Checks only the first element.|| (Single OR): Checks only the first element.a <- c(TRUE, FALSE, TRUE)
b <- c(FALSE, TRUE, TRUE)

print(a & b)
print(a | b)
print(!a)
4. Miscellaneous Operators (أدوات متنوعة): (Sequence): Creates a series of numbers (e.g., 1:10).%in% (Membership): Checks if an element belongs to a vector.%*% (Matrix Multiplication): Multiplies a matrix with its transpose.# Sequence and Membership
v <- 1:5 
print(3 %in% v) # Returns TRUE

# Matrix Multiplication
M = matrix( c(2,6,5,1,10,4), nrow = 2, ncol = 3, byrow = TRUE)
t = M %*% t(M)
print(t)
Chapter 4: Organizing Data (Data Structures)R has specific ways to organize groups of data.1. Vectors (المتجهات)A single row of data. Must be all the same type.# Atomic Vectors
numeric_vector <- c(1, 2, 3, 4, 5)
character_vector <- c("apple", "banana", "orange")
logical_vector <- c(TRUE, FALSE, TRUE)
2. Lists (القوائم)A mixed bag. Can hold numbers, text, and logic all at once.my_list <- list(name = "John", age = 30, is_student = TRUE)
print(my_list$name) # Accessing via $
3. Matrices (المصفوفات)A 2-dimensional grid (rows and columns) of the same data type.# Create a 3x3 matrix with numbers 1 to 9
mat <- matrix(1:9, nrow = 3, ncol = 3)
print(mat)
4. Arrays (المصفوفات متعددة الأبعاد)Similar to matrices but can have more than two dimensions (3D, 4D, etc.).# Create an array with two 3x3 matrices
my_array <- array(data = 1:18, dim = c(3, 3, 2))
print(my_array)
5. Data Frames (إطارات البيانات)The most important structure. Like an Excel sheet with columns of different types.df <- data.frame(
    name = c("Alice", "Bob", "Charlie"),
    age = c(25, 30, 35),
    gender = c("F", "M", "M")
)
print(df)
6. Factors (الفئات)Used for categorical data (Ordinal/Nominal).data <- c("A", "B", "A", "C")
factor_data <- factor(data)
print(factor_data)
Chapter 5: Controlling Flow (التحكم في التكرار والقرارات)1. Decisions (If / Else)x <- 24

if (is.integer(x)) {
    print("x is an Integer")
}

if (x %% 2 == 0) {
    cat(x, "is an even number")
} else {
    cat(x, "is an odd number")
}
2. Switch StatementUseful for specific choices.choice <- "9" 
a <- 10; b <- 2

result <- switch(
    choice,
    "9" = paste("Addition =", a + b),
    "12" = paste("Subtraction =", a - b)
)
print(result)
3. Loops (التكرار)For LoopRepeat a specific number of times.fruit <- c('Apple', 'Orange', 'Guava')
for (i in fruit) {
    print(i)
}
While LoopRepeat while a condition is true.cnt <- 2
while (cnt < 5) {
    print("Hello")
    cnt <- cnt + 1
}
Repeat LoopRepeat forever until a break condition is met.cnt <- 2
repeat {
    print("Hello")
    cnt <- cnt + 1
    if (cnt > 4) {
        break
    }
}
4. Jump Statements (التحكم في الحلقة)Break: Stops the loop immediately.Next: Skips the current iteration and jumps to the next one.x <- 1:5
for (val in x) {
    if (val == 3) {
        next  # Skip printing 3
    }
    print(val)
}
Chapter 6: The Toolkit (Functions)1. Built-in Functions (أدوات جاهزة)Math Functionsabs(x): Absolute value.sqrt(x): Square root.ceiling(x): Round up.floor(x): Round down.trunc(x): Truncate decimals.round(x, digits=n): Round to decimal places.String Functions (دوال نصية)substr(x, start, stop): Extract text.grep(pattern, x): Search for a pattern in text.sub(pattern, replacement, x): Replace text.strsplit(x, split): Split text into parts.toupper(x) / tolower(x): Change case.st1 <- "England is beautiful"
print(sub("England", "UK", st1)) # Replaces England with UK
Statistical Functionsmean(x), median(x), sd(x), range(x), sum(x).Graphics Functions (الرسوم البيانية)plot(x, y, type=...): Creates various types of plots.type="p": Points (Scatter plot).type="l": Lines (Line plot).x <- c(1, 2, 3, 4, 5)
y <- c(2, 4, 6, 8, 10)
# Create a basic Scatter Plot
plot(x, y, main="Scatter Plot", xlab="X", ylab="Y", col="blue")
2. User-Defined Functions (إنشاء دالة خاصة)new.function <- function(a) {
    for(i in 1:a) {
        print(i^2)
    }
}
new.function(5) # Call the function
Chapter 7: Handling Real Files (التعامل مع الملفات)1. CSV FilesRead: data <- read.csv("record.csv")Write: write.csv(data, "output.csv")2. Excel FilesRequires the xlsx package.install.packages("xlsx")
library("xlsx")
data <- read.xlsx("employee.xlsx", sheetIndex = 1)
3. JSON & XML FilesJSON: Requires rjson. Use fromJSON().XML: Requires XML. Use xmlParse() and xmlToDataFrame().Chapter 8: The Analyst at Work (الإحصاء والتحليل)1. Descriptive Statistics (الإحصاء الوصفي)Summarizing data to find the center and the spread.Central Tendency: Mean (Average), Median (Middle), Mode (Most frequent).Dispersion (Variation):Variance (var): How far numbers are from the mean.Standard Deviation (sd): The square root of variance.Range: Difference between min and max.Percentile (quantile): The value below which a percentage of data falls.Important Note: R's built-in mode() function does NOT calculate the statistical mode (it checks storage type). You must create a custom function for this.data <- c(10, 20, 30, 40, 50)

# Standard Functions
print(var(data))      # Variance
print(sd(data))       # Standard Deviation
print(quantile(data, 0.25)) # 25th Percentile

# Custom Mode Function (Required for correct output)
mode <- function(x) {
  ux <- unique(x)
  ux[which.max(tabulate(match(x, ux)))]
}
print(mode(data))
2. Inferential Statistics (الإحصاء الاستنتاجي)T-Test (اختبار T)Compares means.# One sample T-test
t.test(data, mu=30)
Chi-Square Test (مربع كاي)For categorical relationships.chisq.test(table_data)
3. Correlations (الارتباط)Does x move with y?cor(x, y) # Returns between -1 (Negative) and +1 (Positive)
4. Regression (الانحدار)Predicting y based on x.model <- lm(y ~ x)
summary(model)
