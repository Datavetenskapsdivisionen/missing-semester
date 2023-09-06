---
marp: true
theme: uncover

---

## Haskell Workshop
	
### Installera Haskell (utan docker)

- Vad är Docker egentligen?
- Vad är WSL
- Installera WSL
- Installera Haskell på WSL/Linux 
- Haskell trickzz
- Troubleshooting
---

# Installera WSL

I Powershell kör: `wsl --install`

![](attachments/screenshot27.png)

Efter detta är klart behöver datorn startas om.

---

# Konfigurera WSL

Öppna upp `Ubuntu` i startmenyn.
Skriv in ditt önskade användarnamn och lösenord 
```bash
$ Enter new UNIX username: <a good name here>
$ New password: <a good password here>
```

Lösenordet du skriver in kommer inte att synas men det skrivs fortfarande.

![](attachments/screenshot21.png)

---
# Uppdatera Ubuntu

I WSL kör: `sudo apt update && apt upgrade`
Programmet kan fråga om bekräftelse likt: `.. continue? [Y/n]?`
Skriv bara `y` och enter.

P.S
Notera att Y är stor bokstav i `[Y/n].`
Detta innebär att `y` väljs om man klickar enter utan att skriva
![](attachments/screenshot20.png)

----

# Installera Haskells beroenden

För att installera Haskell behövs vissa paket. Installera dessa genom att skriva:

`sudo apt install build-essential curl libffi-dev libffi8ubuntu1 libgmp-dev libgmp10 libncurses-dev libncurses5 libtinfo5`

---
# Installera Haskell (wooho)

Kopiera installations scriptet från www.haskell.org/ghcup och kör det
`curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh`
![](attachments/screenshot17.png)

Tryck `enter` och skriv `y` på allt som dyker upp.
För att testa att allt funkar. Kör i WSL `ghci`, du kan behöva stänga och öppna fönstret.

----
# Installera Code

Om du inte redan installerat VSCode kan du göra det nu.

I Powershell, kör `winget install vscode`

![](attachments/screenshot9.png)

---

# Installera extensions
Du behöver, `WSL, Haskell, Haskell Syntax Highlighting`

![](attachments/screenshot7.png)

___

# Använda WSL i Code

Vänstra hörnet visar status

![](attachments/screenshot5.png)

___
# Använda WSL i Code

Öppna mappen du har öppen i WSL.
`CTRL + SHIFT + P`
`> Reopen Folder in WSL`
![](attachments/screenshot4.png)

---

# Installera bibliotek i Haskell

För att installera exempelvis QuickCheck, kör:

`cabal install --lib QuickCheck`

![](attachments/screenshot2.png)

För andra bibliotek, ersätt `QuickCheck`
`cabal install --lib <Library>`

---
# Troubleshooting


* Virtualisation är av
* HLS funkar inte
* Error när jag laddar hem haskell

---

# HLS funkar inte

Du kan behöva byta GHC version till en som stöds.

I WSL, kör: `ghcup tui`

Navigera med piltangenterna till det markerade och tryck `I` för att installera och sedan `S` för att välja.

![](attachments/screenshot1.png)
