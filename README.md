# Roihu-ML

Koneoppimisen harjoittelua ja GPU-laskennan testaamista CSC:n Roihu-superkoneella.

Projektissa käytetään **PyTorchia** ja **CIFAR-10**-datasettiä yksinkertaisen koneoppimismallin kouluttamiseen Roihun GPU-ympäristössä.

Varsinainen koneoppimistehtävä löytyy notebookista:

**[cifar10_roihu.ipynb](cifar10_roihu.ipynb)**

---

## Roihun käyttöönotto

### 1. CSC-tili

Ennen projektin aloittamista tarvitset CSC-käyttäjätilin.

Tarkista, että:

* CSC-käyttäjätili on olemassa
* Haka/Virtu-yhteys toimii
* pääset kirjautumaan MyCSC-palveluun

Opiskelijaprojektin luominen edellyttää CSC-käyttäjätiliä.

[CSC:n opiskelijan aloitusohje](https://docs.csc.fi/support/tutorials/student_quick/)

---

### 2. Luo opiskelijaprojekti

Avaa [MyCSC](https://my.csc.fi/) ja valitse:

**Projects → New project**

Projektin tiedot voivat olla esimerkiksi:

| Kenttä                         | Arvo                                                                   |
| ------------------------------ | ---------------------------------------------------------------------- |
| **Project Name**               | `Roihu-ML-test`                                                        |
| **Project Description**        | `Opiskeluprojekti, jossa harjoitellaan Roihun GPU-laskentaympäristöä.` |
| **Primary field of science**   | `Engineering and technology`                                           |
| **Secondary field of science** | `Other engineering and technologies`                                   |
| **End date**                   | Valitse projektin päättymispäivä                                       |
| **Comments**                   | Halutessasi lisätietoa                                                 |

Opiskelijaprojektin enimmäisaika on 6 kuukautta.

Projektin nimen ja kuvauksen ei tarvitse olla monimutkaisia. Niissä kerrotaan lähinnä, mihin projektia käytetään.

Seuraavalla **Services**-sivulla valitaan **Roihu**.

---

### 3. Ota Roihu käyttöön

Kun projekti on luotu, avaa:

**Project → Services**

Tarkista, että projektilla on käytössä:

> **Roihu Supercomputer**

Jos Roihua ei vielä näy, valitse:

**Services → Add services → Roihu → Next → Confirm**

Kun Roihu on käytössä, pääset kirjautumaan siihen projektin **Login**-painikkeella.

Palvelun käyttöönotossa ja käynnistyksessä voi olla pieni viive, se voi kestää esimerkiksi noin 30 minuuttia.

---

### 4. Käynnistä Jupyter Notebook

Roihun etusivulla pitäisi näkyä **Pinned Apps**, josta Jupyter Notebook voidaan käynnistää.

Tässä projektissa käytetään seuraavia asetuksia.

#### Laskentaresurssit

| Asetus        | Arvo             |
| ------------- | ---------------- |
| **Project**   | Oma CSC-projekti |
| **Partition** | `gpuinteractive` |
| **CPU cores** | `4`              |
| **Memory**    | `16 GiB`         |
| **Time**      | `2:00:00`        |

Kahden tunnin varaus on tälle testille enemmän kuin riittävä.

Pienempi resurssipyyntö on myös järkevä, koska suuremmat resurssivaraukset voivat joutua odottamaan jonossa pidempään.

Lisätietoja partitioneista löytyy [CSC:n batch job partitions -ohjeesta](https://docs.csc.fi/computing/running/batch-job-partitions/).

#### Python-ympäristö

Valitse:

| Asetus                 | Arvo                  |
| ---------------------- | --------------------- |
| **Python environment** | `python-pytorch`      |
| **Module version**     | `python-pytorch/2.13` |

> **Tärkeää**
>
> Käynnistä Jupyter heti oikealla PyTorch-ympäristöllä.
>
> Älä käynnistä Jupyteria ensin `python-data`-ympäristössä ja yritä vaihtaa sitä myöhemmin `python-pytorch`-ympäristöön.
>
> Näin PyTorch, CUDA ja GPU saadaan toimimaan samassa ympäristössä.

---

### 5. Tuo Jupyter Notebook Roihuun

Kun Jupyter-ympäristö on käynnistynyt, tuo projektin notebook Roihuun.

Siirrä esimerkiksi:

```text
cifar10_roihu.ipynb
```

Jupyterin vasemmalla olevaan hakemistoon.

Avaa notebook ja seuraa sen sisältämiä ohjeita.

---

### 6. Sulje Jupyter-session

Kun olet valmis työskentelyn kanssa, sulje Jupyter-sessio, jotta varatut laskentaresurssit vapautuvat.

Roihu Dashboardissa:

**My Interactive Sessions → Oma Jupyter session → Cancel**

---

## Projektin rakenne

```text
roihu-ml/
├── README.md
├── cifar10_roihu.ipynb
└── .gitignore
```

### Notebook

`cifar10_roihu.ipynb` sisältää varsinaisen koneoppimiskokeilun:

* ympäristön tarkistamisen
* CIFAR-10-datan lataamisen
* datan visualisoinnin
* DataLoaderin
* CNN-mallin
* mallin kouluttamisen
* mallin arvioinnin
* tulosten tulkinnan
* seuraavia kokeiluja

README keskittyy Roihun käyttöönottoon. Varsinainen ML-harjoitus ja sen ohjeet löytyvät notebookista.

---

## Käytetyt teknologiat

`Python` · `PyTorch` · `Torchvision` · `CUDA` · `Jupyter Notebook` · `Matplotlib` · `CIFAR-10` · `CSC Roihu`

---

## Lähteet

* [CSC – Student quick start](https://docs.csc.fi/support/tutorials/student_quick/)
* [CSC – Batch job partitions](https://docs.csc.fi/computing/running/batch-job-partitions/)
* [CSC – Roihu](https://docs.csc.fi/computing/systems-roihu/)
* [PyTorch – CIFAR-10 tutorial](https://docs.pytorch.org/tutorials/beginner/blitz/cifar10_tutorial.html)
* [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html)
