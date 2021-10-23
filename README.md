# HizoProgress

## Version Française :
Ce script permet de créer une barre de progression complétement personnalisée comme le montre cette petite vidéo : https://asciinema.org/a/YpohbfZEd8guOIPjs0po1lmxh


### Principe de base :
La personnalisation de la barre se fait en définissant ses différents éléments :
![01](https://user-images.githubusercontent.com/48289933/138561583-5540d3f9-63b7-42a2-9abc-66b1e0adc9da.png)
 - **--body** : Le corps de la barre (par défaut : caractère = de couleur 4 (bleue)).
 - **--head** : La tête de la barre (par défaut : caractère > de couleur 1 (rouge)).
 - **--remainder** : La partie non ecouverte par le corps et la tête de la barre (par défaut : aucun caractère).
 - **--progress** : Le pourcentage de progression (par défaut : la progression en % sur 3 chiffres entre []).

### Aide :
L'aide est très développée et rend visuellement bien :
 - hizoprogress --help
 - man ./hizoprogress.fr.1

### Exemples :
De nombreux exemples sont présents dans le script, il suffit de lui indiquer l'argument **--examples**.

Ex repris :
```
for x in {0..100}
do 
    hizoprogress -p "${x}" -b "%4- " -h "%1~>" -l "100"
    sleep 0.1
done
```
![02](https://user-images.githubusercontent.com/48289933/138561719-e87e4ee4-9891-434f-a0be-633258da9f0d.png)

```
for x in {0..100}
do 
    [[ ${x} -eq 100 ]] && Text="%cThank you for waiting :)%c" || Text="Please wait pending the process in progress..."
    hizoprogress -p "${x}" -b "%4${Text}" -h "" -r "%3${Text}" -o "[%5%P%00] [%b]" -l "55"
    sleep 0.1
done
```
![03](https://user-images.githubusercontent.com/48289933/138561744-b248218b-ebf7-4cf1-8315-a69fd65e9c58.png)

```
for x in {0..100}
do 
    hizoprogress -p "${x}" -b "%22_" -h "%?‘%?-%?‘%7_@_ " -R -l "100"
    sleep 0.1
done
```
![04](https://user-images.githubusercontent.com/48289933/138561787-fe3c06db-e8a1-498f-95ee-64e6b27d11d3.png)

```
Effect=("(°<" "(°-")
for x in {0..100}
do 
    hizoprogress -p "${x}" -b "%3     ." -r "%7·" -h "%11${Effect[$((x % 2))]}" -l "100"
    sleep 0.1
done 
```
![05](https://user-images.githubusercontent.com/48289933/138561818-46b6e315-b112-4ab7-91fd-5ca86cabf805.png)


```
printf -v Effect '8m==%%1> 8=m=%%1> 8==m%%1> 8=m=%%1> %.s' {0..25}
Effect=(${Effect})
for x in {0..100}
do 
    hizoprogress -p "${x}" -o "%5%P%00 : ${Effect[${x}]}" -of "%5%P%00 : 8=m=%1>%00 ~~o ~~o ~~o"
    sleep 0.1
done
```
![06](https://user-images.githubusercontent.com/48289933/138561923-de62fa0a-dfd0-46fc-b948-3fe569674bd3.png)

*** ***

## English version :
This script allows you to create a completely customized progress bar as shown in this short video: https://asciinema.org/a/YpohbfZEd8guOIPjs0po1lmxh


### Basic principle:
The customization of the bar is done by defining its different elements:
![01](https://user-images.githubusercontent.com/48289933/138561583-5540d3f9-63b7-42a2-9abc-66b1e0adc9da.png)
 - **--body**: The body of the bar (default: character = color 4 (blue)).
 - **--head**: The head of the bar (default: character > color 1 (red)).
 - **--remainder** : The part not covered by the body and the head of the bar (default: no character).
 - **--progress**: The progress percentage (default: the progress in % on 3 digits between []).

### Help:
The help is very developed and renders visually well :
 - hizoprogress --help
 - man ./hizoprogress.fr.1

### Examples:
Many examples are present in the script, you just have to tell it the **--examples** argument.

Example taken fromAide :
L'aide est très développée et rend visuellement bien ::
```
for x in {0..100}
do 
    hizoprogress -p "${x}" -b "%4- " -h "%1~>" -l "100"
    sleep 0.1
done
```
![02](https://user-images.githubusercontent.com/48289933/138561719-e87e4ee4-9891-434f-a0be-633258da9f0d.png)

```
for x in {0..100}
do 
    [[ ${x} -eq 100 ]] && Text="%cThank you for waiting :)%c" || Text="Please wait pending the process in progress..."
    hizoprogress -p "${x}" -b "%4${Text}" -h "" -r "%3${Text}" -o "[%5%P%00] [%b]" -l "55"
    sleep 0.1
done
```
![03](https://user-images.githubusercontent.com/48289933/138561744-b248218b-ebf7-4cf1-8315-a69fd65e9c58.png)

```
for x in {0..100}
do 
    hizoprogress -p "${x}" -b "%22_" -h "%?‘%?-%?‘%7_@_ " -R -l "100"
    sleep 0.1
done
```
![04](https://user-images.githubusercontent.com/48289933/138561787-fe3c06db-e8a1-498f-95ee-64e6b27d11d3.png)

```
Effect=("(°<" "(°-")
for x in {0..100}
do 
    hizoprogress -p "${x}" -b "%3     ." -r "%7·" -h "%11${Effect[$((x % 2))]}" -l "100"
    sleep 0.1
done 
```
![05](https://user-images.githubusercontent.com/48289933/138561818-46b6e315-b112-4ab7-91fd-5ca86cabf805.png)


```
printf -v Effect '8m==%%1> 8=m=%%1> 8==m%%1> 8=m=%%1> %.s' {0..25}
Effect=(${Effect})
for x in {0..100}
do 
    hizoprogress -p "${x}" -o "%5%P%00 : ${Effect[${x}]}" -of "%5%P%00 : 8=m=%1>%00 ~~o ~~o ~~o"
    sleep 0.1
done
```
![06](https://user-images.githubusercontent.com/48289933/138561923-de62fa0a-dfd0-46fc-b948-3fe569674bd3.png)
