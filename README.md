# Társasjáték-napló

**Hallgató:** Müller Máté  
**Neptun-kód:** DE1AJ3  
**Tantárgy:** Szkript nyelvek Python

## Feladat leírása

A Társasjáték-napló egy grafikus Python-program, amellyel nyilvántarthatjuk a társasjátékainkat. Minden alkalommal megadhatjuk, hogy melyik társasjátékkal és hány percet játszottunk. A program játékonként és összesítve is megmutatja, hány játékalkalmat rögzítettünk és mennyi időt játszottunk.

## Funkciók

- Új társasjáték felvétele a gyűjteménybe.
- Meglévő társasjáték átnevezése.
- Társasjáték törlése, megerősítést követően.
- Minden játékalkalom külön rögzítése a játék kiválasztásával és a percben megadott játékidővel.
- Játékonkénti statisztika: alkalmak száma, összes játékidő, átlagos játékidő.
- Összesített statisztika valamennyi társasjátékra.
- A tíz legutóbbi játékalkalom megjelenítése dátummal.
- Adatok automatikus megőrzése a program bezárása után is.

## Indítás és használat

**Szükséges:** Python 3.9 vagy újabb, valamint működő Tkinter-támogatás. Külső csomagot nem kell telepíteni.

A `main.py` és a `mm_tarsasmodul.py` maradjon ugyanabban a mappában. Innen indítható:

```bash
python main.py
```

1. Az **Új játék felvétele** gombbal adj meg legalább egy társasjátékot.
2. Kattints a játék nevére.
3. Írd be a játékidőt percben (1–1440 perc).
4. Kattints az **Alkalom mentése** gombra minden egyes játék után.
5. A **Statisztika** fülön megnézheted az alkalmak számát, a játékidőt és a legutóbbi naplóbejegyzéseket.

Az adatok automatikusan a felhasználó saját mappájában létrejövő `tarsasjatekok_mm_adatok.json` fájlba kerülnek. Ez a fájl futás közben keletkezik, ezért a beadandó forráskódja továbbra is **három fájl**.

**Figyelem:** Egy társasjáték törlése a hozzá tartozó korábbi játékalkalmakat is törli. Átnevezéskor a korábbi alkalmak megmaradnak az új név alatt.

## Program felépítése

- **`main.py`**: az `MMApp` grafikus alkalmazás, a Tkinter és a `ttk` felület, gombok és eseménykezelők.
- **`mm_tarsasmodul.py`**: saját modul az adatok betöltésével, mentésével, az idő formázásával és a játékok kezelésével.
- **`README.md`**: a program és használatának leírása.

### Saját osztályok

- `MMTarsasTar`: a játékok, játékalkalmak és statisztikák kezelése. Saját metódusai például: `mm_uj_jatek`, `mm_alkalom_rogzitese`, `mm_statisztika`, `mm_jatek_torlese`.
- `MMApp`: a grafikus felület és a felhasználói események kezelése.

### Saját modul legalább három függvénye

- `mm_adatok_betoltese(utvonal)`
- `mm_adatok_mentese(utvonal, adatok)`
- `mm_ido_formazasa(percek)`

### Tanult vagy bemutatott modulok

- `tkinter`: grafikus felület, `Tk()`, `StringVar()`, `mainloop()`.
- `tkinter.messagebox` és `tkinter.simpledialog`: felugró üzenetek, adatbekérés.
- `json`: a program adatainak megőrzése, `load()`, `dump()`.
- `datetime`: az aktuális dátum rögzítése, `now()`, `strftime()`.

A grafikus felületen gombkattintások, listakijelölés (`<<TreeviewSelect>>`) és fülek közötti váltás (`<<NotebookTabChanged>>`) eseménykezelése történik.

## Előzetes témabejelentés

**Cím:** Társasjáték-napló  
**Alcím:** Grafikus társasjáték-nyilvántartó játékalkalmak rögzítésével és játékidő-statisztikával.

**Tervezett funkciók:** társasjátékok felvétele, átnevezése és törlése; minden játékalkalom külön rögzítése; játékidő és alkalomszám statisztikák; korábbi alkalmak megjelenítése; adatok mentése és visszatöltése.
