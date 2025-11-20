# **Implementasi Linked List di Python**

Dokumentasi ini menjelaskan implementasi dasar struktur data Linked List menggunakan bahasa Python.
Linked List tersusun dari node-node yang saling terhubung, di mana setiap node menyimpan data dan alamat node berikutnya.

##  **1. Class Node**

Class Node digunakan untuk membuat elemen tunggal dalam Linked List.
###  **Membuat Stack**

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```
Setiap node menyimpan dua bagian utama:

data ➝ nilai yang disimpan

next ➝ penunjuk ke node berikutnya
###  **2.Class LinkedList**
Class LinkedList digunakan sebagai wadah yang menyimpan pointer ke node pertama.

```python
class LinkedList:
    def __init__(self):
        self.head = None

```
Saat LinkedList dibuat, head bernilai None yang berarti list masih kosong.

###  **3. Menambah Data di Awal (insert_at_first)**
```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node

```
Penjelasan:

Membuat node baru yang menunjuk ke node yang sebelumnya menjadi head

Node baru dijadikan sebagai head yang baru
###  **4. Menambah Data di Akhir (insert_at_last)**

```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        
        node = Node(data)
        node_sekarang.next = node

```
Penjelasan:

Jika list kosong → data langsung menjadi head

Jika tidak kosong → program menelusuri hingga node terakhir lalu menambahkan node baru di bagian akhir

###  **5. Menambah Data di Posisi Tertentu (insert_at)**
```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("indeks tidak valid")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head

        while urutan < index - 1:
            urutan += 1
            node_sekarang = node_sekarang.next

        node = Node(data, node_sekarang.next)
        node_sekarang.next = node

```
Penjelasan:

Mengecek apakah index valid

Jika index = 0 ➝ tambahkan di awal

Jika index > 0 ➝ telusuri node hingga posisi yang dituju lalu sisipkan data
###  **6. Menampilkan Isi List (print)**

```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ''
        node_sekarang = self.head

        while node_sekarang:
            text_print += str(node_sekarang.data) + "→"
            node_sekarang = node_sekarang.next
        
        print(text_print)

```
Penjelasan:
Jika list kosong ➝ tampilkan "data kosong"
Jika ada data ➝ tampilkan seluruh isi node secara berurutan.
###  **7. Menghitung Jumlah Node (length)**

```python
def length(self):
    urutan = 0
    data_sekarang = self.head

    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1

    return urutan

```
Penjelasan:
Fungsi ini menghitung jumlah elemen dalam list dengan menelusuri node satu per satu.
###  **8. Contoh Penggunaan Program**

```python
ll = LinkedList()

ll.insert_at_first("jeruk")
ll.insert_at_first("mangga")
ll.insert_at_first("manggis")
ll.insert_at_last("apel")
ll.insert_at(2, "durian")

ll.print()
print(ll.length())

```

**Output:**

```python
manggis→mangga→durian→jeruk→apel→
5
```

**Ringkasan Output Program**

```python
manggis→mangga→durian→jeruk→apel→
5

```
Struktur Data yang Digunakan

Node ➝ elemen penyusun Linked List

next ➝ pointer ke node berikutnya

head ➝ node pertama

while ➝ menelusuri node

None ➝ penanda akhir list

