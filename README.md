def bubble_sort(arr, verbose=False):
    """
    Mengimplementasikan algoritma Bubble Sort untuk mengurutkan array angka.

    Args:
        arr (list): Daftar angka yang akan diurutkan.
        verbose (bool): Jika True, akan mencetak setiap langkah swap.

    Returns:
        list: Daftar angka yang sudah diurutkan.
    """
    n = len(arr)
    # Loop untuk setiap elemen di array
    for i in range(n - 1):
        swapped = False # Flag untuk mendeteksi apakah ada swap di iterasi ini
        # Loop untuk membandingkan elemen yang berdekatan
        # n-1-i karena elemen terakhir 'i' sudah pada posisi yang benar
        for j in range(n - 1 - i):
            if arr[j] > arr[j+1]:
                # Tukar elemen jika yang saat ini lebih besar dari yang berikutnya
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
                if verbose:
                    print(f"Swap: {arr[j+1]} <-> {arr[j]} | Array saat ini: {arr}")
        
        # Jika tidak ada swap di iterasi luar ini, array sudah terurut
        if not swapped:
            break
    
    return arr

# --- Contoh Penggunaan ---

# Array angka untuk diurutkan
my_array = [64, 34, 25, 12, 22, 11, 90]

print("--- Bubble Sort ---")
print(f"Array asli: {my_array}")

print("\n--- Langkah-langkah Bubble Sort (dengan verbose) ---")
sorted_array_verbose = bubble_sort(my_array.copy(), verbose=True) # Menggunakan .copy() agar array asli tidak berubah
print(f"\nArray setelah diurutkan (verbose): {sorted_array_verbose}")

print("\n--- Bubble Sort (tanpa verbose) ---")
my_array_2 = [5, 1, 4, 2, 8]
print(f"Array asli: {my_array_2}")
sorted_array_simple = bubble_sort(my_array_2)
print(f"Array setelah diurutkan (simple): {sorted_array_simple}")

print("\n--- Contoh lain ---")
my_array_3 = [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
print(f"Array asli: {my_array_3}")
sorted_array_another = bubble_sort(my_array_3, verbose=True)
print(f"\nArray setelah diurutkan: {sorted_array_another}")
output
--- Langkah-langkah Bubble Sort (dengan verbose) ---
Swap: 64 <-> 34 | Array saat ini: [34, 64, 25, 12, 22, 11, 90]
Swap: 64 <-> 25 | Array saat ini: [34, 25, 64, 12, 22, 11, 90]
Swap: 64 <-> 12 | Array saat ini: [34, 25, 12, 64, 22, 11, 90]
Swap: 64 <-> 22 | Array saat ini: [34, 25, 12, 22, 64, 11, 90]
Swap: 64 <-> 11 | Array saat ini: [34, 25, 12, 22, 11, 64, 90]
Swap: 34 <-> 25 | Array saat ini: [25, 34, 12, 22, 11, 64, 90]
Swap: 34 <-> 12 | Array saat ini: [25, 12, 34, 22, 11, 64, 90]
Swap: 34 <-> 22 | Array saat ini: [25, 12, 22, 34, 11, 64, 90]
Swap: 34 <-> 11 | Array saat ini: [25, 12, 22, 11, 34, 64, 90]
Swap: 25 <-> 12 | Array saat ini: [12, 25, 22, 11, 34, 64, 90]
Swap: 25 <-> 22 | Array saat ini: [12, 22, 25, 11, 34, 64, 90]
Swap: 25 <-> 11 | Array saat ini: [12, 22, 11, 25, 34, 64, 90]
Swap: 22 <-> 11 | Array saat ini: [12, 11, 22, 25, 34, 64, 90]
Swap: 12 <-> 11 | Array saat ini: [11, 12, 22, 25, 34, 64, 90]

Array setelah diurutkan (verbose): [11, 12, 22, 25, 34, 64, 90]

--- Bubble Sort (tanpa verbose) ---
Array asli: [5, 1, 4, 2, 8]
Array setelah diurutkan (simple): [1, 2, 4, 5, 8]

--- Contoh lain ---
Array asli: [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
Swap: 10 <-> 9 | Array saat ini: [9, 10, 8, 7, 6, 5, 4, 3, 2, 1]
Swap: 10 <-> 8 | Array saat ini: [9, 8, 10, 7, 6, 5, 4, 3, 2, 1]
Swap: 10 <-> 7 | Array saat ini: [9, 8, 7, 10, 6, 5, 4, 3, 2, 1]
Swap: 10 <-> 6 | Array saat ini: [9, 8, 7, 6, 10, 5, 4, 3, 2, 1]
Swap: 10 <-> 5 | Array saat ini: [9, 8, 7, 6, 5, 10, 4, 3, 2, 1]
Swap: 10 <-> 4 | Array saat ini: [9, 8, 7, 6, 5, 4, 10, 3, 2, 1]
Swap: 10 <-> 3 | Array saat ini: [9, 8, 7, 6, 5, 4, 3, 10, 2, 1]
Swap: 10 <-> 2 | Array saat ini: [9, 8, 7, 6, 5, 4, 3, 2, 10, 1]
Swap: 10 <-> 1 | Array saat ini: [9, 8, 7, 6, 5, 4, 3, 2, 1, 10]
Swap: 9 <-> 8 | Array saat ini: [8, 9, 7, 6, 5, 4, 3, 2, 1, 10]
Swap: 9 <-> 7 | Array saat ini: [8, 7, 9, 6, 5, 4, 3, 2, 1, 10]
Swap: 9 <-> 6 | Array saat ini: [8, 7, 6, 9, 5, 4, 3, 2, 1, 10]
Swap: 9 <-> 5 | Array saat ini: [8, 7, 6, 5, 9, 4, 3, 2, 1, 10]
Swap: 9 <-> 4 | Array saat ini: [8, 7, 6, 5, 4, 9, 3, 2, 1, 10]
Swap: 9 <-> 3 | Array saat ini: [8, 7, 6, 5, 4, 3, 9, 2, 1, 10]
Swap: 9 <-> 2 | Array saat ini: [8, 7, 6, 5, 4, 3, 2, 9, 1, 10]
Swap: 9 <-> 1 | Array saat ini: [8, 7, 6, 5, 4, 3, 2, 1, 9, 10]
Swap: 8 <-> 7 | Array saat ini: [7, 8, 6, 5, 4, 3, 2, 1, 9, 10]
Swap: 8 <-> 6 | Array saat ini: [7, 6, 8, 5, 4, 3, 2, 1, 9, 10]
Swap: 8 <-> 5 | Array saat ini: [7, 6, 5, 8, 4, 3, 2, 1, 9, 10]
Swap: 8 <-> 4 | Array saat ini: [7, 6, 5, 4, 8, 3, 2, 1, 9, 10]
Swap: 8 <-> 3 | Array saat ini: [7, 6, 5, 4, 3, 8, 2, 1, 9, 10]
Swap: 8 <-> 2 | Array saat ini: [7, 6, 5, 4, 3, 2, 8, 1, 9, 10]
Swap: 8 <-> 1 | Array saat ini: [7, 6, 5, 4, 3, 2, 1, 8, 9, 10]
Swap: 7 <-> 6 | Array saat ini: [6, 7, 5, 4, 3, 2, 1, 8, 9, 10]
Swap: 7 <-> 5 | Array saat ini: [6, 5, 7, 4, 3, 2, 1, 8, 9, 10]
Swap: 7 <-> 4 | Array saat ini: [6, 5, 4, 7, 3, 2, 1, 8, 9, 10]
Swap: 7 <-> 3 | Array saat ini: [6, 5, 4, 3, 7, 2, 1, 8, 9, 10]
Swap: 7 <-> 2 | Array saat ini: [6, 5, 4, 3, 2, 7, 1, 8, 9, 10]
Swap: 7 <-> 1 | Array saat ini: [6, 5, 4, 3, 2, 1, 7, 8, 9, 10]
Swap: 6 <-> 5 | Array saat ini: [5, 6, 4, 3, 2, 1, 7, 8, 9, 10]
Swap: 6 <-> 4 | Array saat ini: [5, 4, 6, 3, 2, 1, 7, 8, 9, 10]
Swap: 6 <-> 3 | Array saat ini: [5, 4, 3, 6, 2, 1, 7, 8, 9, 10]
Swap: 6 <-> 2 | Array saat ini: [5, 4, 3, 2, 6, 1, 7, 8, 9, 10]
Swap: 6 <-> 1 | Array saat ini: [5, 4, 3, 2, 1, 6, 7, 8, 9, 10]
Swap: 5 <-> 4 | Array saat ini: [4, 5, 3, 2, 1, 6, 7, 8, 9, 10]
Swap: 5 <-> 3 | Array saat ini: [4, 3, 5, 2, 1, 6, 7, 8, 9, 10]
Swap: 5 <-> 2 | Array saat ini: [4, 3, 2, 5, 1, 6, 7, 8, 9, 10]
Swap: 5 <-> 1 | Array saat ini: [4, 3, 2, 1, 5, 6, 7, 8, 9, 10]
Swap: 4 <-> 3 | Array saat ini: [3, 4, 2, 1, 5, 6, 7, 8, 9, 10]
Swap: 4 <-> 2 | Array saat ini: [3, 2, 4, 1, 5, 6, 7, 8, 9, 10]
Swap: 4 <-> 1 | Array saat ini: [3, 2, 1, 4, 5, 6, 7, 8, 9, 10]
Swap: 3 <-> 2 | Array saat ini: [2, 3, 1, 4, 5, 6, 7, 8, 9, 10]
Swap: 3 <-> 1 | Array saat ini: [2, 1, 3, 4, 5, 6, 7, 8, 9, 10]
Swap: 2 <-> 1 | Array saat ini: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

Array setelah diurutkan: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
