# public-domain-library-books

## Disclaimer

Instructions are for unix systems. If you use Windows look into
`Powershell Expand-Archive` commands alternatives for the zip sections.

## Build

### 1. Go to book location

```
cd ./ebooks/{book}
```

### 2. Remove old file

```
rm -f dist/{bookname}.epub
```

### 3. Movce to source

```
cd src-epub
```

### 4. Create new epub file

```
zip -X0 ./{bookname}.epub mimetype
```

### 5. Add book content to epub file

```
zip -r {bookname}.epub META-INF epub
```

**_Note: epub can be under name "OEBPS "depending of the original source_**

### 6. Move book to distrobution folder

```
mv ./src-epub/{bookname}.epub ../dist
```

## Add other formats

### 2. Kobo (kepub.epub)

#### 1. Go to book location

```
cd ./ebooks/{book}
```

#### 2. Remove old file

```
rm -f dist/{bookname}.kepub.epub
```

#### 3. Movce to source

```
cd src-epub
```

#### 4. Create new epub file

```
zip -X0 ./{bookname}.epub mimetype
```

#### 5. Add book content to epub file

```
zip -r {bookname}.kepub.epub META-INF epub
```

**_Note: epub can be under name "OEBPS "depending of the original source_**

#### 6. Move book to distrobution folder

```
mv ./src-epub/{bookname}.kepub.epub ../dist
```

### Kindle (azw3)

#### 1. Go to book location

```
cd ./ebooks/{book}
```

#### 2. Remove old file

```
rm -f dist/{bookname}.azw3
```

#### 3. Movce to source

```
cd src-azw3
```

#### 4. Create new epub file

```
zip -X0 ./{bookname}.epub mimetype
```

#### 5. Add book content to epub file

```
zip -r {bookname}.epub META-INF epub
```

**_Note: epub can be under name "OEBPS "depending of the original source_**

#### 6. Convert book to azw3 file

```
ebook-convert {bookname}.epub {bookname}.azw3 --pretty-print --no-inline-toc --max-toc-links=0 --prefer-metadata-cover
```

**_Will ignore complex css like clamp() and @media_**

#### 7. Move file to distrobution

```
mv ./{bookname}.azw3 ../dist
```

#### 8. Remove temporary files

```
rm -f {bookname}.epub
```

## Add new book

### 1. Create new location

```
cd ebooks && mkdir {book} && cd {book}
```

### 2. Add content folders

```
mkdir {dist,original,src-epub,ksrc-epub}
```

### 3. Move origin file

```
mv {path}/{bookname}.epub ./original
```

### 4. Extract source

```
unzip ./original/{bookname}.epub -d ./src-epub
```
