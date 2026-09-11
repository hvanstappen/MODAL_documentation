# Overzicht
Onderstaande tabel geef teen overzicht van de modellen die werden getest op MODAL, en de analayses waarvoor ze geschikt zijn. Let bij het kiezen van een model op de grootte, Een vuistregel is dat de omvang van het model best kleiner is dan je GPU (als je die gebruikt). Hoe groter het model, hoe trager de verwerking ove rhet algemeen verloopt. Als je een te groot model gebruikt, bestaat het risico dat je PC vastloopt.

Voor elke analyse geven we een score:

| score    | beoordeling                     |
|:---------|:--------------------------------|
| ★★★★★    | uitstekend                      |
| ★★★★     | goed                            |
| ★★★      | geschikt, maar maar met fouten  |
| ★★       | bruikbaar, maar met veel fouten |
| -        | niet geschikt / geen resultaten |

In de detailbeschrijvingen vind je ook de link naar de Ollama-modellenpagina

# Overzichtstabel

| Model naam                            | NER | Summary | Topic | Grootte |
|---------------------------------------|:---:|:-------:|:-----:|--------:|
| [gemma3:270m](#gemma3:270m)           |  -  |    ★    |  ★★   |  0.3 GB |
| [gemma3:1b](#gemma3:1b)               | ★★  |   ★★★   | ★★★★  |    1 GB |
| [nl_core_news_lg](#nl_core_news_lg)   | ★★  |    -    |   -   |  1.2 GB |
| [deepseek-r1:1.5b](#deepseek-r1:1.5b) |  -  |    -    |  ★★   |  1.1 GB |
| [qwen2.5:3b](#qwen2.5:3b)             | ★★★ |  ★★★★   | ★★★★  |  1.9 GB |


# Modellen

## <a id="gemma3:270m"></a>gemma3:270m
Het kleinste model van de Gemma3-familie. Het is beperkt bruikbaar voor Samenvattingen of Topic detection.  
[Ollama](https://ollama.com/library/gemma3:270m)

## <a id="gemma3:1b"></a>gemma3:1b
Gemma3:1b maakt deel uit van de Gemma lichtgewicht modelreeks van Google. De Gemma 3-modellen zijn multimodaal – ze verwerken zowel tekst als afbeeldingen – en ondersteunen meer dan 140 talen. Ze zijn blinken uit in taken zoals vraagbeantwoording, samenvatting en redenering, terwijl hun compacte ontwerp implementatie mogelijk maakt op apparaten met beperkte resources.  
[Ollama]()

### Beoordelingen 

#### Samenvatting
- _Sterk wisselende kwaliteit. Samenvatting op mapniveau zeer vaak niet bruikbaar_
- _Het is voor een deel wel accuraat. Maar het gaat altijd voorbij aan de essentie. Bv. een programma van een studiedag over natuurbeheer. De summary identificeert correct dat het document over natuurbeheer gaat, maar niet dat het over een programma van een studiedag gaat._
- _verzonnen woorden, verzonnen feiten en het lijkt alsof er meerdere documenten in het archief zitten, in realiteit was er slechts 1 heel kort document (mogelijke medeverklaring van  hallucinaties?)_
- _Voor het geteste archief zijn de samenvattingen goed, zowel op top-level als op de lagere niveaus van de mappenstructuur_
- _Sterk wisselende kwaliteit. Samenvatting op mapniveau zeer vaak niet bruikbaar_

#### Entiteitsherkenning (NER)
- _Enorm veel ruis. Lidwoorden zijn ook entiteiten, zou toch gefilterd kunnen worden. De categorie "overige" is niet erg nuttig._

#### Topic detection
- _af en toe hallucinaties (verzonnen topic WO II), maar dat was bij tekst met zeer slechte ocr_
- _Behoorlijk goed. Voor het geteste archief geven de topics een duidelijk beeld van de inhoud_
_ _Te veel bijvoeglijke naamwoorden geselecteerd, focus op zelfstandige naamwoorden_

## <a id="nl_core_news_lg"></a>nl_core_news_lg
nl_core_news_lg is een Nederlandstalig taalmodel voor spaCy. spaCy is een open-source Python-bibliotheek voor Natural Language Processing (NLP). Het model is bedoeld voor algemene NLP-taken in het Nederlands en ondersteunt onder meer: Named Entity Recognition (NER) – herkennen van entiteiten zoals personen, organisaties, locaties en datums. Het model is echter een algemeen taalmodel.  Gebruik dit model als je snel wil werken en/of geen krachtige hardware hebt.  
[Huggingface](https://huggingface.co/spacy/nl_core_news_lg/tree/main)

### Beoordelingen

#### Entiteitsherkenning

- _veel getallen die als entiteit worden herkend  eventueel varianten samenvoegen (stad oostende, oostende, ostend)  persoon als 'andere' herkend ('154 Saivator Dali')  niet volledig, maar geeft goeie eerste indruk_
- _Volledigheid kan ik niet beoordelen (geen ground truth gemaakt). De juistheid laat te wensen over. Enerzijds worden er wel veel entities juist herkend. Soms staat een entity er om onduidelijke redenen meerdere keren in. Veel entities zijn echter onjuist. Bij de analyse werden naast correcte entities ook antwoorden gegeven zoals "navbutton-home-hovered" of ".ms-vb-title" bij personen of "N/427/2002/4" bij locaties_

## <a id="deepseek-r1:1.5b"></a>
deepseek-r1:1.5b is een klein model. In de huidige versie van MODAL levert dit model min of meer bruikbare resultaten op voor Topic detection. het is echter niet geschikt voor NER en geeft slechte resultaten voor Samenvattingen.
[Ollama](https://ollama.com/library/deepseek-r1:1.5b)

## <a id="qwen2.5:3b"></a>qwen2.5:3b
Qwen2.5 models zijn getraind op Alibaba' large-scale dataset
[Ollama](https://ollama.com/library/qwen2.5:3b)