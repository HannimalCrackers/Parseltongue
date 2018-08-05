# Adventures in parseltongue

&nbsp;

I just learned how to create syntax highlighted code blocks on GitHub! 

&nbsp;


## 1. ISO Python IDE to love and cherish

_My futile search for a clean, simple code editor user experience_

#### Terminal 
Pro: outputs only the info I want to see. I feel like I'm in the Matrix and/or 1997 <br>
Con: can't edit inline <br>

#### Spyder
Pro: seems cool <br>
Cons: not launching in my Python 2.7 env for some reason. Also, the runfile paths printing doubled up in the console at every single run makes it hard to read output <br>

Example: print (2+5) <br>
yields: runfile('/Users/hhouse/.spyder-py3/temp.py', wdir='/Users/hhouse/.spyder-py3')
7 <br>

#### Sublime Text
Pro: I like it for editing HTML and CSS at work <br>
Con: Very annoying time counter with every output. I tried to customize to quiet build environment but I didn't work. I guess I did it wrong.

#### BBEdit
Pro: Easier to read output (though still annoying extra stuff present) <br>
Con: Maybe doesn't accept input. Getting error: EOFError: EOF when reading a line

#### Visual Studio Code
Pro: Looks like it would be useful if I had any idea what I was doing <br>
Con: I don't have any idea, and I need something that is simpler to understand and get using

#### Brackets
Pro: Again, looks like it would be handy if I wasn't so noo <br>
Con: Needs other things loaded or added in order to accept inputs

#### PyCharm CE
The version I downloaded is free and has a good rep. About to test it out. Maybe 7th time's the (py)charm! <br>

Pro: "Run" is a clearly displayed option in the menu toolbar. Easy to find! <br>
Con: SIGH. Extraneous output. When everything runs correctly still get "Process finished with exit code 0" message. It's annoying, but it seems like I can't escape this output quirk. 

Will keep using PyCharm for now.

UPDATE: PyCharm turned into a massive headache. It suddenly stopped being able to find files, and overall seems overkill for the simple practice I'm doing. I've gone back to Spyder. 


&nbsp;
&nbsp;

## 2. Practice code

&nbsp;


### 2e. Loops

While loop

```python
enter = input("Speak friend and enter. ")
while enter != "friend":
    enter = input("Speak friend and enter. ")
else:
    print ("\n")
    print ("Welcome to Moria!")
```
&nbsp;
&nbsp;


### 2d. List comprehensions

```python
set = [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

evens = [num for num in set if num%2==0]

print(evens)
```
&nbsp;
&nbsp;


### 2c. Calling values from dictionaries

```python
MyColor = {"name": "seafoam blue", "hex": "#89BBBC"} 
print(MyColor["hex"])
```
&nbsp;

``` python
BrandBlue = {"name": "seafoam blue", "hex": "#89BBBC"} 
print("The correct hex formula for Brand Blue is", BrandBlue["hex"])
```
&nbsp; &nbsp; 

### 2b. More practice code

#### Is it a palindrome?
```python
test = input("Hello, please type in a word. ")

if test[0:] == test[::-1]:
    print("Hello, ", test, "is a palindrome.")
else:
    print("Hello, ", test, "is not a palindrome.")
```
&nbsp;
&nbsp;


#### Polite math bot
```python
num = int(input("Hello, let's do some division. Please tell me a number. "))
print("Thank you for the number", num, ".")

check = int(input("Hello, what number would you like me to divide that by? "))
print("Thank you. You'd like me to divide", num, "by", check, ".")

if num % check == 0:
    &nbsp; &nbsp; ans = num/check
    &nbsp; &nbsp; print ("\n")
    &nbsp; &nbsp; print (num, "divided by", check, "is", int(ans), ". ")
else:
    &nbsp; &nbsp; print ("\n")
    &nbsp; &nbsp; print("I'm sorry. That's too hard.")
```
&nbsp;
&nbsp;

#### Tell me a number
```python
num = int(input("Hello, tell me a number: "))
print("Thank you.")

if num % 2 == 0: 
    &nbsp; &nbsp; print ("That was an even number.")
else:
    &nbsp; &nbsp; print("That was an odd number.")
```
&nbsp;
&nbsp;

#### My first Python script
```python
name = input("Hello, what is your name? ")
age = input("Hello again, how old are you? ")
age = int(age)
year = str((100-age)+2018)
print ("\n")
print ("Hello, " + name + ". You will be 100 years old this time of year in " + year + ".")
```

&nbsp; &nbsp;

### 2a. Mathing with pet names

&nbsp; &nbsp;


>>> Earnest = 10000 <br>
>>> print(Earnest)
#### 10000

&nbsp;

>>> Earnest = 5 < 8 <br>
>>> print (Earnest)
#### True

&nbsp;

>>> print("Duvel" + "Bear")
#### DuvelBear

&nbsp;

>>> print ("Duvel " + "Bear")
#### Duvel Bear

&nbsp;

>>> ExtraKitty = 100 <br>
>>> print (ExtraKitty > 6)
#### True

&nbsp;

>>> print ("Duvel " * 3)
#### Duvel Duvel Duvel 

&nbsp;

>>> ss = "Extra Kitty" <br>
>>> print(ss.upper())
#### EXTRA KITTY

 &nbsp;
 
>>> Earnest = "I'm going to eat too fast and puke and then eat that" <br>
>>> print (len(Earnest))
#### 52

&nbsp;

>>> Duvel = "Little orange sunshine" <br>
>>> " ".join(Duvel)
#### 'L i t t l e   o r a n g e   s u n s h i n e'

&nbsp;

>>> print("".join(reversed(Duvel)))
#### enihsnus egnaro elttiL

&nbsp;

 
>>> print(" ; ".join(["Earnest", "Extra Kitty" , "Duvel"]))
#### Earnest ; Extra Kitty ; Duvel

&nbsp; 

>>> Duvel = "Little orange sunshine" <br>
>>> print (Duvel.split())
#### ['Little', 'orange', 'sunshine']
&nbsp;

>>> NewList = (Duvel.split())
>>> print (NewList)
#### ['Little', 'orange', 'sunshine']
&nbsp;

>>> print (" ; ".join(NewList))
#### Little ; orange ; sunshine


&nbsp; 

>>> x = "Earnest loves {} and {}." <br>
>>> print(x.format("treats","hugs"))
#### Earnest loves treats and hugs.

&nbsp; &nbsp;




## 3. Things to be learned

&nbsp;

### Something going wrong here with the line breaks


>>> ''' <br>
... As Ralph likes to say <br>
... My cats breath smells like cat food <br>
... This was a haiku <br>
... '''
#### '\nAs Ralph likes to say\nMy cats breath smells like cat food\nThis was a haiku\n'
&nbsp;

I don't understand **line breaks and escape characters**. Research later.


&nbsp; &nbsp; &nbsp; &nbsp;
  

< [There's no place like home](../index.md)
