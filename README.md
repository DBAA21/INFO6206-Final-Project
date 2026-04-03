# Electronics E-Commerce Store

**INFO 6205 - Data Structures and Algorithms Project**

A fully functional e-commerce application built with JavaFX that demonstrates implementation and usage of custom data structures and algorithms.

## 📋 Project Overview

This application is an electronics store that allows users to:
- Browse products by category
- Search and filter products
- Sort products by various criteria
- View detailed product information
- Add/remove items from shopping cart
- Navigate browsing history with back/forward buttons
- View recommended products

## 🎯 Requirements Met

### Foundational Topics (2/1 Required)
1. **Stacks** - Browsing history with back/forward navigation
2. **Recursion** - Category tree traversal and operations
3. **Algorithm Efficiency** - Performance analysis and Big-O documentation

### Advanced Topics (5/3 Required)
1. **Binary Search Tree** - Product catalog storage (O(log n) operations)
2. **Hash Table** - Fast product lookup and cart management (O(1) lookups)
3. **Priority Queue** - Product recommendations ranking (O(log n) operations)
4. **Sorting Algorithms** - QuickSort and MergeSort for product sorting
5. **Linked Lists** - Shopping cart implementation

## 🏗️ Architecture

### Custom Data Structures (All Custom Implementations)
```
datastructures/
├── BinarySearchTree.java   - Product catalog indexed by ID
├── HashTable.java          - Fast lookups with chaining
├── Stack.java              - Browsing history (LIFO)
├── PriorityQueue.java      - Heap-based recommendations
├── LinkedList.java         - Shopping cart items
└── CategoryTree.java       - Recursive tree operations
```

### Domain Models
```
models/
├── Product.java    - Product entity with specifications
├── Category.java   - Hierarchical category structure
└── CartItem.java   - Shopping cart item with quantity
```

### Business Services
```
services/
├── ProductService.java          - Product management (BST + HashTable)
├── CartService.java             - Cart operations (LinkedList + HashTable)
├── SearchService.java           - Search & sort algorithms
├── RecommendationService.java   - Priority queue recommendations
└── BrowsingHistoryService.java  - Stack-based navigation
```

### User Interface
```
ui/
├── MainWindow.java         - Main application window
├── ProductGridView.java    - Product grid display
├── ProductDetailView.java  - Product details modal
└── CartView.java           - Shopping cart panel
```

## 🚀 How to Run

### Prerequisites
- Java 11 or higher
- Maven 3.6 or higher

### Option 1: Using Maven (Recommended)
```bash
# Clean and compile
mvn clean compile

# Run the application
mvn javafx:run
```

### Option 2: Using Maven Exec Plugin
```bash
mvn exec:java -Dexec.mainClass="com.ecommerce.Main"
```

### Option 3: Manual Compilation (if JavaFX is installed)
```bash
# Compile
javac -d out --module-path $PATH_TO_JAVAFX_LIB --add-modules javafx.controls \
    src/main/java/com/ecommerce/**/*.java

# Run
java --module-path $PATH_TO_JAVAFX_LIB --add-modules javafx.controls \
    -cp out com.ecommerce.Main
```

## 📊 Algorithm Complexity Analysis

### Data Structure Operations

| Data Structure | Operation | Time Complexity | Use Case |
|---------------|-----------|----------------|----------|
| Binary Search Tree | Insert, Search, Delete | O(log n) avg | Product catalog |
| Hash Table | Get, Put, Remove | O(1) avg | Fast product lookup |
| Stack | Push, Pop, Peek | O(1) | Browsing history |
| Priority Queue | Enqueue, Dequeue | O(log n) | Recommendations |
| Linked List | Add, Remove | O(1) at ends | Shopping cart |
| Recursion | Tree Traversal | O(n) | Category navigation |

### Sorting Algorithms

| Algorithm | Time Complexity | Space | Used For |
|-----------|----------------|-------|----------|
| QuickSort | O(n log n) avg, O(n²) worst | O(log n) | Price, Rating |
| MergeSort | O(n log n) guaranteed | O(n) | Name sorting |
| Binary Search | O(log n) | O(1) | Sorted lookups |

## ✨ Key Features Demonstration

### 1. Binary Search Tree (BST)
- All products stored in BST indexed by product ID
- Supports efficient insertion, deletion, and in-order traversal
- Provides sorted product list

### 2. Hash Table
- O(1) average-case product lookup by ID
- Shopping cart uses hash table for quick product access
- Implements chaining for collision resolution
- Auto-resizing when load factor exceeds 0.75

### 3. Stack (Browsing History)
- Back button: Pop from back stack
- Forward button: Pop from forward stack
- Visit new product: Clear forward stack, push current to back stack
- Demonstrates LIFO principle

### 4. Priority Queue (Recommendations)
- Binary heap implementation
- Ranks products by rating for featured products
- Recommends similar products from same category
- O(log n) enqueue/dequeue operations

### 5. Linked List (Shopping Cart)
- Doubly-linked list for efficient insertion/deletion
- O(1) add/remove at ends
- Maintains cart items in order

### 6. Recursion (Category Tree)
- Recursive category traversal
- Find category by name recursively
- Get all products from category and subcategories
- Calculate tree depth and node count

### 7. Sorting Algorithms
- **QuickSort**: Price and rating sorting (fast average case)
- **MergeSort**: Name sorting (guaranteed O(n log n))
- **Binary Search**: Find product by ID in sorted list

## 🧪 Testing the Features

### Test Data Structure Usage:
1. **BST**: Browse all products - they're stored in BST
2. **HashTable**: Click any product - uses O(1) lookup
3. **Stack**: Click products and use Back/Forward buttons
4. **Priority Queue**: View product details to see recommendations
5. **LinkedList**: Add/remove items from cart
6. **Recursion**: Select different categories to see recursive traversal

### Test Sorting:
1. Change "Sort by" dropdown to different options
2. Notice different sorting algorithms in action
3. Check console for algorithm performance info

### Test Search:
1. Use search bar for text search (linear search)
2. Filter by category (recursive tree search)
3. Sort results to enable binary search

## 📁 Project Structure
```
FinalProject/
├── src/
│   └── main/
│       └── java/
│           └── com/ecommerce/
│               ├── Main.java
│               ├── datastructures/  (6 custom implementations)
│               ├── models/          (3 domain classes)
│               ├── services/        (5 service classes)
│               └── ui/              (4 UI components)
├── pom.xml
└── README.md
```

## 🎓 Learning Outcomes

This project demonstrates:
1. Implementation of core data structures from scratch
2. Understanding of algorithm time/space complexity
3. Practical application of data structures in real-world scenarios
4. Comparison of different sorting algorithms
5. Use of recursion for tree operations
6. Design patterns (Builder, Service Layer, MVC)
7. JavaFX GUI development

## 📝 Code Quality

- All data structures implemented from scratch (no Java Collections used for core functionality)
- Comprehensive documentation with Big-O complexity annotations
- Clean separation of concerns (Models, Services, UI)
- Proper encapsulation and OOP principles
- Builder pattern for complex object creation
- Error handling and validation

## 🔍 Performance Analysis

The application includes performance metrics:
- BST provides O(log n) product lookups vs O(n) linear search
- Hash table provides O(1) cart operations
- Priority queue efficiently maintains top-k recommendations
- Sorting comparison: QuickSort vs MergeSort characteristics
- Stack provides constant-time navigation

## 👨‍💻 Author

**INFO 6205 Student**
Northeastern University
Data Structures and Algorithms Course Project

## 📄 License

This project is created for educational purposes as part of the INFO 6205 course.

---

**Note**: This application uses custom implementations of all data structures to demonstrate understanding of fundamental computer science concepts. The JavaFX GUI provides an interactive way to visualize and test these implementations.
# INFO6206-Final-Project
