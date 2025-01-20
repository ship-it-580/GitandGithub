# Gitti ja Gittihubi ohjeet
Gitti on versionhallintatyökalu, eka träkätään tiedostoa ja sitten lisätään indexiin, minkä jälkeen se commitoidaan. 

<img src="gitti.jpg" width="600" />

# Aloitus
Eka aja terminaattorilla komennon, mikä tekee .git kansion:  ```git init```

Voit lisätä käyttäjänimen, että commiteissa sitten näköö kuka ne on tehnyt, niin syyllinen löytyy nopeasti: ```git config --global user.name <tähän nimi, jos käyttää välilyöntiä, niin se tulee laittaa "" sisään>```\
Sitten loopilla vaan sähköpostiosoite kanssa: git config --global user.email <tähän sähköposti, jos käyttää välilyöntiä, niin se tulee laittaa "" sisään>```

---
# Käytetyt komennot
Tosi hyvä komento tilanteen tarkstukseen on: ```git status``` se kertoo millä haaralla mennään ja mitä committeja on tehty\
sitten jos haluaa nähdä commitit tarkemmin niin siihen käytetään ```git log``` se antaa pirusti tietoa niin laittaa ```git log --oneline``` niin helpottaa kummasti

```mermaid
  graph LR
  Työkansio --> |git add| Indeksi
  Indeksi --> |git commit| Commit
  Commit --> |git push| GitHub
 ```

Kun on tehny muutoksia niin pitää ensin lisätä tiedosto indexiin komennolla ```git add .<tiedoston nimi>``` tai jos laittaa kaiken niin ```git add .``` riittää\
Sitten kun halutut tiedostot indexissä, ajaa vaan komennon ```git commit -m "tähä viesti mitä commitissa muutettin tai lisättiin"```\
Jos paukautit väärän tiedoston indexiin, sen saa poist ```git unstage <tiedoston nimi>```\
Jos on hyvä committi, mutta pikkasen huono sitä voi muokata komennolla ```git commit --amend -m "<muutos mitä tullu tehtyä>"

---
# Haarat
Haarat näkyy komennolla ```git branch```\
Uuden haaran saapi tehtyä komennolla ```git branch <haaran nimi>```\
Haarojen välillä voi siirtyä komennolla ```git checkout <haaran nimi>``` taikka komennolla ```git switch <haaran nimi>```\
Tiedoston voi palauttaa aiempaan committii ```git checkout --<tiedoston nimi>```\
Haaran voi poistaa komennolla ```git branch -d <haaran nimi>```


```mermaid
gitGraph
  commit
  commit
  branch AleksinHaara
  checkout AleksinHaara
  commit
  checkout main
  branch AnssinHaara
  commit
  checkout AleksinHaara
  commit
  checkout main
  merge AleksinHaara
  commit
  checkout AnssinHaara
  commit
  checkout main
  merge AnssinHaara
  commit
```
---

  <img src="sanna_marin_committaa_gittiin.jpg" width="600" />
  
# GitHubista vetely
Eka lisätään se pilvihaara komennolla ```git remote add <nimi> >github repositoryn url linkki>```\
Jos nimesit päähaaran vaikka masteriks tai muuten vaan haluut uudelleen nimetä haaran se tehdään ```git branch -m <haaran nimi> <uusi nimi>```\
Ne remote repository linkit näkee tällä ```git remote -v```

Jos haluu vilkaasta onko omat haarukset ajantasalla sen voi tehdä komennolla ```git fetch```\
Sitten vaan imaasoo viimestä huutoa olevat tiedostot ```git pull```

Lonkeroolla syncciä ja se oli sitten siinä
