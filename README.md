# Panduan Lengkap Setup Zsh, Oh My Zsh, & Powerlevel10k 🚀

Panduan ini akan membantu Anda mengatur terminal yang cantik dan produktif menggunakan Zsh, framework Oh My Zsh, dan tema Powerlevel10k di Windows dan Linux.

## 📋 Daftar Isi
1. [Persiapan (Font)](#1-persiapan-font)
2. [Instalasi di Linux](#2-instalasi-di-linux)
3. [Instalasi di Windows](#3-instalasi-di-windows)
4. [Instalasi Oh My Zsh](#4-instalasi-oh-my-zsh)
5. [Instalasi Tema Powerlevel10k](#5-instalasi-tema-powerlevel10k)
6. [Plugin Tambahan (Opsional tapi Direkomendasikan)](#6-plugin-tambahan)

---

## 1. Persiapan (Font)
Tema Powerlevel10k menggunakan banyak ikon (Nerd Fonts). Sebelum menginstal tema, Anda **wajib** menginstal font yang mendukungnya.

1. Download **MesloLGS NF** fonts:
   - [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
   - [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
   - [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
   - [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)
2. Klik ganda pada setiap file dan pilih **Install** (Windows) atau ikuti cara instal font di Linux Anda.
3. Ubah pengaturan font di terminal Anda (VS Code, Windows Terminal, dll) menjadi `MesloLGS NF`.

---

## 2. Instalasi di Linux

Buka terminal Anda dan jalankan perintah berikut sesuai dengan distribusi Linux yang Anda gunakan:

**Ubuntu / Debian / Pop!_OS:**
```bash
sudo apt update
sudo apt install zsh curl git -y
```

**Arch Linux / Manjaro:**
```bash
sudo pacman -S zsh curl git
```

**Fedora:**
```bash
sudo dnf install zsh curl git
```

Jadikan Zsh sebagai shell default:
```bash
chsh -s $(which zsh)
```
*(Catatan: Anda mungkin perlu logout dan login kembali, atau restart komputer agar perubahan shell default berlaku).*

---

## 3. Instalasi di Windows

Di Windows, cara terbaik untuk menggunakan Zsh adalah melalui **WSL (Windows Subsystem for Linux)**.

**Langkah 1: Instal WSL (jika belum)**
Buka PowerShell sebagai Administrator dan jalankan:
```powershell
wsl --install
```
*Restart komputer jika diminta, lalu selesaikan pembuatan user dan password Ubuntu.*

**Langkah 2: Instal Zsh di WSL (Ubuntu)**
Buka terminal WSL (Ubuntu), lalu jalankan:
```bash
sudo apt update
sudo apt install zsh curl git -y
```

**Langkah 3: Jadikan Zsh sebagai shell default**
```bash
chsh -s $(which zsh)
```
*(Tutup terminal WSL dan buka kembali untuk melihat Zsh shell).*

---

## 4. Instalasi Oh My Zsh

Setelah Zsh terinstal dan menjadi default shell, instal Oh My Zsh dengan menjalankan perintah berikut di terminal:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
*Jika ditanya "Do you want to change your default shell to zsh?", ketik `Y` dan Enter.*

---

## 5. Instalasi Tema Powerlevel10k

1. Clone repositori Powerlevel10k ke dalam folder custom theme Oh My Zsh:
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

2. Buka file konfigurasi Zsh (`~/.zshrc`) menggunakan text editor (seperti nano):
```bash
nano ~/.zshrc
```

3. Cari baris `ZSH_THEME="robbyrussell"` dan ubah menjadi:
```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

4. Simpan file (`Ctrl+O`, `Enter`, lalu `Ctrl+X` untuk keluar dari nano) dan muat ulang konfigurasi:
```bash
source ~/.zshrc
```

5. **Konfigurasi Powerlevel10k:**
Setelah Anda menjalankan `source ~/.zshrc`, panduan konfigurasi Powerlevel10k (`p10k configure`) akan otomatis muncul. Jawab pertanyaan-pertanyaan yang diberikan (seperti apakah Anda melihat logo diamond, lock, dll) untuk menyesuaikan tampilan terminal Anda.

---

## 6. Plugin Tambahan (Opsional tapi Sangat Direkomendasikan)

Plugin ini akan membuat terminal Anda memiliki fitur *autocomplete* dari history (mirip Fish shell) dan pewarnaan sintaks (Syntax Highlighting).

**1. Clone Plugin Zsh Autosuggestions**
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

**2. Clone Plugin Zsh Syntax Highlighting**
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

**3. Aktifkan Plugin di `~/.zshrc`**
Buka file `~/.zshrc`:
```bash
nano ~/.zshrc
```

Cari baris `plugins=(git)` dan tambahkan plugin yang baru diinstal di bawahnya, ubah menjadi:
```bash
plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
)
```

Simpan file dan muat ulang zsh:
```bash
source ~/.zshrc
```

---
🎉 **Selesai!** Sekarang terminal Anda sudah terlihat keren, cepat, dan lebih produktif.
