
# **Implementasi Stack dan Queue di Python**

Dokumentasi ini menjelaskan implementasi dasar struktur data **Stack** dan **Queue** menggunakan bahasa Python.
Keduanya menggunakan tipe data **list**, karena Python menyediakan operasi yang efisien seperti `append()`, `pop()`, dan indexing.


##  **1. Stack (LIFO — Last In, First Out)**

Stack adalah struktur data yang elemen terakhir masuk akan menjadi elemen pertama yang keluar.

###  **Membuat Stack**

```python
stack = []
```

###  **Push (Menambah Elemen ke Stack)**

```python
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack:", stack)
```

**Output:**

```
Stack: ['A', 'B', 'C']
```

###  **Pop (Menghapus Elemen Teratas)**

```python
element = stack.pop()
print("Pop:", element)
```

**Output:**

```
Pop: C
```

###  **Peek (Melihat Elemen Teratas Tanpa Menghapus)**

```python
topElement = stack[-1]
print("Peek:", topElement)
```

**Output:**

```
Peek: B
```

###  **Cek Apakah Stack Kosong**

```python
isEmpty = not bool(stack)
print("isEmpty:", isEmpty)
```

**Output:**

```
isEmpty: False
```

###  **Ukuran Stack**

```python
print("Size:", len(stack))
```

**Output:**

```
Size: 2
```


##  **2. Queue (FIFO — First In, First Out)**

Queue adalah struktur data yang mengeluarkan elemen pertama yang masuk.

###  **Membuat Queue**

```python
queue = []
```

###  **Enqueue (Menambah Elemen ke Queue)**

```python
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue:", queue)
```

**Output:**

```
Queue: ['A', 'B', 'C']
```

###  **Dequeue (Menghapus Elemen Depan)**

```python
element = queue.pop(0)
print("Dequeue:", element)
```

**Output:**

```
Dequeue: A
```

###  **Peek (Melihat Elemen Depan Tanpa Menghapus)**

```python
frontElement = queue[0]
print("Peek:", frontElement)
```

**Output:**

```
Peek: B
```

###  **Cek Apakah Queue Kosong**

```python
isEmpty = not bool(queue)
print("isEmpty:", isEmpty)
```

**Output:**

```
isEmpty: False
```

###  **Ukuran Queue**

```python
print("Size:", len(queue))
```

**Output:**

```
Size: 2
```


##  **Ringkasan Output Program**

### **Stack**

```
Stack: ['A', 'B', 'C']
Pop: C
Peek: B
isEmpty: False
Size: 2
```

### **Queue**

```
Queue: ['A', 'B', 'C']
Dequeue: A
Peek: B
isEmpty: False
Size: 2
```


##  **Struktur Data yang Digunakan**

* `append()` ➝ menambah elemen
* `pop()` ➝ menghapus elemen (terakhir / berdasarkan index)
* indexing `[0]` dan `[-1]` ➝ melihat elemen depan/teratas
* `len()` ➝ menghitung jumlah elemen
* `bool(list)` ➝ mengecek apakah list kosong






