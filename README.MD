# Exercise Javascript Interview

<div align="center">
  
  <h1>JS Submissions Solutions</h1>
</div>

##### 1. Tulislah fungsi untuk isPalindrom menerima string sebagai argument. Fungsi ini membersihkan string dari karakter non-alfanumerik, mengubahnya menjadi huruf kecil, dan kemudian memeriksa apakah string yang dibalik sama dengan string aslinya


```javascript
function isPalindrom(str) {
  //code
  return
}
isPalindrom('katak')); // expected true
isPalindrom('racecar')); // expected true
isPalindrom('ini terbalik') //expected false
```

<details><summary><b>Solution</b></summary>

```javascript
function isPalindrom(str) {
  str = str.toLowerCase();
  const alphanumericsChars = 'abcdefghijklmnopqrstupwxyz0123456789';

  let cleanStr = '';
  for (let i = 0; i < str.length; i++) {
    if (alphanumericsChars.includes(str[i])) {
      cleanStr += str[i];
    } else {
      alert('ini bukan palindrom');
    }
  }
  return cleanStr === cleanStr.split('').reverse().join('');
}

console.log(isPalindrom('katak'));

cara lain:
// pakai regex
function isPalindrom(str) {
  // Menghapus karakter non-alfanumerik dan mengonversi ke huruf kecil
  str = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase();

  // Memeriksa apakah string yang dibalik sama dengan string aslinya
  return str === str.split('').reverse().join('');
}
```

</details>

---

##### 2. Tulislah perulangan untuk Fibonacci ini

```javascript
function generateFibonnacci(n) {

  //code
  return
}
console.log(generateFibonnacci(10)) expected 0,1,1,2,3,5,8,13
```

<details><summary><b>Solution</b></summary>

```javascript
function generateFibonnacci(n) {
  let num_Fibonannacci = [];
  let n1 = 0;
  let n2 = 1;

  for (let i = 0; i <= n; i++) {
    num_Fibonannacci.push(n1);
    let total = n1 + n2;
    n1 = n2;
    n2 = total;
  }

  return num_Fibonannacci;
}
console.log(generateFibonnacci(10))

cara lain:
// pakai spread operator dan perulangan
let num_Fibonannacci = [];
let n1 = 0;
let n2 = 1;

for (let i = 0; i <= 10; i++) {
  if (i === 0 || i === 1) {
    num_Fibonannacci = [...num_Fibonannacci, i];
  } else {
    let total = n1 + n2;
    num_Fibonannacci = [...num_Fibonannacci, total];
    n1 = n2;
    n2 = total;
  }
}
console.log(num_Fibonannacci);
```

</details>

---
##### 3. Tulislah perulangan yang memisahkan angka genap dan ganjil sampai 100 kmmbalikan hasilnya

```javascript

// menggunakan if else dan spread operator
for() {

  //code
  
}
console.log({ num_Genap, num_Ganjil }); expected num_genap : 0,2,4,6,8,.., num_ganjil: 1,3,5,7,9,11,13,..
```

<details><summary><b>Solution</b></summary>

```javascript

// menggunakan if else dan spread operator

 let num_Ganjil = [];
 let num_Genap = [];
 for (let i = 0; i <= 100; i++) {
   if (i % 2 == 0) {
     num_Genap = [...num_Genap, i];
   } else {
     num_Ganjil = [...num_Ganjil, i];
   }
 }
console.log({ num_Genap, num_Ganjil })

cara lain:
// menggunakan ternary dan method push
let num_Ganjil = [];
let num_Genap = [];
for (let i = 0; i <= 100; i++) {
  i % 2 == 0 ? num_Genap.push(i) : num_Ganjil.push(i);
}
console.log({ num_Genap, num_Ganjil })
```
</details>

---
##### 4. Tulislah perulangan menampilkan bilangan prima

```javascript

// menggunakan if else dan spread operator
for() {

  //code
  
}
console.log(num_Prima); expected 2,3,5,7,11,13,17,19,...

```

<details><summary><b>Solution</b></summary>

```javascript

// menggunakan if else dan spread operator

let num_Prima = [];
for (let i = 1; i <= 100; i++) {
  let bill = 0;
  for (a = 1; a <= i; a++) {
    if (i % a == 0) {
      bill = bill + 1;
    }
  }

  if (bill == 2) {
    num_Prima = [...num_Prima, i];
  }
}

console.log(num_Prima);
```

</details>

---

##### 5. Tulislah perulangan yang menampilkan data array yang double

```javascript

const dataArrayy = [9, 3, 6, 4, 2, 5, 6, 3, 1, 2, 7, 8, 8, 6, 5, 22, 7];
for() {

  //code
  
}
console.log(numArray); expected 9,3,6,4,2,5,1,7,8,22
```

<details><summary><b>Solution</b></summary>

```javascript

const dataArray = [9, 3, 6, 4, 2, 5, 6, 3, 1, 2, 7, 8, 8, 6, 5, 22, 7];
let num_Array = [];
let num_Count = '';

for (let i = 0; i < dataArray.length; i++) {
  let tampil = false;

  for (let a = 0; a < num_Array.length; a++) {
    if (dataArray[i] == num_Array[a]) {
      tampil = true;
    }
  }

  if (!tampil) {
    num_Array = [...num_Array, dataArray[i]];
    let total_Muncul = 0;
    for (e = 0; e < dataArray.length; e++) {
      if (dataArray[i] == dataArray[e]) {
        total_Muncul = total_Muncul + 1;
      }
    }
    num_Count += `angka ${dataArray[i]} sebanyak ${total_Muncul} \n`;
  }
}
console.log(num_Array);
console.log(num_Array.length);

cara lain dengan sedikit memakai perulangan looping
const dataArrayy = [9, 3, 6, 4, 2, 5, 6, 3, 1, 2, 7, 8, 8, 6, 5, 22, 7];

const numCount = {};
const numArray = [];

for (let i = 0; i < dataArray.length; i++) {
  const num = dataArray[i];

  if (!numCount[num]) {
    numCount[num] = 1;
    numArray.push(num);
  } else {
    numCount[num]++;
  }
}

console.log(numArray);
```

</details>

---

##### 6. Tulislah fungsi yang menampilkan kata yang dibalik (reverse)

```javascript

function balikKata(kata) {

  //code
  
}
console.log(balikKata('beca di jalan malioboro')); expected oroboilam nalaj aceb
```

<details><summary><b>Solution</b></summary>

```javascript

function balikKata(kata) {
  return kata.split('').reverse().join('');
}

console.log(balikKata('beca di jalan malioboro'));


```
</details>

---

##### 7. Tulislah fungsi untuk Fizz Buzz

```javascript

function fizzBuzz(n) {

  //code
  
}
console.log(fizzBuzz(20));
expected :
Jika kelipatan 3 dan 5, cetak fizzbuzz
jika kelipatan 3 tapi bukan 5 cetak fizz
jika kelipatan 5 tapi bukan 3, cetak buzz
id bukan kelipatan 3 atau 5 cetak i
```

<details><summary><b>Solution</b></summary>

```javascript

  for (let i = 1; i <= n; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
      console.log('FizzBuzz');
    } else if (i % 3 === 0) {
      console.log('Fizz');
    } else if (i % 5 === 0) {
      console.log('Buzz');
    } else {
      console.log(i);
    }
  }
}

console.log(fizzBuzz(20));


```
</details>

---

##### 8. Tulislah fungsi untuk cetakSegitigasSiku

```javascript

function cetakSegitigasSiku(tinggi) {

  //code
  
}
console.log(etakSegitigasSiku(5));
expected
*
**
***
****
*****
```

<details><summary><b>Solution</b></summary>

```javascript
jika bintang 1 yg diatas
function cetakSegitigaSiku(tinggi) {
  for (let i = 1; i <= tinggi; i++) {
    let baris = '';
    for (let j = 1; j <= i; j++) {
      baris += '*';
    }
    console.log(baris);
  }
}

console.log(etakSegitigasSiku(5));
expected
*
**
***
****
*****

jika bintang 1 yg dibawah
function cetakSegitigaSikuBintang(tinggi) {
  for (let i = tinggi; i >= 1; i--) {
    let baris = '';
    for (let j = 1; j <= i; j++) {
      baris += '*';
    }
    console.log(baris);
  }
}
expected
*****
****
***
**
*



```
</details>

---
##### 9. Tulislah fungsi untuk isEven(numbers, n), tentukan apakah element atau digit ke n dalam sebuah array deret adalah bilangan genap

```javascript

function cetakSegitigasSiku(tinggi) {

  //code
  
}
console.log(`Apakah angka ke-${n} genap? ${result}`);
```

<details><summary><b>Solution</b></summary>

```javascript
function isEven(numbers, n) {
  return n >= 0 && n < numbers.length && numbers[n] % 2 === 0;
}

// Contoh penggunaan:
const deretAngka = [2, 4, 6, 8, 10];
const n = 2;

const result = isEven(deretAngka, n);
console.log(`Apakah angka ke-${n} genap? ${result}`);

```
</details>

---


##### 10. Tulislah fungsi TwoSum jika arraynya adalah [3, 5, 2, -4, 8, 11] dan jumlahnya 7, program Anda harus mengembalikan [[11, -4], [2, 5]] karena 11 + -4 = 7 dan 2 + 5 = 7

```javascript

function twoSum(arr, S){

  //code
hint: Pendekatan yang simpel terhadap masalah ini adalah dengan mengulang setiap angka dan kemudian
mengulangi lagi melalui array 
  
}
console.log(twoSum([3, 5, 2, -4, 8, 11], 7))
```

<details><summary><b>Solution</b></summary>

```javascript
// fungsi penjumlahan dua kita yang akan dikembalikan
// semua pasangan dalam array yang berjumlah S
function twoSum(arr, S) {

  var sums = [];

// periksa setiap elemen dalam array
  for (var i = 0; i < arr.length; i++) { 

// tentukan apakah kedua elemen ini berjumlah S
    for (var j = i + 1; j < arr.length; j++) {

      // tentukan apakah kedua elemen ini berjumlah S
      if (arr[i] + arr[j] === S) {
        sums.push([arr[i], arr[j]]);
      }

    }

  }

  // mengembalikan semua pasangan bilangan bulat yang berjumlah S
  return sums;

}


console.log(twoSum([3, 5, 2, -4, 8, 11], 7))

```
</details>

---

##### 11. Tulis sebuah fungsi JavaScript untuk menemukan dan mengembalikan bilangan terbesar dalam sebuah larik bilangan bulat.

```javascript

function findLargestNumber(arr) {
    
}
const numbers1 = [12, 5, 27, 8, 16];
console.log(findLargestNumber(numbers1));  // Output: 27
```

<details><summary><b>Solution</b></summary>

```javascript

function findLargestNumber(arr) {

  if (arr.length === 0) {
        return "larik kosong"
    }

    let largetsNumber = arr[0];

    for (let i =1; i < arr.length; i ++) {
        if (arr[i] > largetsNumber) {
            largestNumber = arr[i];
        }
    }

    return largestNumber;

}

const numbers2 = [4, 11, 9, 3, 21];
console.log(findLargestNumber(numbers2));  // Output: 21

```
</details>

---

##### 12. Tulis sebuah fungsi untuk menghitung faktorial dari sebuah bilangan. Faktorial dari n adalah produk semua bilangan bulat positif dari 1 hingga n.

```javascript

function hitungFaktorial(n) {

}

expected const hasilFaktorial5 = hitungFaktorial(5);
console.log("Faktorial dari 5 adalah:", hasilFaktorial5);  // Output: 120


```

<details><summary><b>Solution</b></summary>

```javascript
hint: faktorial yaitu mengalikan semua bilangan dari 1 ke n misal 5 = 5 * 4 * 3 * 2 * 1


function hitungFaktorial(n) {
    if ( n === 0 || n === 1) {
        return 1;
    } else {
        return n * hitungFaktorial(n - 1)
    }
}

expected const hasilFaktorial8 = hitungFaktorial(8);
console.log("Faktorial dari 8 adalah:", hasilFaktorial8);  // Output: 40320

```
</details>

---

##### 13. Diberikan dua larik terurut, tulis sebuah fungsi untuk menggabungkan keduanya menjadi sebuah larik terurut. misal [1,3,5] & [2,4,6]


```javascript

function mergeSortedArrays(arr1, arr2) {

}

const arr1 = [1, 3, 5];
const arr2 = [2, 4, 6];
expected const hasilGabungan = mergeSortedArrays(arr1, arr2);
console.log("Hasil Gabungan:", hasilGabungan);  // Output: [1, 2, 3, 4, 5, 6]

```

<details><summary><b>Solution</b></summary>

```javascript

function mergeSortedArrays(arr1, arr2) {
    let mergedArray = [];
    let i = 0;
    let j = 0;

    while (i < arr1.length && j < arr2.length) {
        if (arr1[i] < arr2[j]) {
            mergedArray.push(arr1[i]);
            i++;
        } else {
            mergedArray.push(arr2[j]);
            j++;
        }
    }

    // Menambahkan sisa elemen dari arr1 (jika ada)
    while (i < arr1.length) {
        mergedArray.push(arr1[i]);
        i++;
    }

    // Menambahkan sisa elemen dari arr2 (jika ada)
    while (j < arr2.length) {
        mergedArray.push(arr2[j]);
        j++;
    }

    return mergedArray;
}

// Contoh penggunaan fungsi:
const arr1 = [1, 3, 5];
const arr2 = [2, 4, 6];
const hasilGabungan = mergeSortedArrays(arr1, arr2);
console.log("Hasil Gabungan:", hasilGabungan);  // Output: [1, 2, 3, 4, 5, 6]

```
</details>

---

##### 14. Tulis sebuah fungsi untuk memeriksa apakah dua string adalah anagram, yaitu memiliki huruf yang sama dalam urutan yang berbeda. hint: Anagram adalah dua string yang memiliki huruf yang sama, jumlah huruf yang sama, tetapi urutan hurufnya berbeda. Misalnya, "listen" dan "silent"

```javascript

function isAnagram(str1, str2) {

}

const string1 = "listen";
const string2 = "silent";
const isAnagramResult = isAnagram(string1, string2);
expected console.log(`Apakah "${string1}" dan "${string2}" anagram?`, isAnagramResult);  // Output: true

```

<details><summary><b>Solution</b></summary>

```javascript

function isAnagram(str1, str2) {
    // Menghapus spasi dan mengonversi ke huruf kecil untuk memastikan keakuratan
    const cleanStr1 = str1.replace(/\s/g, '').toLowerCase();
    const cleanStr2 = str2.replace(/\s/g, '').toLowerCase();

    // Mengonversi string menjadi array, mengurutkannya, dan menggabungkannya kembali
    const sortedStr1 = cleanStr1.split('').sort().join('');
    const sortedStr2 = cleanStr2.split('').sort().join('');

    // Membandingkan string yang sudah diurutkan
    return sortedStr1 === sortedStr2;
}

// Contoh penggunaan fungsi:
const string1 = "listen";
const string2 = "silent";
const isAnagramResult = isAnagram(string1, string2);
console.log(`Apakah "${string1}" dan "${string2}" anagram?`, isAnagramResult);  // Output: true

```
</details>

---

##### 15. Diberikan sebuah larik yang mungkin berisi elemen duplikat, tulis sebuah fungsi untuk menghapus elemen duplikat tersebut dan mengembalikan larik baru yang hanya berisi elemen unik.


```javascript

function removeDuplicates(arr) {

}

expected const inputArray = [1, 2, 2, 3, 4, 4, 5];
const resultArray = removeDuplicates(inputArray);
console.log("Array setelah menghapus duplikat:", resultArray); // Output [1,2,3,4,5]

```

<details><summary><b>Solution</b></summary>

```javascript

function removeDuplicates(arr) {
    // Menggunakan Set untuk mendapatkan elemen unik
    const uniqueArray = [...new Set(arr)];
    return uniqueArray;
}

// Contoh penggunaan fungsi:
const inputArray = [1, 2, 2, 3, 4, 4, 5];
const resultArray = removeDuplicates(inputArray);
console.log("Array setelah menghapus duplikat:", resultArray);   //  Output [1,2,3,4,5]

```
</details>

---

##### 16. Implementasikan algoritma pengurutan sederhana, seperti pengurutan hitungan (counting sort).


```javascript

function countingSort(arr) {

}

expected const inputArray = [4, 2, 3, 1, 4, 2, 3];
const resultArray = countingSort(inputArray);
console.log("Array setelah Counting Sort:", resultArray); // Output [1,2,2,3,3,4,4]

```

<details><summary><b>Solution</b></summary>

```javascript

function countingSort(arr) {
    // Menemukan nilai maksimum dalam larik
    const max = Math.max(...arr);
    
    // Membuat larik hitungan untuk menghitung kemunculan setiap nilai
    const countArray = Array(max + 1).fill(0);

    // Menghitung kemunculan setiap nilai dalam larik
    for (let i = 0; i < arr.length; i++) {
        countArray[arr[i]]++;
    }

    // Membangun larik hasil berdasarkan kemunculan nilai
    const sortedArray = [];
    for (let i = 0; i < countArray.length; i++) {
        while (countArray[i] > 0) {
            sortedArray.push(i);
            countArray[i]--;
        }
    }

    return sortedArray;
}

// Contoh penggunaan fungsi:
const inputArray = [4, 2, 3, 1, 4, 2, 3];
const resultArray = countingSort(inputArray);
console.log("Array setelah Counting Sort:", resultArray);  //  Output [1,2,2,3,3,4,4]


```
</details>

---

##### 17. Implementasikan pencarian biner dalam larik terurut.                                                                              hint: Binary Search adalah metode pencarian efisien yang hanya dapat diterapkan pada larik terurut.

```javascript

function binarySearch(sortedArray, target) {


}

expected// Contoh penggunaan fungsi:
const sortedArray = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const targetValue = 7;
const resultIndex = binarySearch(sortedArray, targetValue);

if (resultIndex !== -1) {
    console.log(`Nilai ${targetValue} ditemukan pada indeks ${resultIndex}.`);
} else {
    console.log(`Nilai ${targetValue} tidak ditemukan dalam larik.`);
}   // Output  nilai 7 ditemukan pada indeks 6.


```

<details><summary><b>Solution</b></summary>

```javascript

function binarySearch(sortedArray, target) {
    let left = 0;
    let right = sortedArray.length - 1;

    while (left <= right) {
        const mid = Math.floor((left + right) / 2);

        if (sortedArray[mid] === target) {
            return mid; // Nilai ditemukan, kembalikan indeks
        } else if (sortedArray[mid] < target) {
            left = mid + 1; // Pencarian di sebelah kanan
        } else {
            right = mid - 1; // Pencarian di sebelah kiri
        }
    }

    return -1; // Nilai tidak ditemukan
}


expected// Contoh penggunaan fungsi:
const sortedArray = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const targetValue = 7;
const resultIndex = binarySearch(sortedArray, targetValue);

if (resultIndex !== -1) {
    console.log(`Nilai ${targetValue} ditemukan pada indeks ${resultIndex}.`);
} else {
    console.log(`Nilai ${targetValue} tidak ditemukan dalam larik.`);
}   // Output  nilai 7 ditemukan pada indeks 6.


```
</details>

---

##### 18. Implementasikan pencarian dalam graf menggunakan Depth-First Search (DFS).                                                        hint: DFS adalah algoritma pencarian yang digunakan untuk menjelajah atau mencari informasi dalam graf atau struktur data lainnya

```javascript
class Graph {
        constructor() {

        }

}

expected // Contoh penggunaan:
const graph = new Graph();

graph.addVertex('A');
graph.addVertex('B');
graph.addVertex('C');
graph.addVertex('D');
graph.addVertex('E');
graph.addEdge('A', 'B');
graph.addEdge('B', 'C');
graph.addEdge('C', 'D');
graph.addEdge('D', 'E');
graph.addEdge('E', 'A');

const dfsResult = graph.dfs('A');
console.log('Depth-First Search Result:', dfsResult);

```

<details><summary><b>Solution</b></summary>

```javascript

class Graph {
    constructor() {
        this.adjacencyList = {};
    }

    addVertex(vertex) {
        if (!this.adjacencyList[vertex]) {
            this.adjacencyList[vertex] = [];
        }
    }

    addEdge(vertex1, vertex2) {
        this.adjacencyList[vertex1].push(vertex2);
        this.adjacencyList[vertex2].push(vertex1);
    }

    dfs(startVertex) {
        const result = [];
        const visited = {};

        const dfsTraversal = (vertex) => {
            if (!vertex) return;

            result.push(vertex);
            visited[vertex] = true;

            this.adjacencyList[vertex].forEach((neighbor) => {
                if (!visited[neighbor]) {
                    dfsTraversal(neighbor);
                }
            });
        };

        dfsTraversal(startVertex);

        return result;
    }
}

expected // Contoh penggunaan:
const graph = new Graph();

graph.addVertex('A');
graph.addVertex('B');
graph.addVertex('C');
graph.addVertex('D');
graph.addVertex('E');
graph.addEdge('A', 'B');
graph.addEdge('B', 'C');
graph.addEdge('C', 'D');
graph.addEdge('D', 'E');
graph.addEdge('E', 'A');

const dfsResult = graph.dfs('A');
console.log('Depth-First Search Result:', dfsResult);

```
</details>

---





