Implementasi LinkedList di Python
# Implementasi LinkedList di Python

Dokumentasi ini menjelaskan implementasi dasar struktur data **Linked List** menggunakan bahasa Python. Linked List terdiri dari node-node yang saling terhubung satu arah melalui pointer `next`.

---

## 1. Class Node

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer


Class Node merepresentasikan satu elemen dalam Linked List.
Setiap node menyimpan dua informasi:

data → nilai yang disimpan

next → penunjuk ke node berikutnya

2. Class LinkedList
class LinkedList:
    def __init__(self):
        self.head = None


Saat objek LinkedList dibuat, bagian head masih kosong sehingga bernilai None.

3. Menambah Data di Awal List — insert_at_first()
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node


Fungsi ini menambahkan data di bagian paling depan list dengan:

Membuat node baru yang menunjuk ke head lama

Menjadikan node tersebut sebagai head baru

4. Menambah Data di Akhir — insert_at_last()
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        
        node = Node(data)
        node_sekarang.next = node


Jika list kosong → data langsung jadi head.
Jika tidak kosong → program menelusuri hingga node terakhir lalu menambahkan node baru di bagian akhir.

5. Menambah Data pada Posisi Tertentu — insert_at()
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


Langkah fungsi:

Mengecek validitas index

Jika index = 0 → masukkan ke depan

Jika index selain 0 → telusuri hingga posisi yang dituju dan sisipkan node baru

6. Menampilkan Isi List — print()
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


Jika list tidak punya data → tampilkan "data kosong".
Jika ada data → tampilkan seluruh node berurutan dari depan hingga akhir.

7. Menghitung Jumlah Node — length()
def length(self):
    urutan = 0
    data_sekarang = self.head

    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1

    return urutan


Fungsi ini menghitung total elemen pada Linked List dengan menelusuri node satu per satu.

8. Contoh Penggunaan Program
ll = LinkedList()

ll.insert_at_first("jeruk")
ll.insert_at_first("mangga")
ll.insert_at_first("manggis")
ll.insert_at_last("apel")
ll.insert_at(2, "durian")

ll.print()
print(ll.length())


Output berisi daftar data dari linked list dan jumlah nodenya.
