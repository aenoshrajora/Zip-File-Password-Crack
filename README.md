# Zip-File-Password-Crack
# Warning - It will take much time to crack a bigger password including (Lowercase, Uppercase, Symbol, Special Character)

import zipfile

charlist = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~"
complete = []

for current in range(900):
    a = [i for i in charlist]
    for x in range(current):
        a = [y + i for i in charlist for y in a]
    complete = complete + a

z = zipfile.ZipFile('zip.zip')

tries = 0

for password in complete:
    try:
        tries + 1
        z.setpassword(password.encode('ascii'))
        z.extract('zip.txt')
        print(f"Password was found after {tries} tries! It was {passowrd}")
    except:
        pass
