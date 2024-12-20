# Transposition Cipher Implementation in Python
This code implements two types of **transposition ciphers**: **Columnar Transposition** and **Row Transposition**. Both of these are classic encryption methods where the order of characters in the plaintext is changed according to a specific rule, without altering the actual characters themselves.

### Key Components:

1. **Plaintext and Key**:
   - **Plaintext**: The input message to be encrypted (spaces removed).
   - **Key**: This represents either the number of columns (in columnar transposition) or the number of characters in each row (in row transposition).

2. **Choice of Transposition**:
   - The user can choose between two encryption methods:
     - **Columnar Transposition**: Characters are arranged in columns.
     - **Row Transposition**: Characters are arranged in rows.

### Functions:

#### 1. **`encrypt_transposition_by_column(plaintext, key)`**:
   - **Goal**: This function encrypts the plaintext using columnar transposition.
   - **Process**:
     1. It creates a list of empty strings, each corresponding to a column.
     2. Characters from the plaintext are placed in these columns in a cyclic manner based on the key. For example, if the key is 4, characters are placed in the 1st, 2nd, 3rd, 4th columns, then the 1st again, and so on.
     3. It displays the current column layout (how the plaintext was split into columns).
     4. The user is asked to specify the order in which the columns should be rearranged for encryption (e.g., columns could be read in the order 3, 1, 4, 2).
     5. The ciphertext is generated by concatenating the columns in the specified order.

#### 2. **`encrypt_transposition_by_row(plaintext, key)`**:
   - **Goal**: This function encrypts the plaintext using row transposition.
   - **Process**:
     1. It splits the plaintext into rows, with each row containing a number of characters equal to the key.
     2. It displays the current row layout.
     3. The user is asked to specify the order in which the rows should be rearranged (e.g., rows could be read in the order 2, 3, 1).
     4. The ciphertext is generated by concatenating the rows in the specified order.

### Workflow:

1. **User Input**:
   - The user provides the plaintext and the key (number of columns or row width).
   - The user chooses between Columnar Transposition and Row Transposition.

2. **Encryption**:
   - For columnar transposition:
     - The plaintext is split into columns based on the key, and the user specifies the order of columns for encryption.
   - For row transposition:
     - The plaintext is split into rows based on the key, and the user specifies the order of rows for encryption.
   
3. **Output**:
   - The ciphertext is printed after the user-defined transposition of rows or columns.

### Example:

Let's take an example with the input:
- **Plaintext**: "HELLOTHERE"
- **Key**: 4 (number of columns or row width)

#### Columnar Transposition Example:
1. **Initial Column Layout** (before sorting):
   ```
   Column 1: H O R
   Column 2: E T E
   Column 3: L H
   Column 4: L E
   ```

2. **User provides the column order**: Let's say the user specifies the order `3 1 4 2`.

3. **Ciphertext**: The columns are read in the specified order: `"LHLEROTE"`. This is the encrypted message.

#### Row Transposition Example:
1. **Initial Row Layout** (before sorting):
   ```
   Row 1: HELL
   Row 2: OTHE
   Row 3: RE
   ```

2. **User provides the row order**: Let's say the user specifies the order `2 3 1`.

3. **Ciphertext**: The rows are read in the specified order: `"OTHEREHELL"`. This is the encrypted message.


## Python Code
``` python
def encrypt_transposition_by_column(plaintext, key):
    columns = [''] * key
    for index, char in enumerate(plaintext):
        columns[index % key] += char

    print("\nCurrent column layout before sorting:")
    for i, col in enumerate(columns):
        print(f"Column {i + 1}: {col}")

    print("\nEnter the order of columns for encryption (space-separated indices, starting from 1):")
    rotation_order = list(map(int, input().split()))

    ciphertext = ''.join(columns[i - 1] for i in rotation_order)
    return ciphertext

def encrypt_transposition_by_row(plaintext, key):
    rows = [plaintext[i:i + key] for i in range(0, len(plaintext), key)]

    print("\nCurrent row layout before sorting:")
    for i, row in enumerate(rows):
        print(f"Row {i + 1}: {row}")

    print("\nEnter the order of rows for encryption (space-separated indices, starting from 1):")
    rotation_order = list(map(int, input().split()))

    ciphertext = ''.join(rows[i - 1] for i in rotation_order)
    return ciphertext

plaintext = input("Enter the plaintext (no spaces): ").replace(" ", "")
key = int(input("Enter the number of columns (key length): "))
while True:
    print("\nChoose encryption method:")
    print("1. Columnar Transposition")
    print("2. Row Transposition")
    choice = input("Enter your choice (1 or 2): ")

    if choice == '1':
        ciphertext = encrypt_transposition_by_column(plaintext, key)
    elif choice == '2':
        ciphertext = encrypt_transposition_by_row(plaintext, key)
    else:
        print("Invalid choice! Please choose 1 or 2.")
        continue

    print("\nCiphertext:", ciphertext)

    continue_choice = input("\nDo you want to encrypt another message? (yes/no): ").lower()
    if continue_choice != 'yes':
        print("Exiting...")
        break
