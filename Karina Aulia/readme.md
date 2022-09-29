import numpy as np #Library

#Mulai

#Mendeklarasikan variable fungsi untuk menghitung f(xn), f'(xn), xn, dan tol=toleransi galat menggunakan metode Newton Raphson
def nr(f, df, x0, tol):

    if abs(f(x0)) < tol: #jika f(x0) kurang dari toleransi galat
        return x0 #Kembalikan nilai x0   
    else: #jika f(x0) lebih dari toleransi galat 
        return nr(f, df, x0 - f(x0)/df(x0), tol) #Kembalikan nilai x0 melalui operasi rumus Newton-Raphson

#Menentukan fungsi f(x)= x^2 - 2x -8
f = lambda x: x**2 - 2*x - 8 

#Menentukan turunan fungsi f'(x)= 2x - 2
f_prime = lambda x: 2*x - 2 

#Rumus Newton Raphson dengan taksiran awal x0 = 5
newton_raphson = 5 - (f(5))/(f_prime(5))

#Cetak fungsi f(x0)
print("f(x0) = x^2 - 2x - 8")

#Cetak x0
print(f"x0 = {newton_raphson:.3f}")

#Memanggil fungsi nr() dan inisialisasi ke variable akar 
akar = nr(f, f_prime, 5, 1e-6)

#Cetak nilai estimasi akar dari f(x0) 
print(f"Akar fungsi = {akar:.3f}")

#Selesai 
