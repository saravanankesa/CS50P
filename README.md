description: |
    API documentation for modules: project.

lang: en

classoption: oneside
geometry: margin=1in
papersize: a4

linkcolor: blue
links-as-notes: true
...



# Module `project` {#id}







## Functions



### Function `add_transaction` {#id}




>     def add_transaction() ‑> None


Adds a new transaction to the database. Prompts the user to select the transaction type, category,
and enter details such as name, amount, and date. Handles both expense and income transactions.


### Function `add_transaction_refactored` {#id}




>     def add_transaction_refactored(
>         conn: sqlite3.Connection,
>         transaction_type: str,
>         category: str,
>         name: str,
>         amount: float,
>         pre_auth_date: Optional[str]
>     ) ‑> None


A refactored version of add_transaction to directly insert a transaction into the database
with given parameters.

Parameters:
- conn: Database connection object.
- transaction_type: The type of transaction (Expense or Income).
- category: The category of the transaction.
- name: The name/description of the transaction.
- amount: The monetary value of the transaction.
- pre_auth_date: The date of a pre-authorized transaction, if applicable.


### Function `calculate_balance` {#id}




>     def calculate_balance() ‑> None


Provides the user with options to view their current balance, and summary for the last 7, 30,
or 90 days. The user selects an option to calculate and view the balance accordingly.


### Function `delete_transaction` {#id}




>     def delete_transaction() ‑> None


Prompts the user to delete an existing transaction from the database. The user is asked
to enter the ID of the transaction they wish to delete.


### Function `edit_transaction` {#id}




>     def edit_transaction()


Prompts the user to edit an existing transaction. The user is asked to enter the ID of the
transaction they wish to edit, and then provided with options to modify any of the transaction's
details.


### Function `edit_transaction_refactored` {#id}




>     def edit_transaction_refactored(
>         conn: sqlite3.Connection,
>         transaction_id: int,
>         new_values: dict
>     ) ‑> None


Refactored version of edit_transaction to update an existing transaction in the database
using the provided new values.

Parameters:
- conn: Database connection object.
- transaction_id: The ID of the transaction to be updated.
- new_values: A dictionary containing the transaction fields to be updated and their new values.


### Function `initialize_db` {#id}




>     def initialize_db() ‑> None


Initializes the database by creating a 'transactions' table if it doesn't already exist.
This table stores all transaction data including type, category, name, amount, date, and pre-auth date.


### Function `list_transactions` {#id}




>     def list_transactions()


Retrieves and displays all transactions from the database in an ascending order by their IDs.


### Function `main` {#id}




>     def main() ‑> None


Main function to run the finance tracker program. Displays a welcome message upon first run
and continuously prompts the user to choose from the main menu options until exit is selected.


### Function `upcoming_payments` {#id}




>     def upcoming_payments(
>         conn: sqlite3.Connection
>     ) ‑> None


Displays upcoming pre-authorized payments within the next 7 days.

Parameters:
- conn: Database connection object.



-----
Generated by *pdoc* 0.10.0 (<https://pdoc3.github.io>).
