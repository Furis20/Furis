<html>
<head>
</head>
<body>  
  
<h1>Let's have some fun!</h1>
<p>Enter your text here:</p><br>
<form action="/action_page.php">
<input type="text" name="FirstName" value=""><br>
<input type="submit" value="Enter">


<p>Choose your key:</p><br>
<form action="/action_page.php">
<input type="number" name="quantity" min="1" max="100"><br>
<input type="submit" value="OTP-encrypt"> <input type="submit" value="OTP-decrypt"> <input type="submit" value="SHA-2"> <input type="submit" value="MD5 decrypt">

<p>Result:</p>
<form action="/action_page.php">
<input type="text" name="FirstName" value=""><br>
def encrypt(n, plaintext):
    """Encrypt the string and return the ciphertext"""
    result = ''

    for l in plaintext.lower():
        try:
            i = (key.index(l) + n) % 26
            result += key[i]
        except ValueError:
            result += l

    return result.lower()

def decrypt(n, ciphertext):
    """Decrypt the string and return the plaintext"""
    result = ''

    for l in ciphertext:
        try:
            i = (key.index(l) - n) % 26
            result += key[i]
        except ValueError:
            result += l

    return result

text = "I am coding Python on SoloLearn!"
offset = 5

encrypted = encrypt(offset, text)
print('Encrypted:', encrypted)

decrypted = decrypt(offset, encrypted)
print('Decrypted:', decrypted)

