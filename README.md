# Tutorial 5

## Performance Testing Screenshots

### All student

Before:
![alt text](<readme_stuffs/1 - gui.png>)
![alt text](<readme_stuffs/1 - cmd.png>)

After:
![alt text](<readme_stuffs/1 - gui - optimized.png>)
![alt text](<readme_stuffs/1 - cmd - optimized.png>)

### All student name

Before:
![alt text](<readme_stuffs/2 - gui.png>)
![alt text](<readme_stuffs/2 - cmd.png>)

After:
![alt text](<readme_stuffs/2 - gui - optimized.png>)
![alt text](<readme_stuffs/2 - cmd - optimized.png>)

### Highest GPA

Before:
![alt text](<readme_stuffs/3 - gui.png>)
![alt text](<readme_stuffs/3 - cmd.png>)

After:
![alt text](<readme_stuffs/3 - gui - optimized.png>)
![alt text](<readme_stuffs/3 - cmd - optimized.png>)

### Profiling Screenshot:

![alt text](<readme_stuffs/record profiling.png>)

Berdasarkan screenshots performance pada all-student, student-name, dan highest-gpa, terlihat jelas bahwa terdapat perbedaan performance yang besar. "Before" adalah sebelum melakukan profiling (optimasi) dan "After" adalah setelah profiling (optimasi). Terlihat jelas bahwa performance yang diperoleh dari JMeter measurements meningkat dengan signifikan (dapat dilihat dari hasil measurements setiap test plan). Jadi, ketiga test plan mengalami improvement yang sangat signifikan.

## Reflection

1. Jika diperhatikan, IntelliJ Profiler lebih berfokus dari aspek saat eksekusi , seperti alokasi memori, CPU time, dan lainnya, sedangkan JMeter lebih berfokus pada performance aplikasi (diuji dengan beban/load tertentu). Saya rasa keduanya penting, karena dengan memanfaatkan JMeter dan IntelliJ Profiler, kita jadi dapat memaksimalkan both performance overall (karena seperti simulasi dengan diberikan load dari user) dan yang berhubungan dengan performance (CPU Time, running time, penggunaan memori, etc).

2. Karena dengan profiling, kita dapat melihat kira-kira bagian mana pada program kita yang memakan paling banyak resources (seperti running time didominasi bagian mana, penggunaan CPU, alokasi memory, dan lainnya). Dengan demikian, akan membantu programmer mendapat informasi lebih terkait cara berjalannya aplikasi saat eksekusi dan tentunya menemukan kelemahan aplikasi, sehingga dapat melakukan opotimasi padabagian-bagian yang berdampak major terlebih dahulu juga.

3. Menurut saya efektif, karena terdapat visualisasi yang mempermudah saya ketika mencari bagian mana saja sih yang eprlu dioptimisasi. Misal, ketika ada method yang memakan waktu lama saat dieksekusi, akan diberi logo waktu berwarna merah beserta waktu eksekusinya, sehingga mempermudah saya juga ketika melakukan optimisasi. Kemudian juga ada keterangan alokasi-alokasi resources dengan detail, sehingga dapat membantu saya menemukan weak points dari program saya.

4. Tentunya ketika memikirkan ide kira-kira bagian mana yang bisa diubah agar performancenya bisa meningkat. Misal saya tahu bahwa method X memakan resources paling banyak, kemudian saya merasa bahwa method tersebut sudah cukup efektif, sehingga perubahan-perubahan yang saya lakukan menjadi tidak memberikan pengaruh yang signifikan. Dengan demikian, ketika profiling kembali, permasalahan yang muncul tetaplah pada bagian program yang sama. Cara saya untuk overcomenya adalah tentunya observe bagian-bagian yang berhubungan dengan method tersebut, kemudian juga bisa sambil mencari referensi dari internet pada bagian yang saya rasa dapat dioptimized.

5. Bagi saya, dapat mempermudah saya mengidentifikasi bagian mana program saya yang memakan resources terbanyak. Dengan demikian, potongan program yang saya optimisasi adalah yang paling berdampak banyak, sehingga ketika telah berhasil dioptimisasi, performance akan emningkat secara signifikan. Tanpa detail alokasi-alokasi saat waktu eksekusi, mungkin akan lebih sulit menentukan kira-kira method mana yang paling boros resources, sehingga dapat berakhir refactor method yang sebenarnya sudah optimized. Jadi, IntelliJ Profiler dapat membatnu memaksimalkan waktu dan resources ketika refactor program untuk optimisasi.

6. Tentunya membandingkan di part mana saja terdapat perbedaan tersebut, apakah kira-kira terdapat korelasinya. Selain itu, kembali ke main point dari keduanya, di mana JMeter berfokus pada performance ketika diberikan suatu request atau load tertentu, sedangkan IntelliJ Profiler berfokus di alokasi resources pada waktu eksekusi. Dengan demikian, saat membandingkan dan ditemukan perbedaan, dapat dilihat juga konteksnya apakah lebih mengarah ke alokasi resources atau performance.

7. Melihat potongan programmana yang harus diprioritaskan berdasarkan hasil profiling dan JMeter. Setelah itu, melihat kira-kira apa yang bisa diubah, apakah struktur data yang digunakan dapat diubah agar lebih optimized (misal tadinya menggunakan array, ternyata lebih optimized jika menggunakan hash map). Selain itu, sebisa mungkin memanfaatkan fitur bawaan karena biasanya sudah optimized (misal findAll pada repository, dan lain sebagainya). Untuk memastikan program tetap berjalan sebagaimana mestinya, tentunya saya berhati-hati dalam melakukan perubahan pada kode yang terpengaruh. Selain itu, saya juga melakukan testing (manual) untuk memastikan bahwa ternyata memang berjalan sebagaimana mestinya (untuk program skala besar mungkin akan lebih efisien jika menggunakan automated testing).