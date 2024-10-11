
# Swift Code Snippets

## 1. Remove Specific Item from Array
```swift
var array = [1, 2, 3, 4, 5, 6, 7]
if let index = array.firstIndex(of: 3) {
    array.remove(at: index)
}
print(array)  // Output: [1, 2, 4, 5, 6, 7]
```

## 2. Check for Anagram
```swift
func areAnagrams(_ str1: String, _ str2: String) -> Bool {
    return str1.lowercased().sorted() == str2.lowercased().sorted()
}

print(areAnagrams("listen", "silent"))  // Output: true
```

## 3. Convert Object to Query String
```swift
let params: [String: String] = ["name": "Rana", "age": "90"]
let queryString = params.map { "\($0)=\($1)" }.joined(separator: "&")
print(queryString)  // Output: "name=Rana&age=90"
```

## 4. Delay Execution
```swift
DispatchQueue.main.asyncAfter(deadline: .now() + 2.0) {
    print("Executed after delay")
}
```

## 5. Sum of Array Elements
```swift
let array = [1, 2, 3, 4, 5, 6]
let sum = array.reduce(0, +)
print(sum)  // Output: 21
```

## 6. Get Distinct Characters in String
```swift
let string = "hello world"
let distinctCharacters = Set(string)
print(distinctCharacters)  // Output: ["o", "r", "e", "h", " ", "l", "w", "d"]
```

## 7. Convert Array to Object
```swift
let keys = ["name", "age"]
let values = ["Rana", 90] as [Any]
let dictionary = Dictionary(uniqueKeysWithValues: zip(keys, values))
print(dictionary)  // Output: ["name": "Rana", "age": 90]
```

## 8. Count Occurrences in Array
```swift
let array = ["apple", "banana", "apple", "orange"]
let counts = array.reduce(into: [:]) { counts, word in
    counts[word, default: 0] += 1
}
print(counts)  // Output: ["apple": 2, "banana": 1, "orange": 1]
```

## 9. Generate UUID
```swift
let uuid = UUID().uuidString
print(uuid)
```

## 10. Get Random Element from Array
```swift
let array = [1, 2, 3, 4, 5]
let randomElement = array.randomElement()
print(randomElement)
```

## 11. Convert Celsius to Fahrenheit
```swift
func celsiusToFahrenheit(celsius: Double) -> Double {
    return (celsius * 9/5) + 32
}
print(celsiusToFahrenheit(celsius: 25))  // Output: 77.0
```

## 12. Get Unique Values from Array
```swift
let array = [1, 2, 2, 3, 3, 4, 5, 5]
let uniqueArray = Array(Set(array))
print(uniqueArray)
```

## 13. Get Current Date and Time
```swift
let currentDate = Date() // or .now()
print(currentDate)
```

## 14. Flatten Nested Arrays
```swift
let nestedArray = [[1, 2], [3, 4], [5, 6]]
let flattenedArray = nestedArray.flatMap { $0 }
print(flattenedArray)  // Output: [1, 2, 3, 4, 5, 6]
```

## 15. Sort an Array of Objects
```swift
struct Person {
    let name: String
    let age: Int
}

let people = [Person(name: "Rana", age: 90), Person(name: "jene", age: 85)]
let sortedPeople = people.sorted { $0.age < $1.age }
print(sortedPeople.map { $0.name })  // Output: ["jene", "Rana"]
```

## 16. Check if Number is Even or Odd
```swift
let number = 5
let isEven = number % 2 == 0
print(isEven)  // Output: false
```

## 17. Check for Palindrome
```swift
func isPalindrome(_ str: String) -> Bool {
    let cleanString = str.lowercased().filter { $0.isLetter }
    return cleanString == String(cleanString.reversed())
}
print(isPalindrome("A man a plan a canal Panama"))  // Output: true
```

## 18. Fetch JSON Data
```swift
struct MyData: Decodable {
    let name: String
}

let url = URL(string: "https://api.example.com/data")!
URLSession.shared.dataTask(with: url) { data, response, error in
    if let data = data {
        let decodedData = try? JSONDecoder().decode(MyData.self, from: data)
        print(decodedData?.name)
    }
}.resume()
```

## 19. Random Color Generator
```swift
import SwiftUI

let randomColor = Color(red: .random(in: 0...1), green: .random(in: 0...1), blue: .random(in: 0...1))
print(randomColor)
```

## 20. Convert String to Title Case
```swift
let sentence = "hello world"
let titleCase = sentence.capitalized
print(titleCase)  // Output: "Hello World"
```

## 21. Convert Camel Case to Snake Case
```swift
let camelCase = "camelCaseExample"
let snakeCase = camelCase.unicodeScalars.reduce("") {
    $0 + ($1.properties.isUppercase ? "_" + String($1).lowercased() : String($1))
}
print(snakeCase)  // Output: "camel_case_example"
```

## 22. Get URL Parameters
```swift
if let urlComponents = URLComponents(string: "https://example.com?name=Rana&age=90") {
    let queryParams = urlComponents.queryItems?.reduce(into: [String: String]()) {
        $0[$1.name] = $1.value
    }
    print(queryParams)  // Output: ["name": "Rana", "age": 90"]
}
```

## 23. Capitalize First Letter of Each Word
```swift
let sentence = "rana akbar"
let capitalizedSentence = sentence.split(separator: " ").map { $0.capitalized }.joined(separator: " ")
print(capitalizedSentence)  // Output: "Rana Akbar"
```

## 24. Check if Object is Empty
```swift
let dictionary: [String: Any] = [:]
let isEmpty = dictionary.isEmpty
print(isEmpty)  // Output: true
```

## 25. Random Number Generator
```swift
let randomNumber = Int.random(in: 1...100)
print(randomNumber)
```

## 26. Check if Array is Empty
```swift
let myArray : [String] = [ "Swift", "is", "awesome", "and", "fast"]
let IsArrayEmpty = myArray.isEmpty
print(IsArrayEmpty) //Output : false
```

## 27. Unique Array Elements
```swift
let array = [1, 2, 2, 3, 3, 4, 5, 5, 6, 6, 7, 7]
let uniqueArray = array.reduce(into: [Int]()) { result, element in
    if !result.contains(element) {
        result.append(element)
    }
}
print(uniqueArray)  // Output: [1, 2, 3, 4, 5, 6, 7]
```
```
