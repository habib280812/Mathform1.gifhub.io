# welcome to my website by habib
import math

# 1. Nombor nisbah
def nombor_nisbah(a, b):
    return a / b
    
# 2. Faktor dan gandaan
def faktor(n):
    return [i for i in range(1, n+1) if n % i == 0]

def gandaan(n, jumlah=5):
    return [n * i for i in range(1, jumlah+1)]

# 3. Kuasa dan punca
def kuasa_dua(n):
    return n ** 2

def punca_kuasa_dua(n):
    return math.sqrt(n)

def kuasa_tiga(n):
    return n ** 3

def punca_kuasa_tiga(n):
    return n ** (1/3)

# 4. Nisbah, kadar dan kadaran
def nisbah(a, b):
    gcd = math.gcd(a, b)
    return f"{a//gcd}:{b//gcd}"

def kadar(jarak, masa):
    if masa == 0:
        return "Masa tak boleh sifar"
    return jarak / masa

def kadaran(a, b, x):
    # a : b = x : ?
    return (b * x) / a

# 5. Ungkapan algebra (Contoh: 2x + 3, bila x = 4)
def ungkapan_algebra(a, b, x):
    return a * x + b

# 6. Persamaan linear (ax + b = c)
def persamaan_linear(a, b, c):
    if a == 0:
        return "Tiada penyelesaian"
    return (c - b) / a

# 7. Ketaksamaan linear (ax + b < c)
def ketaksamaan_linear(a, b, c):
    x = (c - b) / a
    if a > 0:
        return f"x < {x}"
    else:
        return f"x > {x}"

# 8. Garis dan sudut
def sudut_tepat():
    return 90

def sudut_lurus():
    return 180

# 9. Poligon asas
def bil_sudut_poligon(sisi):
    return (sisi - 2) * 180

# 10. Perimeter dan luas
def perimeter_segiempat(panjang, lebar):
    return 2 * (panjang + lebar)

def luas_segiempat(panjang, lebar):
    return panjang * lebar

# 11. Set
def set_bersilang(set1, set2):
    return list(set(set1) & set(set2))

def set_gabungan(set1, set2):
    return list(set(set1) | set(set2))

# 12. Pengendalian data (min)
def min_data(data):
    return sum(data) / len(data)

def median_data(data):
    data = sorted(data)
    n = len(data)
    if n % 2 == 1:
        return data[n//2]
    else:
        return (data[n//2 - 1] + data[n//2]) / 2

def mod_data(data):
    return max(set(data), key=data.count)

# 13. Teorem Pythagoras
def pythagoras(a, b):
    return math.sqrt(a**2 + b**2)

# Contoh penggunaan
print("Kuasa Dua bagi 5:", kuasa_dua(5))
print("Punca Kuasa Tiga bagi 27:", punca_kuasa_tiga(27))
print("Nisbah 6 dan 9:", nisbah(6, 9))
print("Faktor 12:", faktor(12))
print("Sudut dalam segitiga:", bil_sudut_poligon(3))
print("Panjang hipotenus bila sisi 3 dan 4:", pythagoras(3, 4))
