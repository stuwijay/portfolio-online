# Build your Dynamic Portfolio using Javascript

## Penjelasan 

### 1. Mengganti model menu

Tambahkan elemen menu mobile di dalam tag <nav>.

**Code:**
```javascript
<nav>
    <div class="menu-mobile">
        <a href="#" onclick="showMenu()">menu</a>
    </div>
    <ul id="menu">
        <li><a href="/">HOME</a></li>
        <li><a href="#">PRODUCT</a></li>
        <li><a href="#">GALLERY</a></li>
        <li><a href="#">BLOG</a></li>
        <li><a href="#">INVENTORY</a></li>
    </ul>
</nav>
```


### 2. Tambahkan Fungsi JavaScript untuk Menampilkan/Sembunyikan Menu:

Tambahkan fungsi showMenu di bagian bawah file HTML sebelum tag </body>.

**Code:**
```javascript
<script>
    function showMenu() {
        var menu = document.getElementById("menu");
        var box = document.getElementById("box-profile");

        if (menu.style.display === "block") {
            menu.style.display = "none";
            box.style.paddingTop = "0px";
        } else {
            menu.style.display = "block";
            box.style.paddingTop = "125px";
        }
    }
</script>
```

### 3. Menyembunyikan Form secara Default

a. Tambahkan ID input-form pada section form.

**Code:**
```javascript
<section id="input-form" style="display: none;">
    <form method="#" action="#">
        <div class="form">
            <label>Nama</label>
            <input type="text" name="nama" placeholder="masukkan nama anda">
        </div>
        <!-- Form fields lainnya -->
    </form>
</section>
```

b. Tambahkan Tombol Edit pada Bagian Profil:

**Code:**
```javascript
<div class="description">
    <h1>Nama Anda</h1>
    <p>Front End Designer</p>
    <a href="#input-form" class="button bg-blue" onclick="editForm()">Edit</a>
    <a href="#" class="button bg-green">Resume</a>
</div>
```

c. Tambahkan fungsi editForm di bagian bawah file HTML sebelum tag </body>.

**Code:**
```javascript
<script>
    var formMenu = document.getElementById("input-form");
    formMenu.style.display = "none";

    function editForm() {
        if (formMenu.style.display === "none") {
            formMenu.style.display = "block";
        } else {
            formMenu.style.display = "none";
        }

        var name = document.getElementById("pName").innerHTML;
        var role = document.getElementById("pRole").innerHTML;
        var available = document.getElementById("pAvailable").innerHTML;
        var usia = document.getElementById("pAge").innerHTML;
        var lokasi = document.getElementById("pLocation").innerHTML;
        var experience = document.getElementById("pExperience").innerHTML;
        var email = document.getElementById("pEmail").innerHTML;

        document.getElementById("inpName").value = name;
        document.getElementById("inpRole").value = role;
        document.getElementById("inpAvailability").value = available;
        document.getElementById("inpUsia").value = usia;
        document.getElementById("inpLokasi").value = lokasi;
        document.getElementById("inpYears").value = experience;
        document.getElementById("inpEmail").value = email;
    }
</script>

```

### 4. Menyimpan Data Form dan Memperbarui Profil

A. Tambahkan ID pada Input Form:

**Code:**
```javascript
<div class="form">
    <label>Nama</label>
    <input id="inpName" type="text" name="nama" placeholder="masukkan nama anda">
</div>
<div class="form">
    <label>Role</label>
    <input id="inpRole" type="text" name="role">
</div>
<!-- Input fields lainnya dengan ID masing-masing -->
```

B. Tambahkan event onclick pada tombol submit untuk memanggil fungsi simpanForm.

**Code:**
```javascript
<div class="form">
    <input onclick="simpanForm()" type="submit" name="submit" value="SUBMIT" class="bg-green">
</div>
<!-- Input fields lainnya dengan ID masing-masing -->
```

C. Tambahkan fungsi simpanForm di bagian bawah file HTML sebelum tag </body>.

**Code:**
```javascript
<script>
    function simpanForm() {
        formMenu.style.display = "none";

        var name = document.getElementById('inpName').value;
        var role = document.getElementById("inpRole").value;
        var available = document.getElementById("inpAvailability").value;
        var usia = document.getElementById("inpUsia").value;
        var lokasi = document.getElementById("inpLokasi").value;
        var experience = document.getElementById("inpYears").value;
        var email = document.getElementById("inpEmail").value;

        document.getElementById("pName").innerHTML = name;
        document.getElementById("pRole").innerHTML = role;
        document.getElementById("pAvailable").innerHTML = available;
        document.getElementById("pAge").innerHTML = usia;
        document.getElementById("pLocation").innerHTML = lokasi;
        document.getElementById("pExperience").innerHTML = experience;
        document.getElementById("pEmail").innerHTML = email;
    }
</script>
<!-- Input fields lainnya dengan ID masing-masing -->
```
