# O'Reilly Books Discount App

This Vue.js-based application displays a list of books from the publisher "O'Reilly Media" and applies a 20% discount on all books. The app dynamically generates a table to display the book data and shows both the original and discounted prices. 

## Features

- Display a table of books from the publisher "O'Reilly Media".
- Dynamically render table headers and rows based on the book data.
- Calculate and display a 20% discount on the original price.
- Highlight the original price with a strikethrough and show the discounted price below it.

## Project Structure

- **HTML**: The main layout and table structure.
- **JavaScript**: Vue.js is used to manage the app's state, methods, and dynamic rendering.
- **CSS**: Basic styles for the table and text formatting.

---

## How the App Works

### 1. Displaying Data Dynamically

The app uses Vue's `v-for` directive to iterate over both the headers and rows dynamically based on the data. This way, no manual work is needed to hardcode the column names or the book data.

- **Table Headers**: The column names are defined in a computed property `objectKeys`, which returns an array of strings: `"title"`, `"isbn"`, `"author"`, `"publisher"`, `"price"`, and `"numPages"`.
- **Table Rows**: The book data is filtered using a computed property `filterPublisherOReilly`, which filters the list of books to only include those from "O'Reilly Media".

The following Vue.js features are utilized:

- **`v-for`**: Used to loop through `objectKeys` to generate table headers and to loop through the filtered list of books to generate table rows.
- **`v-if`**: Used to conditionally render certain elements within the table, like displaying the discounted price if the column is for the price.

### 2. Discount Calculation

The app includes a method `calculateDiscountedPrice`, which takes the original price as input and applies a 20% discount. This method is called in the template wherever the price column is rendered.

### 3. Vue.js Key Concepts

Here are the key Vue.js concepts used in this app:

#### Data Binding (`data`)
The `data()` function returns the initial state of the app, which includes an array of book objects. Each book has properties like `title`, `isbn`, `author`, `publisher`, `price`, and `numPages`.

#### Computed Properties (computed)
objectKeys: This computed property returns the list of keys that will be used as column headers and to access corresponding book data.

#### Methods (methods)
calculateDiscountedPrice: This method calculates a 20% discounted price based on the original price and formats it for display.

#### Directives (v-for, v-if)
v-for: Used to iterate through arrays to generate table rows and columns.
v-if: Conditionally renders elements in the DOM, such as showing both the original and discounted prices.