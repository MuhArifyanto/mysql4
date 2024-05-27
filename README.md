# Tugas Praktikum { Pertemuan ke 11 } 


|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|Muhammad Arif Mulyanto|312310359|TI.23.A.5|Basis Data|

# Soal Latihan Praktikum ( Pegawai )

# Buat table pegawai dan isi datanya sebagai berikut
![tugas4opening](https://github.com/MuhArifyanto/mysql4/assets/147913440/34497cf6-9faf-4f38-9795-82aa0330e5d0)

**Perintah SQL :**

```
CREATE TABLE pegawai (
    idpegawai VARCHAR(5) PRIMARY KEY,
    nama_depan VARCHAR(10) NOT NULL,
    nama_belakang VARCHAR(15) NOT NULL,
    email VARCHAR(25) UNIQUE KEY,
    telepon VARCHAR(15),
    tgl_kontrak DATA,
    id_job VARCHAR(5),
    gaji INT,
    tunjangan INT
    );
```
***Output :***

![tugas4a](https://github.com/MuhArifyanto/mysql4/assets/147913440/384aba9d-df24-4475-a5cb-81f003d4dd7e)

```
INSERT INTO pegawai VALUES
  ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
```
***Output :***

![tugas4b](https://github.com/MuhArifyanto/mysql4/assets/147913440/f91ead18-5c1b-436b-981e-41c9d7268f30)


## Tugas Praktikum

**1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000 !**

```
SELECT*FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
```

***Output :***

![tugas4](https://github.com/MuhArifyanto/mysql4/assets/147913440/8cdacbf1-9779-4729-b20d-6b7a50dba82c)



**2. Tampilkan pegawai yang tunjangannya NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NULL;
```

***Output :***

![tugas4c](https://github.com/MuhArifyanto/mysql4/assets/147913440/d93b06c4-1ca8-4d44-a29d-b0099d83f73c)



**3. Tampilkan pegawai yang tunjangannya tidak NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NOT NULL;
```

***Output :***

![tugas4d](https://github.com/MuhArifyanto/mysql4/assets/147913440/fa7d9076-4625-47d2-bf63-a96b881c703b)


**4. Tampilkan/hitung jumlah baris/record tabel pegawai!**

```
SELECT COUNT(*) AS jmlh_pegawai FROM pegawai;
```

***Output :***

![tugas40](https://github.com/MuhArifyanto/mysql4/assets/147913440/b11e35c1-fc1a-460e-ab58-20245e3d4a49)


**5. Tampilkan/hitung jumlah total gaji di tabel pegawai!**

```
SELECT SUM(gaji) AS ttl_gaji FROM pegawai;
```

***Output :***

![tugas4g1](https://github.com/MuhArifyanto/mysql4/assets/147913440/42f03503-1353-47e6-81b4-12aa9ecbdc82)


**6. Tampilkan/hitung rata-rata gaji pegawai!**

```
SELECT AVG(gaji) AS mean_gaji FROM pegawai;
```

***Output :***

![tugas4j](https://github.com/MuhArifyanto/mysql4/assets/147913440/8aa17a68-3d14-4f2e-851e-152ae1e2919a)



**7. Tampilkan gaji terkecil!**

```
SELECT MIN(gaji) AS terkecil FROM pegawai;
```

***Output :***

![tugas4h](https://github.com/MuhArifyanto/mysql4/assets/147913440/de73593b-b276-4cce-b059-a12af687e979)


**8. Tampilkan gaji terbesar!**

```
SELECT MAX(gaji) AS terbesar FROM pegawai;
```

***Output :***

![tugas4i](https://github.com/MuhArifyanto/mysql4/assets/147913440/d0a575bb-9074-4140-b84a-34366fce95e5)


# Soal Latihan Praktikum ( Hewan )

# Buat table hewan dan isi datanya sebagai berikut

![tugas4last](https://github.com/MuhArifyanto/mysql4/assets/147913440/c5e45f7b-fd5b-4b94-82a8-ec1aea8ce6e0)

**Perintah SQL :**

```
CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );
INSERT INTO hewan VALUES
    ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
    ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
    ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
    ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
    ('p5', 'Fang', 'Benny', 'Dog', 'M'),
    ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
    ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
    ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
    ('p9', 'Slim', 'Benny', 'Snake', 'M');
```

***Output :***

![tugas4(1)](https://github.com/MuhArifyanto/mysql4/assets/147913440/c06719b8-42a2-454b-ab97-6b5c482c4bd2)


## Tugas Praktikum

**1. Tampilkan jumlah hewan yang dimiliki setiap owner.**

```
SELECT owner, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY owner;
```

***Output :***

![tugas4(2)](https://github.com/MuhArifyanto/mysql4/assets/147913440/720d9e7f-2961-4a34-97bc-027a1ad42c79)


**2. Tampilkan jumlah hewan berdasarkan spesies**

```
SELECT species, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY species;
```

***Output :***

![tugas4(3)](https://github.com/MuhArifyanto/mysql4/assets/147913440/a309022c-334c-4232-907c-d9939fd72a26)


**3. Tampilkan jumlah hewan berdasarkan jenis kelamin**

```
SELECT sex, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY sex;
```

***Output :***

![tugas4(4)](https://github.com/MuhArifyanto/mysql4/assets/147913440/5a2cddb0-37cf-49dc-9139-13b0ef20e60a)


**4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
```

***Output :***

![tugas4(4)](https://github.com/MuhArifyanto/mysql4/assets/147913440/2692cadc-76c7-4d95-af44-5e9d8b65d4e4)

**5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE
species IN ('Cat', 'Dog')
GROUP BY species, sex;
```

***Output :***

![tugas4(6)](https://github.com/MuhArifyanto/mysql4/assets/147913440/17a8ba72-83f5-4fc6-ba92-8ce8292647f7)


**6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja**

```
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

***Output :***

![tugas4(7)](https://github.com/MuhArifyanto/mysql4/assets/147913440/1e8f282e-90b3-4a65-99d8-75082d7beef2)


## Tulis semua perintah-perintah SQL percobaan di atas beserta outputnya!

```
CREATE DATABASE praktikum4;
USE praktikum4;
CREATE TABLE pegawai (
    idpegawai VARCHAR (5) PRIMARY KEY,
    nama_depan VARCHAR (10) NOT NULL,
    nama_belakang VARCHAR (15) NOT NULL,
    email VARCHAR (25) UNIQUE KEY,
    telepon VARCHAR (15),
    tgl_kontrak DATE,
    id_job VARCHAR (5),
    gaji INT,
    tunjangan INT
    );
INSERT INTO pegawai VALUES
        ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
SELECT * FROM pegawai;
SELECT * FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
SELECT * FROM pegawai WHERE tunjangan IS NULL;
SELECT * FROM pegawai WHERE tunjangan IS NOT NULL;
SELECT COUNT(*) AS jumlah_pegawai FROM pegawai;
SELECT SUM(gaji) AS total_gaji FROM pegawai;
SELECT AVG(gaji) AS rata_rata_gaji FROM pegawai;
SELECT MIN(gaji) AS gaji_terkecil FROM pegawai;
SELECT MAX(gaji) AS gaji_terbesar FROM pegawai;
CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );
INSERT INTO hewan (id, name, owner, species, sex)
VALUES ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
       ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
       ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
       ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
       ('p5', 'Fang', 'Benny', 'Dog', 'M'),
       ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
       ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
       ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
       ('p9', 'Slim', 'Benny', 'Snake', 'M');
SELECT * from hewan;
SELECT owner, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY owner;
SELECT species, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species;
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY sex;
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE species IN ('Cat', 'Dog') GROUP BY species, sex;
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

## Berikan Kesimpulan Anda !
``
# Pembuatan Database dan Tabel: 
- Di dalam database ini, dua tabel dibuat: pegawai dan hewan.
- Tabel pegawai berisi informasi tentang karyawan, termasuk ID karyawan, nama depan, nama belakang, email, telepon, tanggal kontrak, ID pekerjaan, gaji, dan tunjangan.
- Tabel hewan berisi informasi tentang hewan, termasuk ID hewan, nama, pemilik, spesies, dan jenis kelamin.

# Penambahan Data ke Tabel:

-  Data untuk masing-masing tabel dimasukkan menggunakan pernyataan INSERT INTO.
- Pada tabel pegawai, data karyawan ditambahkan dengan berbagai nilai untuk kolom yang telah didefinisikan.
- Pada tabel hewan, data hewan ditambahkan dengan informasi terkait pemilik dan jenis kelamin.

# Penggunaan Query untuk Pengambilan Data:

- Pengambilan Semua Data: Menggunakan SELECT * FROM untuk menampilkan seluruh data dalam tabel.
- Pengambilan Data dengan Kondisi Khusus:
  Menampilkan karyawan dengan gaji selain 2.000.000 atau 1.250.000.
  Menampilkan karyawan dengan tunjangan yang bernilai NULL atau tidak NULL.
- Penghitungan dan Agregasi Data:
  Menghitung jumlah total karyawan menggunakan COUNT.
  Menghitung total gaji seluruh karyawan menggunakan SUM.
  Menghitung rata-rata gaji karyawan menggunakan AVG.
- Menemukan gaji terkecil dan terbesar menggunakan MIN dan MAX.
  Pengelompokan Data:
  Menghitung jumlah hewan berdasarkan pemilik, spesies, dan jenis kelamin menggunakan GROUP BY.
  Menghitung jumlah hewan per kombinasi spesies dan jenis kelamin tertentu.
# poin-poin dalam SQL
- Konsistensi Penulisan dan Penggunaan Data Types: Penting untuk menggunakan tipe data yang tepat dan memastikan konsistensi dalam definisi tabel.
- Keunikan Data: Menggunakan constraint seperti PRIMARY KEY dan UNIQUE untuk memastikan keunikan data pada kolom tertentu.
- Agregasi dan Pengelompokan: Fungsi agregasi dan pengelompokan (COUNT, SUM, AVG, MIN, MAX, GROUP BY) sangat berguna untuk analisis data.
- Penggunaan NULL: Penanganan nilai NULL harus diperhatikan dalam kondisi dan agregasi.
``

