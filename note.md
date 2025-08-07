# File Explanations

This document provides an explanation for each file in the repository.

## HTML Files

-   **`index.html`**: This is the main entry point of the application. It displays a login form with fields for username and password. The form submits to `check_login.php`.

-   **`formtest.html`**: This file contains a registration form for new users. It includes fields for gender, name, province, favorite color, size, mobile number, password, and a self-introduction. The form submits to `test.php`. It also contains links to `show.php` and `formprovince.html`.

-   **`formprovince.html`**: This file provides a form to search for users by province. It contains a dropdown menu with a list of provinces and submits the selected province to `showbyprovince.php`.

-   **`testing.html`**: This is a simple HTML file with a form that includes radio buttons for a title (Mr., Mrs., Miss). The form has "Clear" and "Send" buttons but does not have a defined action, so it doesn't submit anywhere.

## PHP Files

-   **`check_login.php`**: This script handles the login form submission from `index.html`. It connects to the MySQL database, verifies the user's credentials against the `user` table, sets cookies for the user's session, and redirects to `show.php` upon successful login.

-   **`show.php`**: This script displays a table of all users from the `user` table if a valid login cookie is present. If the user is not logged in, it provides a link to the login page (`index.html`). It also includes a "Logout" link that directs to `logout.php`.

-   **`logout.php`**: This script handles the logout process. It clears the cookies that were set during login and then redirects the user back to `show.php`.

-   **`test.php`**: This script processes the registration form from `formtest.html`. It retrieves the submitted data, inserts a new user into the `user` table in the database, and then displays the submitted values. It uses the `mysqli` extension for database operations.

-   **`test_pdo.php`**: This script is an alternative to `test.php` for handling the registration form. The main difference is that it uses the PDO (PHP Data Objects) extension for database interaction, which is a more modern and secure way to connect to databases.

-   **`showbyprovince.php`**: This script displays a table of users filtered by the province selected in `formprovince.html`. It connects to the database and retrieves only the users who match the selected province.

-   **`search.php`**: This file contains a search form that allows users to search for other users by name. The same script processes the search query, retrieves matching users from the database using a `LIKE` clause, and displays the results in a table. Each result has a link to edit the user's information via `edit.php`.

-   **`edit.php`**: This script displays a form to edit an existing user's information. It retrieves the user's current data from the database based on the user ID passed in the URL and pre-fills the form with that data. The form submits to `update.php` (which is currently missing from the repository).

-   **`cookie.php`**: This is a simple script that displays the value of the 'city' cookie, which is set in `test.php`.

## SQL Files

-   **`shop.sql`** and **`shop (1).sql`**: These are SQL dump files that contain the structure of the `user` table and some sample data. They are used to set up the database for the application.

## Other

-   **`README.md`**: This file provides an overview of the project, setup instructions, and a brief description of each file.

-   **`.gitattributes`**: This is a Git configuration file that defines attributes for pathnames.

-   **`img/`**: This directory contains an image file (`images.png`) that is used in the `search.php` file as an icon for the edit link.
