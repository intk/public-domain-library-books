# public-domain-library-books

## Disclaimer

Instructions are for unix systems. If you use Windows look into `Powershell Expand-Archive` commands alternatives for the zip sections.

## Build

### 1. Go to book location

```
cd ./{book}
```

### 2. Remove old file

```
rm -f dist/{bookname}.epub
```

### 3. Create new epub file

```
zip -X0 ./dist/{bookname}.epub ./src/mimetype
```

### 4. Add book content to epub file

```
zip -rX9 ./dist/{bookname}.epub ./src/META-INF ./src/epub
```

**_Note: epub can be under name "OEBPS "depending of the original source_**

## Add new book

### 1. Create new location

```
mkdir {book} && cd {book}
```

### 2. Add content folders

```
mkdir {dist,original,src}
```

### 3. Move origin file

```
mv {path}/{bookname}.epub ./original
```

### 4. Extract source

```
unzip ./original/{bookname}.epub -d ./src
```
