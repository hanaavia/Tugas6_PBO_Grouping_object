# Tugas6_PBO_Grouping_object

PersonalOrganizer.java
import java.util.ArrayList;
import java.util.Scanner;
class Task {
private String title;
private String description;
public Task(String title, String description) {
this.title = title;
this.description = description;
}
public String getTitle() {
return title;
}
public String getDescription() {
return description;
}
@Override
public String toString() {

2

return "Judul: " + title + " | Deskripsi: " + description;
}
}
public class PersonalOrganizer {
public static void main(String[] args) {
ArrayList<Task> tasks = new ArrayList<>();
Scanner scanner = new Scanner(System.in);
int choice;
do {
System.out.println("\n=== Personal Organizer ===");
System.out.println("1. Tambah Tugas");
System.out.println("2. Lihat Semua Tugas");
System.out.println("3. Hapus Tugas");
System.out.println("4. Keluar");
System.out.print("Pilih menu: ");
choice = scanner.nextInt();
scanner.nextLine(); // clear buffer
switch (choice) {
case 1:
System.out.print("Masukkan judul tugas: ");
String title = scanner.nextLine();
System.out.print("Masukkan deskripsi tugas: ");
String description = scanner.nextLine();
tasks.add(new Task(title, description));
System.out.println("Tugas berhasil ditambahkan!");
break;
case 2:
System.out.println("\nDaftar Tugas:");
if (tasks.isEmpty()) {
System.out.println("Tidak ada tugas.");
} else {
for (int i = 0; i < tasks.size(); i++) {
System.out.println((i + 1) + ". " + tasks.get(i));
}
}
break;
case 3:
System.out.print("Masukkan nomor tugas yang akan dihapus: ");
int index = scanner.nextInt();
if (index > 0 && index <= tasks.size()) {
tasks.remove(index - 1);
System.out.println("Tugas berhasil dihapus!");
} else {

3

System.out.println("Nomor tugas tidak valid.");
}
break;
case 4:
System.out.println("Terima kasih! Keluar dari aplikasi.");
break;
default:
System.out.println("Pilihan tidak valid, coba lagi.");
}
} while (choice != 4);
scanner.close();
}
}


Code: LibraryCatalog.java
import java.util.ArrayList;
import java.util.Scanner;
class Book {
private String title;
private String author;
private int year;
public Book(String title, String author, int year) {
this.title = title;
this.author = author;
this.year = year;
}
public String getTitle() {
return title;
}
@Override

5

public String toString() {
return "Judul: " + title + " | Penulis: " + author + " | Tahun: " + year;
}
}
public class LibraryCatalog {
public static void main(String[] args) {
ArrayList<Book> catalog = new ArrayList<>();
Scanner scanner = new Scanner(System.in);
int choice;
do {
System.out.println("\n=== Library Catalog ===");
System.out.println("1. Tambah Buku");
System.out.println("2. Lihat Semua Buku");
System.out.println("3. Cari Buku");
System.out.println("4. Hapus Buku");
System.out.println("5. Keluar");
System.out.print("Pilih menu: ");
choice = scanner.nextInt();
scanner.nextLine(); // clear buffer
switch (choice) {
case 1:
System.out.print("Masukkan judul buku: ");
String title = scanner.nextLine();
System.out.print("Masukkan nama penulis: ");
String author = scanner.nextLine();
System.out.print("Masukkan tahun terbit: ");
int year = scanner.nextInt();
catalog.add(new Book(title, author, year));
System.out.println("Buku berhasil ditambahkan!");
break;
case 2:
System.out.println("\nDaftar Buku:");
if (catalog.isEmpty()) {
System.out.println("Tidak ada buku dalam katalog.");
} else {
for (int i = 0; i < catalog.size(); i++) {
System.out.println((i + 1) + ". " + catalog.get(i));
}
}
break;
case 3:
System.out.print("Masukkan judul buku yang dicari: ");
String searchTitle = scanner.nextLine().toLowerCase();

6

boolean found = false;
for (Book book : catalog) {
if (book.getTitle().toLowerCase().contains(searchTitle)) {
System.out.println(book);
found = true;
}
}
if (!found) {
System.out.println("Buku tidak ditemukan.");
}
break;
case 4:
System.out.print("Masukkan nomor buku yang akan dihapus: ");
int index = scanner.nextInt();
if (index > 0 && index <= catalog.size()) {
catalog.remove(index - 1);
System.out.println("Buku berhasil dihapus!");
} else {
System.out.println("Nomor buku tidak valid.");
}
break;
case 5:
System.out.println("Keluar dari katalog. Terima kasih!");
break;
default:
System.out.println("Pilihan tidak valid, coba lagi.");
}
} while (choice != 5);
scanner.close();
}
}

Code: StudentRecordSystem.java
import java.util.ArrayList;
import java.util.Scanner;
class Student {
private String nim;
private String name;
private String major;
public Student(String nim, String name, String major) {
this.nim = nim;
this.name = name;
this.major = major;
}
public String getNim() {
return nim;
}
public String getName() {

8

return name;
}
public String getMajor() {
return major;
}
@Override
public String toString() {
return "NIM: " + nim + " | Nama: " + name + " | Jurusan: " + major;
}
}
public class StudentRecordSystem {
public static void main(String[] args) {
ArrayList<Student> records = new ArrayList<>();
Scanner scanner = new Scanner(System.in);
int choice;
do {
System.out.println("\n=== Student Record System ===");
System.out.println("1. Tambah Mahasiswa");
System.out.println("2. Lihat Semua Mahasiswa");
System.out.println("3. Cari Mahasiswa");
System.out.println("4. Hapus Mahasiswa");
System.out.println("5. Keluar");
System.out.print("Pilih menu: ");
choice = scanner.nextInt();
scanner.nextLine(); // clear buffer
switch (choice) {
case 1:
System.out.print("Masukkan NIM: ");
String nim = scanner.nextLine();
System.out.print("Masukkan Nama: ");
String name = scanner.nextLine();
System.out.print("Masukkan Jurusan: ");
String major = scanner.nextLine();
records.add(new Student(nim, name, major));
System.out.println("Mahasiswa berhasil ditambahkan!");
break;
case 2:
System.out.println("\nDaftar Mahasiswa:");
if (records.isEmpty()) {
System.out.println("Belum ada data mahasiswa.");

9

} else {
for (Student s : records) {
System.out.println(s);
}
}
break;
case 3:
System.out.print("Masukkan NIM yang dicari: ");
String searchNim = scanner.nextLine();
boolean found = false;
for (Student s : records) {
if (s.getNim().equalsIgnoreCase(searchNim)) {
System.out.println("Data ditemukan: " + s);
found = true;
break;
}
}
if (!found) {
System.out.println("Mahasiswa dengan NIM " + searchNim + " tidak
ditemukan.");
}
break;
case 4:
System.out.print("Masukkan NIM mahasiswa yang akan dihapus: ");
String deleteNim = scanner.nextLine();
boolean removed = records.removeIf(s ->
s.getNim().equalsIgnoreCase(deleteNim));
if (removed) {
System.out.println("Data mahasiswa berhasil dihapus.");
} else {
System.out.println("Mahasiswa dengan NIM " + deleteNim + " tidak
ditemukan.");
}
break;
case 5:
System.out.println("Keluar dari sistem. Terima kasih!");
break;
default:
System.out.println("Pilihan tidak valid, coba lagi.");
}
} while (choice != 5);

10

scanner.close();
}
}

Code: NotebookApp.java
import java.util.ArrayList;
import java.util.Scanner;
class Note {
private String title;
private String content;
public Note(String title, String content) {
this.title = title;
this.content = content;
}
public String getTitle() {
return title;
}
public String getContent() {
return content;
}

12

@Override
public String toString() {
return "Judul: " + title + "\nIsi: " + content;
}
}
public class NotebookApp {
public static void main(String[] args) {
ArrayList<Note> notes = new ArrayList<>();
Scanner scanner = new Scanner(System.in);
int choice;
do {
System.out.println("\n=== Personal Notebook ===");
System.out.println("1. Tambah Catatan");
System.out.println("2. Lihat Semua Catatan");
System.out.println("3. Cari Catatan");
System.out.println("4. Hapus Catatan");
System.out.println("5. Keluar");
System.out.print("Pilih menu: ");
choice = scanner.nextInt();
scanner.nextLine(); // clear buffer
switch (choice) {
case 1:
System.out.print("Masukkan judul catatan: ");
String title = scanner.nextLine();
System.out.print("Masukkan isi catatan: ");
String content = scanner.nextLine();
notes.add(new Note(title, content));
System.out.println("Catatan berhasil ditambahkan!");
break;
case 2:
System.out.println("\nDaftar Catatan:");
if (notes.isEmpty()) {
System.out.println("Belum ada catatan.");
} else {
for (int i = 0; i < notes.size(); i++) {
System.out.println((i + 1) + ". " + notes.get(i).getTitle());
}
}
break;
case 3:
System.out.print("Masukkan judul catatan yang dicari: ");

13

String searchTitle = scanner.nextLine().toLowerCase();
boolean found = false;
for (Note note : notes) {
if (note.getTitle().toLowerCase().contains(searchTitle)) {
System.out.println("\nCatatan ditemukan:\n" + note);
found = true;
}
}
if (!found) {
System.out.println("Catatan tidak ditemukan.");
}
break;
case 4:
System.out.print("Masukkan judul catatan yang akan dihapus: ");
String deleteTitle = scanner.nextLine().toLowerCase();
boolean removed = notes.removeIf(note ->
note.getTitle().toLowerCase().equals(deleteTitle));
if (removed) {
System.out.println("Catatan berhasil dihapus.");
} else {
System.out.println("Catatan dengan judul tersebut tidak ditemukan.");
}
break;
case 5:
System.out.println("Keluar dari Notebook. Sampai jumpa!");
break;
default:
System.out.println("Pilihan tidak valid, coba lagi.");
}
} while (choice != 5);
scanner.close();
}
}
