# Bug Projek Solver

Nama: Rohima Ningsih

## Kasus 01 - CRUD Buku
1. Variabel $daftarBuku tidak cocok dengan $books di Blade -> diganti jadi $books
2. Nama route books.simpan tidak cocok dengan books.store -> diganti jadi books.store
3. Route hapus memakai PUT, padahal form DELETE -> diganti jadi Route::delete
4. Fungsi store tidak menyimpan data dan tanpa validasi -> ditambah validate() dan Book::create()

## Kasus 02 - Relasi Buku dan Kategori
1. category_id tanpa foreign key -> ditambah foreignId()->constrained()
2. Relasi Book memakai hasMany -> diganti belongsTo
3. Relasi Category memakai belongsTo -> diganti hasMany
4. Controller memanggil with('categories') -> diganti with('category')
5. Dropdown mengirim nama, bukan ID -> value diganti $category->id
6. Daftar menampilkan angka category_id -> diganti $book->category->name

## Kasus 03 - Pencarian dan Filter
1. Nama parameter form dan Controller berbeda (keyword/category vs search/kategori) -> disamakan
2. Pencarian harus persis sama -> diganti LIKE
3. orWhere tidak dikelompokkan -> dibungkus function
4. Controller mengirim hasilBuku, Blade memakai $books -> diganti books
5. Kotak cari kosong setelah submit (old) -> diganti request('keyword')
