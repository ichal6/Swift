# Sprawozdanie nr 9 (Tasks in Polish)
## Michał Lechowicz
### Programowanie Mobilne 2022/2023
#### Swift
 
1. Deklarowanie zmiennych i interpolacja ciągu tekstowego:

```swift
var points = 5.0
print("Student has \(points) points.")
```

2. Wyrażenie warunkowe:
```swift
import Foundation


let points = 80 // replace with actual student points
let satisfactionLevel = round(pow(Double.random(in: 0...1), (110 - Double(points)) / 100) * 20)

var auraColor: String

switch satisfactionLevel {
case 0...5:
    auraColor = "red"
case 6...10:
    auraColor = "orange"
case 11...15:
    auraColor = "purple"
default:
    auraColor = "green"
}

print("Satisfaction Level: \(satisfactionLevel), Aura Color: \(auraColor)")
```
3. Klasy:
```swift
class Student {
    var firstName: String
    var lastName: String
    var points: Int
    
    init(firstName: String, lastName: String, points: Int) {
        self.firstName = firstName
        self.lastName = lastName
        self.points = points
    }
}

let student1 = Student(firstName: "Jan", lastName: "Kowalski", points: 80)
print(student1.firstName) // Jan
print(student1.lastName) // Kowalski
print(student1.points) // 80
```
4. Enkapsulacja i metody klasowe:
```swift
import Foundation

class Student {
    private var firstName: String
    private var lastName: String
    private var points: Int
    
    init(firstName: String, lastName: String, points: Int) {
        self.firstName = firstName
        self.lastName = lastName
        self.points = points
    }
    
    public func showStudent() {
        let satisfactionLevel = Foundation.round(pow(Double.random(in: 0...1), (110 - Double(points)) / 100) * 20)

        var auraColor: String

        switch satisfactionLevel {
        case 0...5:
            auraColor = "red"
        case 6...10:
            auraColor = "orange"
        case 11...15:
            auraColor = "purple"
        default:
            auraColor = "green"
        }
        
        print("\(firstName) \(lastName) has a \(auraColor) aura color.")
    }
}

let student = Student(firstName: "Mike", lastName: "Smith", points: 80)
student.showStudent()

```
5. Dziedziczenie:
```swift
import Foundation

class Person {
    private let name: String
    private let lastName: String
    
    init(name: String, lastName: String) {
        self.name = name
        self.lastName = lastName
    }
    
    func getName() -> String {
        return name
    }
    
    func getLastName() -> String {
        return lastName
    }
}

class Student: Person {
    private let points: Int
    
    init(name: String, lastName: String, points: Int) {
        self.points = points
        super.init(name: name, lastName: lastName)
    }
    
    func showStudentAura() {
        let satisfactionLevel = Foundation.round(pow(Double.random(in: 0...1), (110 - Double(points)) / 100) * 20)
        
        var auraColor: String
        
        switch satisfactionLevel {
        case 0...5:
            auraColor = "red"
        case 6...10:
            auraColor = "orange"
        case 11...15:
            auraColor = "purple"
        default:
            auraColor = "green"
        }
        
        print("Student: \(getName()) \(getLastName()), Satisfaction Level: \(satisfactionLevel), Aura Color: \(auraColor)")
    }
}

let student = Student(name: "John", lastName: "Doe", points: 80)
student.showStudentAura()
 
```
