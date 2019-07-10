# Dictionaries lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

- Create an instance of a dictionary called `citiesDict` that maps 3 countries to their capital cities.

- Add two more countries to your dictionary.

- Translate at least 3 of the capital names into another language.

```swift
var citiesDict = ["US": "Washington DC", "Philippines": "Manila", "South Korea": "Seoul"]
citiesDict["Japan"] = "Tokyo"
citiesDict["Thailand"] = "Bangkok"
//in Russian
citiesDict["Japan"] = "\u{0422}\u{043E}\u{043A}\u{0438}\u{043E}"
citiesDict["South Korea"] = "\u{0421}\u{0435}\u{0443}\u{043B}"
citiesDict["Philippines"] = "\u{041C}\u{0430}\u{043D}\u{0438}\u{043B}\u{0430}"
print(citiesDict)
```


## Question 2

`var someDict:[String:Int] = ["One": 1, "Two": 4, "Three": 9, "Four": 16, "Five": 25]`

- Using `someDict`, add together the values associated with "Three" and "Five" and print the result.

```swift
if let key3 = someDict["Three"], let key5 = someDict["Five"] {
print(key3 + key5)
}
```
- Add values to the dictionary for the keys "Six" and "Seven".

```swift
someDict["Six"] = 36
someDict["Seven"] = 49
```

- Make a key called `productUpToSeven` and set its value equal to the product of all the values.

```swift
someDict["productUpToSeven"] = 1
for a in someDict.values {
if var product = someDict["productUpToSeven"] {
product *= a
someDict["productUpToSeven"] = product
}
}
print(someDict["productUpToSeven"])
```

- Make a key called `sumUpToSix` and set its value equal to the sum of the keys "One", "Two", "Three", "Four", "Five" and "Six".

```swift
someDict["sumUpToSix"] = 0
for (a, b) in someDict {
if a == "productUpToSeven" || a == "Seven"  {
continue
}
if var sum = someDict["sumUpToSix"] {
sum += b
someDict["sumUpToSix"] = sum
}
}
print(someDict["sumUpToSix"])

```

- Remove the new keys made in the previous two steps

```swift
someDict["productUpToSeven"] = nil
someDict["sumUpToSix"] = nil

print(someDict)
```
- Add 2 to every value inside of `someDict`.

```
for (a, b) in someDict {
if var addTwo = someDict[a] {
addTwo = b + 2
someDict[a] = addTwo
}
}
print(someDict)
```


## Question 3

Create a variable that is explicitly typed as a dictionary that maps strings to floating point numbers. Initialize the variable to the data shown in the table below which lists an author name and their comprehensibility score.

| Author Name |	Score |
| :--: | :--: |
| Mark Twain |	8.9 |
| Nathaniel Hawthorne	| 5.1 |
| John Steinbeck	| 2.3 |
| C.S. Lewis | 9.9 |
| Jon Krakauer | 6.1 |

```swift
var authorDict: [String:Double] = ["Mark Twain":8.9, "Nathaniel Hawthorne":5.1, "John Steinbeck":2.3, "C.S. Lewis":9.9, "John Krakauer":6.1]
```

Using the dictionary created in the previous problem, do the following:

- Print out the floating-point score for “John Steinbeck”.

```swift
print(authorDict["John Steinbeck"])
```

- Add an additional author named “Erik Larson” with an assigned score of 9.2.

```swift
authorDict["Erik Larson"] = 9.2
```

- Write an if/else statement that compares the score of John Krakaur with Mark Twain. Print out the name of the author with the highest score.

```swift
if let john = authorDict["John Krakauer"], let mark = authorDict["Mark Twain"] {
if john > mark {
print("John Krakauer")
} else {
print("Mark Twain")
}
}
```

- Use a for-loop to iterate through the dictionary you created at the beginning of the problem, and print out the content in the form of key: value, one entry per line.

```swift
for a in authorDict {
print(a)
}
```


## Question 4

You are given a dictionary code of type [String:String] which has values for all lowercase letters. The code dictionary represents a way to encode a message. For example if code["a"] = "z" and code["b"] = "x" the encoded version if "ababa" will be "zxzxz". You are also given a message which contains only lowercase letters and spaces. Use the `code` dictionary below to encode the message and print it.

```swift
var code = [
    "a" : "b",
    "b" : "c",
    "c" : "d",
    "d" : "e",
    "e" : "f",
    "f" : "g",
    "g" : "h",
    "h" : "i",
    "i" : "j",
    "j" : "k",
    "k" : "l",
    "l" : "m",
    "m" : "n",
    "n" : "o",
    "o" : "p",
    "p" : "q",
    "q" : "r",
    "r" : "s",
    "s" : "t",
    "t" : "u",
    "u" : "v",
    "v" : "w",
    "w" : "x",
    "x" : "y",
    "y" : "z",
    "z" : "a"
]

var message = "hello world"


for a in message {
for (b, c) in code {
if "\(a)" == "\(b)" {
print(c, terminator: "")
}
}
if "\(a)" == " " {
print(" ", terminator: "")
}
}
```

You are also given an `encodedMessage` which contains only lowercase letters and spaces. Use the `code` dictionary to decode the message and print it.
`var encodedMessage = "uijt nfttbhf jt ibse up sfbe"`

```swift
for a in encodedMessage {
for (b, c) in code {
if "\(a)" == "\(c)" {
print(b, terminator: "")
}
}
if "\(a)" == " " {
print(" ", terminator: "")
}
}
```


## Question 5

You are given an array of dictionaries. Each dictionary in the array contains exactly 2 keys `“firstName”` and `“lastName”`. Create an array of strings called `firstNames` that contains only the values for `“firstName”` from each dictionary.

```swift
var people: [[String:String]] = [
    [
        "firstName": "Calvin",
        "lastName": "Newton"
    ],
    [
        "firstName": "Garry",
        "lastName": "Mckenzie"
    ],
    [
        "firstName": "Leah",
        "lastName": "Rivera"
    ],
    [
        "firstName": "Sonja",
        "lastName": "Moreno"
    ],
    [
        "firstName": "Noel",
        "lastName": "Bowen"
    ]
]


var firstNames: [String] = []

for a in people {
for (b, c) in a {
if b == "firstName" {
firstNames.append(c)
}
}
}
print(firstNames)
```

Now, create an array of strings called `fullNames` that contains the values for `“firstName”` and `“lastName”` from the dictionary separated by a space.

```swift
var fullNames: [String] = []

for a in people {
if let first = a["firstName"], let last = a["lastName"] {
fullNames.append("\(first) \(last)")
}
}
print(fullNames)
```


## Question 6

You are given an array of dictionaries. Each dictionary in the array describes the score of a person. Find the person with the best score and print his full name.

```swift
var peopleWithScores: [[String: String]] = [
    [
        "firstName": "Calvin",
        "lastName": "Newton",
        "score": "13"
    ],
    [
        "firstName": "Garry",
        "lastName": "Mckenzie",
        "score": "23"
    ],
    [
        "firstName": "Leah",
        "lastName": "Rivera",
        "score": "10"
    ],
    [
        "firstName": "Sonja",
        "lastName": "Moreno",
        "score": "3"
    ],
    [
        "firstName": "Noel",
        "lastName": "Bowen",
        "score": "16"
    ]
]

var highest = 0
for a in peopleWithScores {
for (b, c) in a where b == "score" {

if let num = Int(c) {
if num > highest {
highest = num
}
}
}
}

print(highest)
print("\(peopleWithScores[1]["firstName"]) \(peopleWithScores[1]["lastName"])")
```

Print out the dictionary above in the following format:  **full name - score**

```swift
for a in peopleWithScores {
if let first = a["firstName"], let last = a["lastName"], let num = a["score"] {
print("\(first) \(last) - \(num)")
}
}
```

## Question 7

`var numbers = [1, 2, 3, 2, 3, 5, 2, 1, 3, 4, 2, 2, 2]`

You are given an array of integers. The frequency of a number is the number of times it appears in the array. Find out the frequency of each one.

Print the numbers in ascending order followed by their frequency.

```swift
var frequency = 0
var noDupes: [Int] = []

for a in numbers {
if !noDupes.contains(a) {
noDupes.append(a)
}
}

for a in noDupes.sorted() {
for b in numbers {
if a == b {
frequency += 1
}
}
print("\(a) frequency:\(frequency)")
frequency = 0
}
```

## Question 8

Print the most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`

```swift
var alphabet = "abcdefghijklmnopqrstuvwxyz"
var count = 0

var alphabetArray:[Character] = []
for a in alphabet {
alphabetArray.append(a)
}

var countingLetters: [Int] = []
for a in alphabetArray {
for b in myString {
if a == b {
count += 1
}
}
countingLetters.append(count)
count = 0
}

var frequencyDict: [Character:Int] = [:]
for a in 0...25 {
frequencyDict[alphabetArray[a]] = countingLetters[a]
}

for (a, b) in frequencyDict {
let max = countingLetters.max()
if b == max {
print(a)
}
}
```

## Question 9

Write code that creates a dictionary where the keys are Ints between 0 and 20 inclusive, and each key's value is its cube.

```swift
var numCube: [Int:Int] = [:]
for a in 0...20 {
numCube[a] = (a * a)
}
```

## Question 10

Write code that iterates through `testStates` and prints out whether or not that key is in `statePop`.

```swift
let statePop = ["Alabama": 4.8, "Alaska": 0.7, "Arizona": 6.7, "Arkansas": 3.0]
let testStates = ["California","Arizona", "Alabama", "New Mexico"]

for (a, b) in statePop {
for c in testStates {
if a == c {
print(a)
}
}
}
```


## Question 11

You are given the dictionary `deposits`, which maps a persons name to an array of deposits that have been made to their account.

a) Write code to to print the name and total amount deposited of the person who recieved the most money.

b) Create an array called `stolenCents`, iterate over deposits for each person and steal their cents! ... like Office Space or Superman 3. Calculate the decimal part of each value, add it to the `stolenCents` array and round down the value in the dict.

c) How much money did you steal?

```swift
var deposits: [String: [Double]] = [
 "Williams" : [300.65, 270.45, 24.70, 52.00, 99.99],
 "Cooper" : [200.56, 55.00, 600.78, 305.15, 410.76, 35.00],
 "Davies" : [400.98, 56.98, 300.00],
 "Clark" : [555.23, 45.67, 99.95, 80.76, 56.99, 46.50, 265.70],
 "Johnson" : [12.56, 300.00, 640.50, 255.60, 26.88]
]

//a
var total: [String:Double] = [:]
for (a, b) in deposits {
var sum = 0.00
for c in b {
sum += c
}
total[a] = sum
}
print(total)
var findHighest: [Double] = []
for (_, b) in total {
findHighest.append(b)
}
for (c, d) in total {
if d == findHighest.max() {
print(c)
}
}

//b
var stolenCents: [Double] = []
for (a, b) in total {
let x = b.truncatingRemainder(dividingBy: 1)
let y = (x * 100).rounded()/100
stolenCents.append(y)
total[a] = b - y
}
print(stolenCents)

//c
print(stolenCents)
var sum = 0.00
for a in stolenCents {
sum += a
}
print(sum)//3.34
```


## Question 12

Print the second most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`

```swift
var alphabet = "abcdefghijklmnopqrstuvwxyz"

var alphabetArray:[Character] = []
for a in alphabet {
alphabetArray.append(a)
}

var countingLetters: [Int] = []
for a in alphabetArray {
for b in myString {
if a == b {
count += 1
}
}
countingLetters.append(count)
count = 0
}

var frequencyDict: [Character:Int] = [:]
for a in 0...25 {
frequencyDict[alphabetArray[a]] = countingLetters[a]
}

for (a, b) in frequencyDict {
let second = countingLetters.sorted()[24]
if b == second {
print(a)
}
}
```

## Question 13

Given the below 4 arrays of Ints,

a) create a new array, sorted in ascending order, that contains all the values without duplicates.

b) create another new array that contains unique values that appear in all 4 arrays.

```swift
let arr1 = [2, 4, 5, 6, 8, 10, 12]
let arr2 = [1, 2, 3, 4, 5, 6]
let arr3 = [5, 6, 7, 8, 9, 10, 11, 12]
let arr4 = [1, 3, 4, 5, 6, 7, 9]

//a
var withoutDuplicate: [Int] = []
for a in arr1 {
if !withoutDuplicate.contains(a) {
withoutDuplicate.append(a)
}
}

for a in arr2 {
if !withoutDuplicate.contains(a) {
withoutDuplicate.append(a)
}
}

for a in arr3 {
if !withoutDuplicate.contains(a) {
withoutDuplicate.append(a)
}
}

for a in arr4 {
if !withoutDuplicate.contains(a) {
withoutDuplicate.append(a)
}
}
withoutDuplicate = withoutDuplicate.sorted()
print(withoutDuplicate)

//b
var unique: [Int] = []
for a in arr1 {
if arr3.contains(a) && arr2.contains(a) && arr4.contains(a) {
if !unique.contains(a) {
unique.append(a)
}
}
}
```


## Question 14

Given the following exert from the Declaration of Independence, find the most frequent word that is longer than 5 characters.

 - use `components(separatedBy:)` to break up the string into an array.

 - use `CharacterSet.punctuationCharacters` in union with any other characters you don't want in your array, like spaces and new lines.

 ```swift
let declarationOfIndependence = """
When in the Course of human events, it becomes necessary for one people to dissolve the
political bands which have connected them with another, and to assume among the powers of the
earth, the separate and equal station to which the Laws of Nature and of Nature's God entitle
them, a decent respect to the opinions of mankind requires that they should declare the causes
which impel them to the separation.

We hold these truths to be self-evident, that all men are created equal, that they are endowed by
their Creator with certain unalienable Rights, that among these are Life, Liberty and the pursuit
of Happiness. That to secure these rights, Governments are instituted among Men, deriving
their just powers from the consent of the governed, That whenever any Form of Government
becomes destructive of these ends, it is the Right of the People to alter or to abolish it, and to
institute new Government, laying its foundation on such principles and organizing its powers in
such form, as to them shall seem most likely to effect their Safety and Happiness. Prudence,
indeed, will dictate that Governments long established should not be changed for light and
transient causes; and accordingly all experience hath shewn, that mankind are more disposed to
suffer, while evils are sufferable, than to right themselves by abolishing the forms to which they
are accustomed. But when a long train of abuses and usurpations, pursuing invariably the same
Object evinces a design to reduce them under absolute Despotism, it is their right, it is their duty,
to throw off such Government, and to provide new Guards for their future security. Such has
been the patient sufferance of these Colonies; and such is now the necessity which constrains
them to alter their former Systems of Government. The history of the present King of Great
Britain is a history of repeated injuries and usurpations, all having in direct object the
establishment of an absolute Tyranny over these States. To prove this, let Facts be submitted to a
candid world.
"""

var declarationArray: [String] = []
for a in declarationOfIndependence.components(separatedBy: " ") {
for b in a.components(separatedBy: CharacterSet.punctuationCharacters) {
declarationArray.append(a)
}
}
print(declarationArray)
var count = 0
var declaraCount: [Int] = []
var declaraDict: [String:Int] = [:]
for a in declarationArray {
for b in declarationArray {
if a == b {
count += 1
}
}
declaraCount.append(count)
count = 0
}

for a in declarationArray.indices {
declaraDict[declarationArray[a]] = declaraCount[a]
}

for (a, b) in declaraDict {
if b == declaraCount.max() {
print(a)
}
}
```
