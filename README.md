# Tugas-1-Jarkom_Naila-Cahyarani-Idelia_063

- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)

## Question 1
> Rancanglah topologinya menggunakan Cisco Packet Tracer.

## Question 2
> Setiap mahasiswa memiliki base network unik, dengan aturan: 10.(NRP mod 256).0.0

NRP 5027241063 mod 256 = 23, maka base: 10.63.0.0.

## Question 3
> Lakukan perhitungan subnetting dengan VLSM & CIDR di Spreadsheet untuk seluruh jaringan LAN dan link antar-router.

<img width="1057" height="554" alt="image" src="https://github.com/user-attachments/assets/c1ab8ab7-aa94-4212-8688-630632ad928b" />

1. Sekretariat – 380 host → /23
- Network: 10.63.0.0/23
- Range Host: 10.63.0.1 – 10.63.1.254
- Broadcast: 10.63.1.255
- Gateway (biasanya .1): 10.63.0.1
- Memakai 2 blok /24: 10.63.0.x dan 10.63.1.x 

2. Bidang Kurikulum – 220 host → /24
- Network: 10.63.2.0/24
- Range: 10.63.2.1 – 10.63.2.254
- Broadcast: 10.63.2.255
- Gateway: 10.63.2.1

3. Bidang Guru & Tendik – 95 host → /25
- Network: 10.63.3.0/25
- Range: 10.63.3.1 – 10.63.3.126
- Broadcast: 10.63.3.127
- Gateway: 10.63.3.1

4. Bidang Sarana Prasarana – 45 host → /26
- Network: 10.63.3.128/26
- Range: 10.63.3.129 – 10.63.3.190
- Broadcast: 10.63.3.191
- Gateway: 10.63.3.129

5. Bidang Pengawas Sekolah (Cabang) – 18 host → /27
- Network: 10.63.3.192/27
- Range: 10.63.3.193 – 10.63.3.222
- Broadcast: 10.63.3.223
- Gateway: 10.63.3.193

6. Server & Admin – 6 host → /29
- Network: 10.63.3.224/29
- Range: 10.63.3.225 – 10.63.3.230
- Broadcast: 10.63.3.231
- Gateway: 10.63.3.225

7. Link Router P2P – /30
- Network: 10.63.3.232/30
- Range: 10.63.3.233 – 10.63.3.234
- Broadcast: 10.63.3.235
- Router A: 10.63.3.233, Router B: 10.63.3.234

<img width="1442" height="262" alt="image" src="https://github.com/user-attachments/assets/a5993df9-60fc-4bf1-afba-1ce92849645b" />

<img width="1442" height="150" alt="image" src="https://github.com/user-attachments/assets/0c0ac622-5db9-4a0c-901a-048d0d240620" />

Jaringan Cabang & Server" adalah agregasi dari:
- 10.63.3.0/25 (Guru & Tendik),
- 10.63.3.128/26 (Sarpras),
- 10.63.3.192/27 (Pengawas),
- 10.63.3.224/29 (Server),
- 10.63.3.232/30 (Link).

Jika diperhatikan bahwa:

- 10.63.3.0/25 mencakup 10.63.3.0 sampai 10.63.3.127
- 10.63.3.128/26 mencakup 10.63.3.128 sampai 10.63.3.191
- 10.63.3.192/27 mencakup 10.63.3.192 sampai 10.63.3.223
- 10.63.3.224/29 mencakup 10.63.3.224 sampai 10.63.3.231
- 10.63.3.232/30 mencakup 10.63.3.232 sampai 10.63.3.235

Semua subnet ini berurutan dan dimulai dari 10.63.3.0 hingga 10.63.3.235. Maka semua subnet di 10.63.3.x bisa diwakili oleh satu route: 10.63.3.0/24.

+-------------------------------------------------------------+
|                  Base Network: 10.63.0.0/16                   |
+-------------------------------------------------------------+
|                                                               |
|  +-----------+  +-----------+  +----------------------------+ |
|  | /23       |  | /24       |  | /24                      | 
|  | 10.63.0.0 |  | 10.63.2.0 |  |10.63.3.0/24 (Aggregated) |
|  | Sekret.   |  | Kurik.    |  |                          |
|  +-----------+  +-----------+  +----------------------------+ |
|                                                               |
+-------------------------------------------------------------+
