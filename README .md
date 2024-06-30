
# Library Management System

The Library Management System (LMS) is a web-based application designed to manage and automate the operations of a library. With the growing need for digital transformation, libraries are moving towards electronic management of books and user data. This project aims to create a user-friendly system for library users and administrators to handle various tasks, such as logging in, viewing available books, and borrowing books.



<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Library Management System</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-image: url('https://img.freepik.com/free-photo/abundant-collection-antique-books-wooden-shelves-generated-by-ai_188544-29660.jpg');
      background-size: cover;
      position: relative;
    }

    body::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.4);
    }

    .container {
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
      position: relative;
    }

    .form {
      margin-bottom: 20px;
    }

    input[type='text'],
    input[type='password'] {
      width: calc(100% - 10px);
      padding: 5px;
      margin-bottom: 10px;
    }

    button {
      padding: 8px 15px;
      background-color: #153ed3;
      color: #fff;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background-color: #0056b3;
    }

    h1,
    h2 {
      color: #f8f1f1;
    }

    ul {
      list-style-type: none;
      padding: 0;
    }

    li {
      margin-bottom: 5px;
      color: #fff;
      cursor: pointer; /* Add cursor pointer to indicate selectable items */
    }

    li:hover {
      background-color: rgba(255, 255, 255, 0.2); /* Add hover effect */
    }

    .selected {
      background-color: rgba(255, 255, 255, 0.4);
    }
  </style>
</head>
<body>
  <!-- Container div to hold content -->
  <div class="container">
    <h1>LIBRARY MANAGEMENT SYSTEM</h1>

    <!-- Login form -->
    <div id="loginForm" class="form">
      <h2>Login/logon</h2>
      <input type="text" id="userId" placeholder="User ID" />
      <input type="password" id="password" placeholder="Password" />
      <button onclick="login()">Login</button>
    </div>

    <!-- Display area for books -->
    <div id="displayArea">
     <div AVAILABLE BOOKS="displayArea"></div>
      <ul id="bookList"></ul>
      <button id="borrowButton" style="display: none" onclick="borrowBook()">Borrow Book</button>
      <!-- Borrow button initially hidden -->
    </div>
  </div>

  <script>
    // Sample data for initial display
    let books = [
      { ISBN: '56768-001', title: 'OOPS' },
      { ISBN: '56768-002', title: 'Network Analysis' },
      { ISBN: '56768-003', title: 'PF' },
      { ISBN: '56768-004', title: 'Linear Algebra' },
      { ISBN: '56768-005', title: 'Electric Circuits' },
      { ISBN: '55599-006', title: 'Applied Physics' },
      { ISBN: '55599-007', title: 'OHS' },
      { ISBN: '55599-008', title: 'Circuit Analysis' },
      { ISBN: '55599-009', title: 'Geography' },
      { ISBN: '55599-010', title: 'ICT' },
      { ISBN: '55589-011', title: 'Chemistry' },
      { ISBN: '55589-012', title: 'Maths' },
      { ISBN: '55589-013', title: 'Islamiyat' },
      { ISBN: '55589-014', title: 'English' },
      { ISBN: '55589-015', title: 'Ethical Hacking' },
      { ISBN: '55589-016', title: 'Biology' },
    ];

    // Function to display books
    function displayBooks() {
      const bookList = document.getElementById('bookList');
      bookList.innerHTML = '';
      books.forEach(book => {
        const li = document.createElement('li');
        li.textContent = `${book.title} - ISBN: ${book.ISBN}`;
        // Add event listener to each book item to handle selection
        li.addEventListener('click', function () {
          // Highlight selected book
          const selectedBook = document.querySelector('.selected');
          if (selectedBook) {
            selectedBook.classList.remove('selected');
          }
          li.classList.add('selected');
          // Show borrow button
          document.getElementById('borrowButton').style.display = 'block';
        });
        bookList.appendChild(li);
      });
    }

    // Function to validate login
    function login() {
      const userId = document.getElementById('userId').value;
      const password = document.getElementById('password').value;

      // Check if the user ID and password are correct
      const validUserIds = ['56768', '55599', '55589'];
      const validPassword = '12345';

      if (validUserIds.includes(userId) && password === validPassword) {
        // Hide login form and display books
        document.getElementById('loginForm').style.display = 'none';
        displayBooks();
      } else {
        alert('Invalid user ID or password.');
      }
    }

    // Function to borrow selected book
    function borrowBook() {
      const selectedBook = document.querySelector('.selected');
      if (selectedBook) {
        const selectedISBN = selectedBook.textContent
          .split(' - ')[1]
          .split(': ')[1];
        // Implement your borrow logic here
        alert(`You have borrowed the book with ISBN: ${selectedISBN}. Please return it within 7 days.`);
      } else {
        alert('Please select a book to borrow.');
      }
    }
  </script>
</body>
</html>


## Authors

- [@saqibnawaz]

