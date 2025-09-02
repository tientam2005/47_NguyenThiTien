def caesar_encrypt(plaintext, k):
    result = ""
    k = k % 26  # nếu k > 26 thì lấy dư
    for char in plaintext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift + k) % 26 + shift)
        else:
            result += char
    return result

def caesar_decrypt(ciphertext, k):
    return caesar_encrypt(ciphertext, -k)

if __name__ == "__main__":
    k = 47   # STT
    plaintext = "NguyenThiTien"  # Ten

    ciphertext = caesar_encrypt(plaintext, k)
    decrypted = caesar_decrypt(ciphertext, k)

    print("Plaintext :", plaintext)
    print("Key (k)   :", k, "→ dùng k mod 26 =", k % 26)
    print("Ciphertext:", ciphertext)
    print("Decrypt   :", decrypted)
