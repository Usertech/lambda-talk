title: AWS Lambda - Serverless architektura
author:
  name: Lukáš Rychtecký
  twitter: lukasrychtecky
controls: true
style: style.css

--

# AWS Lambda - Serverless architektura
## Lukáš Rychtecký
## [https://twitter.com/LukasRychtecky](https://twitter.com/LukasRychtecky)

--

### Osnova

* Co je to serverless?
* AWS Lambda
* Výhody a nevýhody
* Hello world ukázka
* Pokročilá ukázka s balíčky

--

### Co je to serverless?

Je to architektura systému, ve kterém jsou jednotlivé části systému využívány jako služba třetích stran.

* např. DB je připojena pouze přes DB link a víc o ní nevíme (nestáráme se o škálování, monitoring apod.)
* autentizace a autorizace (AWS IAM), nestaráme se o access, pouze definujeme pravidla

--

### Co je to serverless?

<img src="http://martinfowler.com/bliki/images/serverless/sketch.png" width="600px">

--

### Serverless - Výhody

* rychlejší kick-off projektu
* nestaráte se (přímo) o škálování, zálohování, monitoring apod.
* lepší škálovatelnost jednotlivých komponent

--

### Serverless - Nevýhody

* orchestrace systému (mnoho malých komponent)
* složitější nastavení dev. prostředí
* vendor lock-in na konkrétní produkty

--

### AWS Lambda

Je to služba, která spustí zdrojový kód na základě události.

* Function as a Service
* "jenom" nahrajete zdrojový kód
* platíte pouze za compute time
* lambdu lze spustit na základě HTTP requestu, vložení záznamu do DB apod.
* funguje to jako funkce, dostane data na vstupu, provede výpočet a vrátí jiná data

--

### AWS Lambda - Jazyky


* Python 2.7
* Node.js 4.3
* Java 8

--

### AWS Lambda - Use case

![](http://docs.aws.amazon.com/lambda/latest/dg/images/push-s3-example-10.png)

--

### AWS Lambda - Výhody

* nestaráte se o server
* platí se pouze compute time
* skoro neomezené škálování
* snadný deployment
* snadné zpracování asynchronních úkolů

--

### AWS Lambda - Nevýhody

* overhead na spuštění lambdy (největší asi u JVM)
* omezení doby výpočtu na 5 min.
* omezení velikosti zdrojového kódu, max. 50 MB
* všechny knihovny musí být v uplodovaném zipu
* více [http://docs.aws.amazon.com/lambda/latest/dg/limits.html](http://docs.aws.amazon.com/lambda/latest/dg/limits.html)

--

### Hello world ukázka

```python
# event = {'a': 1, 'b': 2}
def lambda_handler(event, context):
    return {'keys': event.keys()}

# ['a', 'b']
```

* `lambda_handler` je entry point (jako `main` u C)
* `event` událost, která spustila lambdu
* `context` meta obsahuje informace jméno, prostředí (dev, prod), ...

--

### Hello world ukázka - Konfigurace

![](http://new.tinygrab.com/75723fac28d8a7f8f39c17daa4a5b2c73422840d03.png)

--

### Hello world ukázka - Konfigurace triggeru

![](http://new.tinygrab.com/75723fac2879bc10d14d532330ba79700568fb10a4.png)

--


### Pokročilá ukázka s balíčky

[https://github.com/LukasRychtecky/aws-lambda-python-example](https://github.com/LukasRychtecky/aws-lambda-python-example)

--

### Thanks for your attention

* [http://martinfowler.com/bliki/Serverless.html](http://martinfowler.com/bliki/Serverless.html)
* [http://docs.aws.amazon.com/lambda/latest/dg/welcome.html](http://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
* [https://aws.amazon.com/lambda/details/](https://aws.amazon.com/lambda/details/)
