# Snow-melt volcanic mudflow (lahar) simulator (laharsim) and window app — companion source for the book

Design documents and code for the snow-melt volcanic mudflow (lahar) simulator built in ***Toward a Million Lines XIV — Building a Snowmelt Lahar Simulator*** (Japanese title 『LLM で 100 万行のソフトウェア開発 XIV — 融雪型火山泥流のシミュレータをつくる』; the book is in Japanese).

`laharsim` (Python) computes a lahar produced when a hot collapse mass runs over snow on a volcano: a depth-averaged flow of a water–sediment mixture with bed erosion and deposition, snow melting and entrainment (the snow carried as ice), and heat exchange (frictional heat and the heat of rock blocks). It runs an **idealized snowy volcano** (no data needed), the **1926 Taisho lahar** and a **large winter collapse** on **Tokachi-dake** (real terrain from the DEM of the Geospatial Information Authority of Japan), and a sensitivity set of 19 runs, and writes 2-D and 3-D animations, figures and hazard-class maps. A Windows **window app** (Flutter) sets the parameters, starts the computation, shows progress and plays the animations. **The window holds no computation of its own**: every button runs a `laharsim` command and reads the result files it writes. In this project **the design documents are the source of the code**.

## Download

**The ready-to-run app and the source are on the [Releases](../../releases) page**, not in this repository. The release has three separate ZIPs:

| File | Contents |
|:---|:---|
| `laharsim_exe.zip` | The Windows window app, ready built (**Japanese screens**), with the simulator it runs, the two Tokachi-dake case files and a small-example launcher |
| `laharsim_exe_en.zip` | The same app (**English screens** by default) |
| `laharsim.zip` | Design documents (`docs/`, Japanese, L1-L4, the source; `docs_en/`, the complete set for English readers: L1-L3 translated into English, L4 the Japanese originals as is) in separate folders, the code (`src/laharsim/`, `src/floodsim/`, `app/`), the requirements specification (105 requirements), the case files, and empty databases (`ledger/`) |

The app needs Python 3.11 and numpy, scipy, numba, matplotlib, pillow and pyproj on your PC (see the README inside the ZIPs); extract to a short path. There is **no APK** (the app is a Windows desktop app). The app is **not code-signed**, so Windows may warn you. Computation results and tests are not included. The Tokachi-dake elevation data is not included; the window fetches it for you. The first run takes a few minutes (numba compiles); try the bundled small example first.

You are free to change the design documents and the code and compare the results.

---

## License

- **The author holds the copyright.**
- **The code is under the GNU General Public License v3.0 or later (GPL-3.0-or-later).** The full text is [`LICENSE`](LICENSE). **If you modify it and distribute it, you must publish the source under the same GPL-3.0-or-later terms.**
- **The design documents and the text are under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0).** This covers `docs/`, `docs_en/`, the READMEs and the other written text of this repository, and the text of the matching book. See [`LICENSE-DOCS.md`](LICENSE-DOCS.md).
- **If you use them, say so.** State where it came from (the title of the book and the name of this repository) and keep the copyright notice. If you changed it, say that you changed it.
- **In this project the design documents are the source of the code.** When you publish something made from this code, **publish the design documents together with the code.**
- Third-party components (numpy, scipy, numba, matplotlib, pillow, pyproj installed by `pip install .`; the Flutter engine inside the EXEs) remain under their own original licenses.
- Provided "as is", without warranty — as the GPL-3.0 text says.

## 著作権とライセンス

- **著作権は、著者にあります。**
- **コードは、GNU General Public License v3.0 以降（GPL-3.0-or-later）です。**全文は [`LICENSE`](LICENSE) です。**改変して配布するときは、同じ GPL-3.0 以降の条件で、ソースを公開する義務があります。**
- **設計書と文章は、Creative Commons 表示-継承 4.0 国際（CC BY-SA 4.0）です。**このリポジトリの `docs/`・`docs_en/`・README ほかの文章と、対応する本の文章が当たります。内容は [`LICENSE-DOCS.md`](LICENSE-DOCS.md) です。
- **使ったときは、使ったことを書いてください。**どこから使ったか（本の題名と、このリポジトリの名前）と、著作権の表示を、使った先に書いてください。直したときは、直したことも書いてください。
- **このプロジェクトでは、設計書がコードの源です。**コードを使って作ったものを公開するときは、**設計書も、コードと一緒に公開してください。**
- 第三者の部品（`pip install .` で入る numpy・scipy・numba・matplotlib・pillow・pyproj、EXE の中の Flutter の engine）は、それぞれの元のライセンスのままです。
- 現状のまま（as is）提供します。保証はありません（GPL-3.0 の全文のとおりです）。
