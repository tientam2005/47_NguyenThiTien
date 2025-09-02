def caesar_encrypt(plaintext, k):
    ket_qua = ""   # kết quả
    k = k % 26     # nếu k > 26 thì lấy dư
    for char in plaintext:   # duyệt từng ký tự
        if char.isalpha():   # nếu là chữ cái
            shift = 65 if char.isupper() else 97
            ket_qua += chr((ord(char) - shift + k) % 26 + shift)
        else:
            ket_qua += char
    return ket_qua

def caesar_decrypt(ciphertext, k):
    return caesar_encrypt(ciphertext, -k)

if __name__ == "__main__":   
    k = 47   # STT
    plaintext = "NguyenThiTien"  # tên 

    ciphertext = caesar_encrypt(plaintext, k)
    decrypted = caesar_decrypt(ciphertext, k)

    print("Bản rõ     :", plaintext)
    print("Khóa (k)   :", k, "→ dùng k mod 26 =", k % 26)
    print("Bản mã     :", ciphertext)
    print("Giải mã    :", decrypted)
