Penjelasan Kode LinkedList

Kode di atas membuat struktur data Linked List sederhana yang dapat menambah data di awal, di akhir, dan di posisi tertentu.

1. Class Node
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer


Class ini digunakan untuk membuat elemen di dalam linked list.
Setiap node menyimpan dua hal:

data → nilai yang disimpan

next → penunjuk ke node berikutnya

2. Class LinkedList
class LinkedList:
    def __init__(self):
        self.head = None


Saat linked list baru dibuat, kondisinya masih kosong, sehingga head diset menjadi None.

3. Menambah data di awal — insert_at_first()
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node


Fungsi ini membuat node baru yang langsung mengarah ke head lama. Setelah itu node baru dijadikan head yang baru.

4. Menambah data di akhir — insert_at_last()
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        
        node = Node(data)
        node_sekarang.next = node


Jika list kosong, data langsung jadi head.
Jika sudah ada isi, program mencari node terakhir lalu menyambungkan node baru di bagian ujung.

5. Menambah data di posisi tertentu — insert_at()
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


Fungsi ini digunakan untuk menyisipkan data di posisi tertentu.

Jika indeks tidak sesuai, program menolak.

Jika indeks 0, data ditaruh di depan.

Untuk posisi lainnya, program bergerak sampai node sebelum posisi yang dituju dan menambahkan node baru di tempat tersebut.

6. Mencetak isi list — print()
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


Jika list kosong, muncul tulisan “data kosong”.
Jika tidak kosong, program menampilkan semua data dari awal sampai akhir.

7. Menghitung jumlah node — length()
def length(self):
    urutan = 0
    data_sekarang = self.head

    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1

    return urutan


Fungsi ini menghitung jumlah node dengan cara menelusuri list dari awal hingga habis.

8. Pemanggilan Program
ll = LinkedList()
ll.insert_at_first("jeruk")
ll.insert_at_first("mangga")
ll.insert_at_first("manggis")
ll.insert_at_last("apel")
ll.insert_at(2, "durian")

ll.print()
print(ll.length())


Program membuat linked list, mengisi beberapa data ke dalamnya, kemudian mencetak isi list dan menghitung jumlah elemennya.
