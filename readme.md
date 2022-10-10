# Writing & Presentation Test Week 3
##### Muh Zaki Choiruddin 
##### Backend Web Development Track | Skilvul Tech4Impact

Assalamu'alaikum Wr. Wb. Di markdown ini saya akan menjelaskan berbagai materi yang telah saya pelajari selama mengikuti kegiatan `Kampus Merdeka Skilvul Tech4Impact pada track Backend Web Development`.

## Table of Contents
  - [Array](#array)
  - [Object](#object)
  - [Recursive](#recursive)
  - [Asynchronous](#asynchronous)
  - [Web Storage](#web-storage)

## Array
### Pengertian
Array adalah tipe data list order yang dapat menyimpan tipe data apapun di dalamnya. Array dapat menyimpan tipe data String, Number, Boolean, dan lainnya. Jika biasanya kita hanya dapat menyimpan satu nilai di dalam variable, dengan array kita dapat menyimpan banyak nilai di dalam satu variable.

### Membuat Array
Array dapat dibuat dengan menulis kode berikut:
```sh
let friends = [
    "Zaki",
    "Meisha",
    "Okta",
    "Fandi"
]
```

Array dapat menyimpan banyak value dengan tipe data  yang berbeda.
```sh
let info = [
    "Zaki",
    "20",
    true
]
```

### Memanggil Array
Array pada javascript dihitung dari index data ke-0. Data pertama adalah index ke-0. Untuk memanggil array ketikkan nama array diikuti bracket [nilai index] .

```sh
let friends = [
    "Zaki",
    "Meisha",
    "Okta",
    "Fandi"
]

console.log(friends[2]) // "Okta"
```
Contoh lain
```sh
let info = [
    "Zaki",
    "20",
    true
]

console.log(info[1]) // 20
```

### Update Array
Seperti tipe data dan variabel pada umumnya, kita dapat mengupdate data pada Array.
```sh
let friends = [
    "Zaki",
    "Meisha",
    "Okta",
    "Fandi"
]

let friends[0] = "Xanny"

console.log(friends)
// ["Xanny", "Meisha", "Okta", "Fandi"]
```

### Const in Array
Seperti yang kita ketahui apabila mendeklarasikan variable menggunakan const maka nilai dari variable tersebut tidak dapat diubah. Namun jika menggunakan const untuk mendeklarasikan array maka data di dalamnya masih dapat diubah karena konten di dalam array bersifat mutable.
```sh
const tools = ["VS Code", "Postman", "Figma", "Chrome"]
tools[3] = "Laragon"

console.log(tools)
// ["VS Code", "Postman", "Figma", "Laragon"]
```
Namun kita tidak dapat mengganti variable array dengan array lain.
```sh
const tools = ["VS Code", "Postman", "Figma", "Chrome"]
tools = ["NPM"]

// Uncaught TypeError: Assignment to constant variable.
```

### Properties
Seperti tipe data lainnya array juga memiliki properties, contohnya length.

#### .length
Digunakan untuk mendapatkan panjang suatu array.
```sh
const tools = ["VS Code", "Postman", "Figma", "Chrome"]
console.log(tools.length) // 4
```

### Built in Methods
Javascript sudah memudahkan kita dengan menyediakan function/method umum yang bisa kita gunakan untuk mengelola array.
#### .push
Digunakan untuk manambahkan item array pada posisi terakhir.
```sh
const tools = ["VS Code", "Postman", "Figma", "Chrome"]
tools.push("GitHub")

console.log(tools)
// ["VS Code", "Postman", "Figma", "Chrome", "GitHub"]
```

#### .pop
Berfungsi untuk menghapus item terakhir pada sebuah array.
```sh
const tools = ["VS Code", "Postman", "Figma", "Chrome"]
tools.pop()

console.log(tools)
// ["VS Code", "Postman", "Figma"]
```

#### .shift
Berfungsi untuk menghapus item pertama pada sebuah array.
```sh
const tools = ["VS Code", "Postman", "Figma", "Chrome"]
tools.shift()

console.log(tools)
// ["Postman", "Figma", "Chrome"]
```

#### .unshift
Diigunakan untuk menambahkan item di index pertama sebuah array.
```sh
const tools = ["VS Code", "Postman", "Figma", "Chrome"]
tools.unshift("Terminal")

console.log(tools)
// ["Terminal", "VS Code", "Postman", "Figma", "Chrome"]
```

#### .sort
Berfungsi untuk mengurutkan array secara ascending atau descending berdasarkan angka atau huruf
```sh
const scores = [1, 4, 23, 2]
scores.sort()
console.log(scores)
// [1, 2, 4, 23]
```

### Array Looping
Array memiliki built in methods untuk melakukan looping yaitu .map() dan .forEach(). .map() dan forEach() sama-sama digunakan untuk melakukan looping dan mengembalikan nilai baru dari operasi yang dilakukan. Perbedaannya adalah .forEach tidak dapat membuat Array baru dari hasil operasi yang ada dalam looping

#### .forEach()
Method untuk melakukan looping pada setiap elemen array. Gunakan .forEach() jika hanya memerlukan looping untuk menampilkan saja atau menyimpan ke database.
```sh
let tools = ["VS Code", "Postman", "Figma", "Chrome"]
tools.forEach(el => {
    console.log(el)
})

// "VS Code", "Postman", "Figma", "Chrome"
```

#### .map()
Untuk melakukan perulangan/looping dengan membuat array baru. Gunakan .map() jika akan melakukan operasi pada array seperti yang dapat mengubah nilai array sebelumnya.
```sh
let scores = [3, 5, 7, 2]
let finalScores = scores.map(score => {
    return score * 2
})

console.log(finalScores)
// [5, 10, 14, 4]
```

### Multidimensional Array
Multidimensional Array merupakan sebuah array di dalam array. Array multidimensi dapat ditulis seperti ini:
```sh
let users = [
    ["Zaki", 94],
    ["Meisha", 98],
    ["Okta", 82]
]
```
Cara mengaksesnya adalah
```sh
console.log(users[0][1])
// 94
```

## Object
### Pengertian
Object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method). Dalam kehidupan nyata, kita sebenarnya sudah sering menjumpai object. Entah itu benda mati atau benda hidup. Semuanya adalah object.
- Properti => Data lengkap dari sebuah object.
- Method => Action dari sebuah object. Apa saja yang dapat dilakukan dari suatu object.

### Membuat Object
Object ditandai dengan adanya curly brackets {}, contoh seperti kode berikut:
```sh
let account = {}
```
```sh
let account = {
    name: "Zaki",
    age: 20,
    country: "INA"
}
```

### Memanggil Object
#### Keseluruhan Object
```sh
let account = {
    name: "Zaki",
    age: 20,
    country: "INA"
}

console.log(account)
// call the object
```

#### Properti Object
Menggunakan dots notation
```sh
let account = {
    name: "Zaki",
    age: 20,
    country: "INA"
}

console.log(account.name)
// "Zaki"
```
atau menggunakan bracket notation
```sh
let account = {
    name: "Zaki",
    age: 20,
    country: "INA"
}

console.log(account["age"])
// 20
```

### Update Object
Kita dapat melakukan update pada variabel dengan tipe data Object. Object dapat mengupdate value dari key yang sudah tersedia dan Object juga dapat menambahkan key dan value baru.
```sh
let account = {
    name: "Zaki",
    age: 20,
    country: "INA"
}

// change new value from some key
account.country = "USA"

// add new key and value
account.laptop = "DELL"

console.log(account)
// {
    name: "Zaki",
    age: 20,
    country: "USA",
    laptop: "DELL"
}
```

### Delete Object Property
Kita dapat menghapus properti dari object menggunakan operator delete.
```sh
let account = {
    name: "Zaki",
    age: 20,
    country: "INA"
}

delete account.country
console.log(account)
// {
    name: "Zaki",
    age: 20
}
```

### Nested Object
Nested object adalah keadaan dimana terdapat object di dalam object, bahkan bisa lebih dari dua object saja.
```sh
let account = {
    name: "Zaki",
    age: 20,
    address: {
        country: "INA",
        province: "Central Java",
        zipCode: 23478
    }
}

console.log(account.address.zipCode)
// 23478
```

### Looping Object
Jika kita ingin menampilkan seluruh object properti. Kita bisa menggunakan looping. Jadi tidak perlu mengakses secara manual memanggil setiap propertinya.

```sh
let account = {
    name: "Zaki",
    age: 20,
    address: {
        country: "INA",
        province: "Central Java",
        zipCode: 23478
    }
}

for (let data in account) {
    console.log(account[data])
}

// Zaki
// 20
// {country: 'INA', province: 'Central Java', zipCode: 23478}
```
Untuk loop nested object dapat dilakukan dengan:
```sh
for (let data in account.address) {
    console.log(account.address[data])
}

// INA
// Central Java
// 23478
```

## Recursive
Recursive adalah function yang memanggil dirinya sendiri sampai kondisi tertentu. Recursive kebanyakan digunakan untuk case matematika, fisika, kimia, dan yang berhubungan dengan calculation.

### Schema
```sh
function recursive () {
    recursive()
}
```
Recursive akan berhenti memanggil dirinya sendiri jika kondisi terpenuhi
```sh
function recursive () {
    if (condition) {
        // stop calling itself
    } else {
        recursive()
    }
}
```

### Ciri - Ciri Recursive
- Fungsi rekursif selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. Kondisi ini harus dapat dibuktikan akan tercapai, karena jika tidak tercapai maka kita tidak dapat membuktikan bahwa fungsi akan berhenti, yang berarti algoritma kita tidak benar.
- Fungsi rekursif selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya. Hal ini penting diingat, karena tujuan utama dari rekursif ialah memecahkan masalah dengan mengurangi masalah tersebut menjadi masalah-masalah kecil.

#### Contoh
Fungsi rekursif menghitung mundur number
```sh
function countDown (fromNumber) {
    console.log(fromNumber)
    
    let nextNumber = fromNumber - 1
    
    if (nextNumber > 0) {
        countDown(nextNumber)
    }
}

countDown(4)
// 4
// 3
// 2
// 1
```

## Asynchronous
### Pengertian
Asynchronous programming adalah teknik yang memungkinkan program untuk memulai tugas yang berpotensi berjalan lama dan masih dapat responsif terhadap proses lain saat tugas itu berjalan, daripada harus menunggu sampai tugas itu selesai.

### Synchronous vs Asynchronous
Dalam dunia programming kedua istilah ini digunakan untuk membedakan tentang cara urutan eksekusi perintah-perintah yang ada dalam kode anda.
- Synchronous 
Setiap perintah di eksekusi satu persatu sesuai urutan kode yang anda tuliskan. Contoh:
```sh
console.log('Namaku')
console.log('Adalah')
console.log('Zaki')

// Namaku
// Adalah
// Zaki
```
Output dari kode diatas dijamin akan sesuai urutan, karena setiap perintah harus menunggu perintah sebelumnya selesai. Proses seperti ini disebut `blocking`.

- Asynchronous
Hasil eksekusi atau output tidak selalu berdasarkan urutan kode, tetapi berdasarkan waktu proses. Eksekusi dengan asynchronous tidak akan membloking atau menunggu suatu perintah sampai selesai. Daripada menunggu, asynchronous akan mengeksekusi perintah selanjutnya.
```sh
console.log('Namaku');
setTimeout(() => { console.log('Adalah')},100) // tunda selama 100 miliseconds
console.log('Zaki');

Namaku
Zaki
Adalah
```

### Callback
Callback sebenarnya adalah function bedanya dengan function pada umumnya adalah di cara eksekusinya. Jika function pada umumnya di eksekusi berurutan dari atas ke bawah maka callback di eksekusi pada point tertentu, itu sebabnya di sebut callback.
```sh
function p1() {
 console.log('p1 done')
}

function p2(callback) {
    setTimeout(
        function() {
            console.log('p2 done')
            callback()
        }, 100
    )
}

function p3() {
  console.log('p3 done')
}

p1()
p2(p3)
```
### Promise
Mekanisme baru pada fitur javascript / ES6 yang merepresentasikan sebuah object request pengolahan data yang dilakukan secara asynchronous seperti ajax, dan promise ini mewakili sebuah operasi yang belum selesai, tetapi diharapkan di masa mendatang.
Ketika melakukan sebuah request asynchronous seperti ajax, maka ada 3 kemungkinan state:
- Pending (sedang dalam proses)
- Fulfilled ( terpenuhi )
- Rejected ( dibatalkan / gagal)

```sh
let data = false;

const Promises = new Promise((resolve, reject) => {
	if (data) {
		resolve('promises has been kept')
	} else {
		reject('promise not kept')
	}
})

Promises
.then(res => console.log(`Ok ${res} !`))
.catch(res => console.log(`Its Ok ! ${res}`))
```

### Async/ Await
Async/ await adalah fitur yang hadir sejak ES2017. Fitur ini mempermudah kita dalam menangani proses asynchronous. Async/Await merupakan sebuah syntax khusus yang digunakan untuk menangani Promise agar penulisan code lebih efisien dan rapih.
- async => Mengubah function menjadi asynchronous
- await => Menunda eksekusi hingga proses asynchronous selesai

```sh
async function getPosts () {
    let response = await fetch("https://api.osorateam.com/posts")
    let data = await response.json()
    console.log(data)
}
```
Dari kode di atas berarti let data tidak akan di eksekusi sebelum proses fetch di atasnya selesai. Await bisa digunakan berkali-kali di dalam function.


## Web Storage
### Pengertian
Sebuah browser (Chrome, Opera, Safari, Firefox) memiliki tempat penyimpanannya sendiri. Web Storage biasanya digunakan untuk menyimpan data sebuah website seperti token akun pengguna, settingan website dan hal lainnya yang bersifat tidak rahasia.

### localStorage
Data yang disimpan di dalam localStorage tidak akan menghilang walaupun tab atau browser ditutup.

#### Menyimpan Data
```sh
localStorage.setItem("name", "Zaki");

// name adalah key
// Zaki adalah valuenya
```

#### Mengambil Data
Gunakan key untuk mengambil value di local storage.
```sh
localStorage.getItem("name");
```

#### Mengambil Data
```sh
localStorage.removeItem("Zaki");
```
Atau gunakan clear untuk menghapus semua data dari local storage.
```sh
localStorage.clear();
```

### sessionStorage
Menyimpan data secara sementara, data akan menghilang saat tab ditutup atau browser ditutup.

#### Menyimpan Data
```sh
sessionStorage.setItem("name", "Zaki");

// name adalah key
// Zaki adalah valuenya
```

#### Mengambil Data
Gunakan key untuk mengambil value di local storage.
```sh
sessionStorage.getItem("name");
```

#### Mengambil Data
```sh
sessionStorage.removeItem("Zaki");
```
Atau gunakan clear untuk menghapus semua data dari local storage.
```sh
sessionStorage.clear();
```