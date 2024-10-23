# Caesar Cipher Implementation in Python

This Python code implements a **Caesar cipher**, a type of substitution cipher where each letter in the plaintext is shifted by a certain number of positions in the alphabet. Here's a breakdown of the code:

## Functions:

### `encrypt(text, s)`

- Takes in two arguments:
  - `text`: the string to be encrypted.
  - `s`: the shift value, which is the number of positions each letter in the text is shifted.
- The function processes each character in `text`:
    - If it's an **uppercase** letter (`A-Z`), it shifts the character by `s` positions forward in the alphabet.
    - If it's a **lowercase** letter (`a-z`), it similarly shifts the character forward by `s` positions.
    - If the character is **not a letter** (like punctuation or space), it is left unchanged.
- The encrypted characters are concatenated and returned as `result`.

### `decrypt(text, s)`

- Works similarly to the `encrypt` function but shifts characters **backwards** by `s` positions in the alphabet.
- This reverses the encryption process, recovering the original text.

## Encryption and Decryption Logic:

- **For Uppercase Letters**:
  - The ASCII value of an uppercase letter can be found using `ord(char)`. The shift operation is done using:
    ```python
    chr((ord(char) + s - 65) % 26 + 65)
    ```
    - `ord(char)` converts the character to its ASCII value.
    - Subtracting `65` normalizes it to a 0-based index for letters `A-Z`.
    - The shift `s` is added.
    - The modulus operation `% 26` ensures that if the shift goes past `Z`, it wraps back to the start of the alphabet.
    - Finally, adding `65` converts it back to an uppercase letter.
  
- **For Lowercase Letters**:
  - The process is similar for lowercase letters but with the base value `97` (ASCII value of `a`).

## Main Code Execution:

1. The user is prompted to input:
    - `text`: the message to be encrypted.
    - `s`: the shift value (an integer).
  
2. The `encrypt` function is called with the user-provided `text` and `s`, and the result is stored in `encrypted_text`.

3. The `decrypt` function is called with the `encrypted_text` and `s`, and the result is stored in `decrypted_text`.

4. Finally, the original text, the shift value, the encrypted text, and the decrypted text are printed.

### Example:

For an input text "Hello" and shift `s = 3`:
- **Encrypted Text**: "Khoor"
- **Decrypted Text**: "Hello" (the original text is restored).

## Python Code:

```python
def encrypt(text, s):
    result = ""
    for i in range(len(text)):
        char = text[i]
        if char.isupper():
            result += chr((ord(char) + s - 65) % 26 + 65)
        elif char.islower():
            result += chr((ord(char) + s - 97) % 26 + 97)
        else:
            result += char
    return result

def decrypt(text, s):
    result = ""
    for i in range(len(text)):
        char = text[i]
        if char.isupper():
            result += chr((ord(char) - s - 65) % 26 + 65)
        elif char.islower():
            result += chr((ord(char) - s - 97) % 26 + 97)
        else:
            result += char
    return result

text = input("Enter the text: ")
s = int(input("Enter the shift value: "))
encrypted_text = encrypt(text, s)
decrypted_text = decrypt(encrypted_text, s)
print("Original Text : " + text)
print("Shift         : " + str(s))
print("Encrypted Text: " + encrypted_text)
print("Decrypted Text: " + decrypted_text)
