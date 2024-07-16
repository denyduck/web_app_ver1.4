# WEBAPP TEMPLATES

**Projekt se zabývá vytvořením šablon serverové části kodu webových aplikací pro budoucí nasazení v komerčním použíti. Vytvoří se několik verzí projektu od nejméně složitého jako běžná webová aplikace po složitější kterou bude webový magazín nebo eshopové řešení. Každá verze bude uložena jako šablona, tak aby byla samostatně použitelná.**

## Cíle

Cílem tohoto projektu je postupně vybudovat komplexní backendovou aplikaci, přičemž každy krok zahrnuje jak vytvoření jednotlivých částí systému tak i dokumentaci k šabloně. Tento přístup má několik specifických cílů:

### Dílčí cíle:

#### Učení a porozumění
- Pochopit a implementovat různé aspekty backendových aplikací.

#### Modularita
- Vytvářet komoponenty, které mohou být snadno rozšířeny nebo opakovaně použity v různých projektech

#### Přehledná dokumentace
- Usnadnit navigaci a porozmění každému kroku v projektu
- udržování čitelnosti a přehlednosti
- Vytvářet jasnou a přehlednou dokumentaci

#### Praktická zkušnost

#### Flexibilita
- rozšiřování a upraveni podle kontkrétnách potřeb

## Struktura projektu

- [Git, GIThub](#GIT)
- [Docker, nasazení aplikace ](#DOCKER)
- [Projektový adresář](Projektovy_adresar.md)
- [Frontend](#frontend)
- [Backend](#backend)
- [Database](#database)
- [API](#api)
- [Backup](#backup)
- [Testování](#testovani)

- [GitHub](#github)
- [Návrh tříd a diagramy](#navrh-trid-a-diagramy)

## GIT

Projekt je versován na Github do třech základních větví. Pracuje se s hlavní větví, ve které je vždy funkční kod a funguje jako poslední záloha projektu. Vedlejší větev *develop* je vývojová, kde probíhá hlavní vývoj. Poslední podružná větev pracuje na nejnižší úrovni jako ne například funkce nebo metoda. Název větve bude vždy odvozen od úkolu fce nebo metody.

> 1. main - hlavní větev
> 2. develop - vývojřská větev, která zahrnuje celky
> 3. funkce develop - poddružná větev DEVELOPu pro vývoj jednotlivých funkcí, metod


## DOCKER

### dockerfile
Aplikace se nasazuje v kontejneru s dalšími zavislostmi, které jsou pro běh serveru nutné. Samotná aplikace bude konfigurovaní v souboru dockerfile. Zahrnuje napřiklad instalaci všech *requirements, app path, verze balíčků atd*

```
# Use an official Python runtime as a parent image
FROM python:3.8-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
```

### docker-compose.yml
Pro nasazení vytvořeného předsloženého *image* z dockerfile se vytvoří spouštěcí script docker-compose.yml. Ten nasazuje samotne kontejnery do jedné aplikace. Kontejnery mezi sebou komunikují. 

```
# 
```

