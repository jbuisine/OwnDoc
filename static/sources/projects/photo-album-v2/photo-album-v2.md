layout: true
<div class="remark-header"><span><a href="" class="remark-quit-cross"><i class="fas fa-times fa-2x"></i></a></span></div>
<div class="remark-footer"><span>Photo album project V2
<a href="https://github.com/jbuisine/PhotoAlbumOR-v2" class="remark-icon-bottom"><i class="fab fa-github fa-1x"></i></a>
</span></div>

---
class: center, middle
# Photo album project V2

<hr>
**Description**: Second version of photo album QAP using ParadisEO C++ library in order to make statistics faster (MOEA/D, NSGA-II, Adaptative Operator Selection).

---

## Description

Relative to the [first version](https://github.com/jbuisine/OR.PhotoAlbumProject/blob/master/www/modules/routes/solution.js) project which contains client interface. This second version is created to improve performance using c++ ParadisEO library and found best AOS (adaptive operators strategy) for this real problem.

So, some statistics will be generated in order to compare the different AOS known and perhaps propose a new one.
]

---

## Installation

This project is a cmake project. So you need to install all dependencies before build it:

* [ParadisEO library](http://paradiseo.gforge.inria.fr/index.php?n=Doc.Install)
* [RapidJSON](https://github.com/Tencent/rapidjson)

Some python scripts are used to run application or create new photo album. You also need some python dependencies :

[Clarifai](https://www.clarifai.com/) dependency used for getting some information about your photo in order to compare them.

```
pip install clarifai==2.0.20
```

Some others dependencies required :
```
pip install imagehash
pacman -S grahpicsmagick
```

And finally :
```
mkdir build && cd build
cmake ..
```
---

## Utilisation

### Generate information

First of all, you need to respect this folder template architecture :

Template folder structure :
- img/*
- html/*
- solutions/*
- album-disposition.json
- info-photo.json

---

## Utilisation

### Generate information

#### 1. Clarifai API data
Generate tags information from an template folder :

```
cd application/resources/photo-album
python tag-clarifay.py <template-folder> <YOUR_CLARIFAI_API_KEY>
```

Example :
```
cd application/resources/photo-album
python tag-clarifay.py templates/FirstTemplate <YOUR_CLARIFAI_API_KEY>
```

---

## Utilisation

### Generate information

#### 2. Generate info photo file

In order to generate json file information about photos template, you need to run this command line :
```
python extractInfo.py <template-folder>
```

---

## Utilisation

### Generate information

#### 3. Generate disposition info file

```
python disposition.py <template-folder> <output-filename> <x-axis-number-photos> <y-axis-number-photos> <number-of-pages>
```

---

## Utilisation

### Generate information

#### 4. Generate photo album

```
python buildAlbum.py <template-folder> <disposition-file> <solution-file> (<solution-line>)
```

Example :
```
python buildAlbum.py templates/FirstTemplate/ album-6-2per3.json chronologic-order.sol
```

---

## Licence

[CeCILL](http://www.cecill.info/index.en.html)
