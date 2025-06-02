# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM:
```
def encrypt_rail_fence(message, rails):
    rail = [['\n' for _ in range(len(message))] for _ in range(rails)]
    row, direction = 0, 1

    for col in range(len(message)):
        rail[row][col] = message[col]
        row += direction

        if row == 0 or row == rails - 1:
            direction *= -1
    encrypted = ''
    for r in rail:
        for ch in r:
            if ch != '\n':
                encrypted += ch

    return encrypted
message = input("Enter a Secret Message: ").replace(" ", "")
rails = int(input("Enter number of rails: "))
cipher_text = encrypt_rail_fence(message, rails)
print("Encrypted text:", cipher_text)

```

# OUTPUT:
![image](https://github.com/user-attachments/assets/d4e2b9ac-e519-48f8-beb1-2f69975c02b9)


# RESULT:
The program is executed successfully
