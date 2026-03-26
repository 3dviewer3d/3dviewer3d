# 3D Viewer

Przeglądarka plików 3D dla Windows — szybka, lekka, bez instalacji.

![3D Viewer Screenshot](https://i.imgur.com/placeholder.png)

## Obsługiwane formaty

| Format | Opis | Miniatura | Podgląd 3D |
|--------|------|-----------|------------|
| `.stl` | Stereolithography | ✅ | ✅ |
| `.step` / `.stp` | STEP (wymaga Python+OCP) | ✅ | ✅ |
| `.3mf` | 3D Manufacturing Format | ✅ | ✅ |
| `.obj` | Wavefront OBJ | ✅ | ✅ |
| `.ply` | Stanford PLY | ✅ | ✅ |
| `.gcode` | G-code (miniatura ze slicera) | ✅ | ✅ |
| `.f3d` | Fusion 360 (tylko miniatura) | ✅ | 🖼️ |

## Wymagania

- Windows 10/11 x64
- [.NET SDK 8.0](https://dotnet.microsoft.com/download/dotnet/8.0) (do budowania)
- Python 3.11 z biblioteką OCP (opcjonalnie — do plików STEP/STP)

### Instalacja Python + OCP (dla STEP):
```
py -3.11 -m pip install ocpython
```

### Instalacja zstandard (dla F3D):
```
py -3.11 -m pip install zstandard
```

## Budowanie

```bat
git clone https://github.com/TwojaNazwa/3DViewer.git
cd 3DViewer
build.bat
```

EXE zostanie wygenerowany w `publish\3DViewer.exe` (~162 MB, self-contained, bez instalacji .NET).

## Funkcje

- 🗂️ **Wiele katalogów** — dodaj kilka folderów naraz, przełączaj widoczność checkboxem
- 🔍 **Filtrowanie** — STL / STEP / 3MF / GCODE / OBJ / PLY / F3D
- ⇅ **Sortowanie** — według rozszerzenia i nazwy
- 🔎 **Wyszukiwanie** — filtruj po nazwie pliku
- 🖼️ **Miniatury** — generowane automatycznie, cache na dysku
- 🎨 **Tryby cieniowania** — Phong, Flat, Metal, Plastik, Glinka, Wireframe
- 💡 **Tła** — Ciemne, Gradient, Studio
- 🖨️ **Integracja ze slicerem** — otwórz plik bezpośrednio w PrusaSlicer / OrcaSlicer / Cura
- 🔄 **G-code** — wizualizacja ścieżek druku w 3D z kolorowym gradientem warstw

## Technologie

- **C# / .NET 8** + **WPF** — UI
- **SharpGL 3.1.1** — renderowanie OpenGL
- **Python + OCP** — parsowanie STEP
- **zstandard** — dekompresja miniatur F3D

## Licencja

CC BY-NC 4.0 — użytek niekomercyjny, wymagane podanie autora.
Szczegóły: [LICENSE](LICENSE)
