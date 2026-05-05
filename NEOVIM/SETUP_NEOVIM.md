# Panduan Lengkap Setup Neovim & LazyVim 🚀

Panduan ini akan membantu Anda menginstal dan mengatur Neovim menggunakan **LazyVim** (sebuah konfigurasi starter untuk Neovim yang sangat populer, cepat, dan modern).

## 📋 Daftar Isi
1. [Prasyarat (Requirements)](#1-prasyarat-requirements)
2. [Instalasi di Linux](#2-instalasi-di-linux)
3. [Instalasi di Windows](#3-instalasi-di-windows)
4. [Instalasi LazyVim](#4-instalasi-lazyvim)
5. [Penggunaan Dasar & Keymaps](#5-penggunaan-dasar--keymaps)

---

## 1. Prasyarat (Requirements)

Sebelum menginstal LazyVim, pastikan sistem Anda memenuhi persyaratan berikut:
- **Neovim** (versi >= 0.9.0, sangat disarankan 0.10.0+)
- **Git** (versi >= 2.19.0)
- **C Compiler** (GCC / Clang / MinGW di Windows) - *diperlukan untuk compile *treesitter* (syntax highlighting)*
- **Ripgrep (rg)** - *diperlukan untuk fitur pencarian teks di dalam file*
- **fd (fd-find)** - *diperlukan untuk mencari nama file dengan cepat*
- **Nerd Fonts** - *(Jika Anda sudah mengikuti panduan Zsh/Powerlevel10k dan menggunakan MesloLGS NF, Anda bisa melewati langkah ini).*

---

## 2. Instalasi di Linux

Buka terminal Anda dan jalankan perintah sesuai dengan distribusi Linux Anda:

### Ubuntu / Debian / Pop!_OS
Karena Neovim di repository resmi Ubuntu kadang tertinggal versinya, sangat disarankan menggunakan PPA:
```bash
sudo add-apt-repository ppa:neovim-ppa/unstable
sudo apt update
sudo apt install neovim git build-essential ripgrep fd-find -y
```

### Arch Linux / Manjaro
```bash
sudo pacman -S neovim git base-devel ripgrep fd
```

### Fedora
```bash
sudo dnf install neovim git gcc gcc-c++ ripgrep fd-find
```

---

## 3. Instalasi di Windows

Di Windows, sangat disarankan untuk menggunakan package manager seperti **Winget** atau **Scoop** untuk mempermudah instalasi.

Buka **PowerShell** (sebagai Administrator jika diperlukan) dan jalankan:

### Menggunakan Winget (Bawaan Windows 10/11)
```powershell
winget install Neovim.Neovim
winget install Git.Git
winget install BurntSushi.ripgrep.MSVC
winget install sharkdp.fd
```

*Untuk C Compiler di Windows:*
Anda dapat menginstal MSYS2 / MinGW, atau menginstal instalasi LLVM:
```powershell
winget install LLVM.LLVM
```

### Menggunakan Scoop (Alternatif)
Jika Anda menggunakan Scoop:
```powershell
scoop install neovim git ripgrep fd gcc
```

---

## 4. Instalasi LazyVim

Jika Anda sebelumnya sudah pernah menggunakan Neovim, pastikan untuk mem-backup atau menghapus konfigurasi lama Anda agar tidak terjadi konflik:

**Linux / WSL / Mac:**
```bash
# Backup konfigurasi lama (opsional)
mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.local/share/nvim ~/.local/share/nvim.bak
mv ~/.local/state/nvim ~/.local/state/nvim.bak
mv ~/.cache/nvim ~/.cache/nvim.bak
```

**Windows (PowerShell):**
```powershell
# Backup konfigurasi lama (opsional)
Move-Item $env:LOCALAPPDATA\nvim $env:LOCALAPPDATA\nvim.bak -ErrorAction SilentlyContinue
Move-Item $env:LOCALAPPDATA\nvim-data $env:LOCALAPPDATA\nvim-data.bak -ErrorAction SilentlyContinue
```

### Clone Template LazyVim
Jalankan perintah berikut untuk mengambil konfigurasi starter dari LazyVim:

**Linux / WSL:**
```bash
git clone https://github.com/LazyVim/starter ~/.config/nvim
rm -rf ~/.config/nvim/.git
```

**Windows (PowerShell):**
```powershell
git clone https://github.com/LazyVim/starter $env:LOCALAPPDATA\nvim
Remove-Item $env:LOCALAPPDATA\nvim\.git -Recurse -Force
```

### Mulai Neovim
Buka terminal / command prompt Anda dan ketik:
```bash
nvim
```
Saat pertama kali dibuka, LazyVim akan secara otomatis mendownload dan menginstal plugin module beserta semua dependensinya. Tunggu hingga proses ini selesai (akan ada tampilan progress bar dari `lazy.nvim`).

---

## 5. Penggunaan Dasar & Keymaps

LazyVim menggunakan tombol **Spasi (Space)** sebagai `Leader Key` (tombol utama untuk menjalankan command).

Beberapa shortcut (Keymaps) penting yang wajib diketahui:

### File Explorer (Neo-tree)
- `Space` + `e` : Membuka / Menutup file explorer di sebelah kiri.

### Pencarian (Telescope)
- `Space` + `Space` : Mencari file berdasarkan nama di dalam project Anda.
- `Space` + `s` + `g` : Mencari kata/teks spesifik di dalam seluruh file (menggunakan ripgrep).

### Tab dan Buffer
- `Shift` + `h` : Pindah ke buffer/tab sebelah kiri.
- `Shift` + `l` : Pindah ke buffer/tab sebelah kanan.
- `Space` + `b` + `d` : Menutup (Delete) tab/buffer yang sedang aktif.

### Terminal Terintegrasi
- `Ctrl` + `/` : Membuka / Menyembunyikan terminal mengambang (floating terminal).

### Manajemen Plugin (Lazy)
- `Space` + `l` : Membuka antarmuka package manager `lazy.nvim` untuk melihat, update, atau menghapus plugin.

### Keluar (Exit)
- Ketik `:q` lalu tekan `Enter` untuk keluar.

---
🎉 **Selesai!** Neovim Anda sekarang sudah ditenagai oleh LazyVim. Anda siap ngoding dengan performa kilat dan tampilan yang modern!
