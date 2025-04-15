# structs-practice

Here are a few exercises to practice using structs in Go, progressing from basic to more advanced concepts. Each includes a problem description and hints to guide you. Try implementing them, and feel free to ask if you need help with solutions or explanations!

### Exercise 1: Basic Struct Creation and Initialization
**Task**: Create a struct to represent a `Book` with fields for title, author, and publication year. Write a program that initializes a few books and prints their details.

- **Hints**:
  - Define a `Book` struct with appropriate field types (e.g., `string` for title and author, `int` for year).
  - Create instances using struct literals and field-by-field initialization.
  - Use `fmt.Println` or `fmt.Printf` to display the books.
  - Example output: "Title: The Go Programming Language, Author: Kernighan, Year: 2015"

### Exercise 2: Struct Methods
**Task**: Extend the `Book` struct from Exercise 1 by adding a method `Summary()` that returns a string summarizing the book (e.g., "The Go Programming Language by Kernighan, published in 2015"). Create a slice of books and print their summaries.

- **Hints**:
  - Define a method with the signature `func (b Book) Summary() string`.
  - Use `strings.Join` or `fmt.Sprintf` to format the summary.
  - Create a slice (`[]Book`) and iterate over it to call `Summary()` on each book.
  - Try passing the struct by value vs. pointer to understand the difference.

### Exercise 3: Embedded Structs
**Task**: Create a `Library` struct that contains a name and a slice of `Book` structs. Embed a `ContactInfo` struct with fields for email and phone number within `Library`. Write a program to initialize a library with a few books and print all details, including contact info.

- **Hints**:
  - Define `ContactInfo` with `email` and `phone` fields.
  - Embed `ContactInfo` in `Library` using an anonymous field (e.g., `ContactInfo` without a field name).
  - Initialize a `Library` instance, including books and contact info.
  - Access embedded fields directly (e.g., `library.Email`) and print all data.
  - Bonus: Add a method to `Library` to count the number of books.

### Exercise 4: Structs with Pointers and Mutability
**Task**: Create a `Student` struct with fields for name and a slice of grades (integers). Add two methods: `AddGrade(grade int)` to append a grade and `AverageGrade() float64` to compute the average. Write a program that modifies a student’s grades and prints the updated average.

- **Hints**:
  - Use a pointer receiver for `AddGrade` (e.g., `func (s *Student) AddGrade(grade int)`) to modify the struct.
  - Use a value receiver for `AverageGrade` since it doesn’t modify the struct.
  - Handle the case where the grades slice is empty to avoid division by zero.
  - Test by adding multiple grades and checking the average.

### Exercise 5: Struct Composition and JSON Serialization
**Task**: Create a `Course` struct with a title and an embedded `Instructor` struct (with name and ID fields). Write a program that creates a slice of courses, serializes it to JSON, and then deserializes it back into a new slice. Print the results to verify.

- **Hints**:
  - Use the `encoding/json` package for serialization (`json.Marshal`) and deserialization (`json.Unmarshal`).
  - Add JSON tags to struct fields (e.g., `json:"title"`) to control JSON key names.
  - Create a few `Course` instances with different instructors.
  - Verify the deserialized data matches the original by printing both.
  - Bonus: Handle potential errors during JSON processing using error checks.

### Tips for Practice
- **Test Your Code**: Write `main()` functions to test each exercise. Use `go run` to execute and verify output.
- **Experiment**: Try variations, like adding validation (e.g., ensure publication year is positive) or using pointers vs. values.
- **Debug**: Use `fmt.Printf("%+v\n", structInstance)` to inspect struct fields during development.
- **Read Docs**: Refer to the Go tour (tour.golang.org) or the official docs (pkg.go.dev) for struct and method syntax.

If you want sample solutions for any of these or more exercises (e.g., involving interfaces or concurrency with structs), let me know!