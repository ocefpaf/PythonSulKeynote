---
title: 20 Mil Léguas Sub-pythonicas
---


# whoami

### Filipe Fernandes
#### ([ocefpaf]((https://github.com/ocefpaf)))

![](images/twitter-github.png)

Oceanógrafo Físico por profissão, programador por acaso, educador por paixão.

<aside class="notes">
Primeira conferência de Python que atendi foi em 2012
</aside>


# O que é oceanografia?

(em 3 slides)

```python
slides = iter([1, 2, 3, 4])
next(slides)
```

>- um curso essencialmente científico com foco primariamente acadêmico;
>- bases em física, química, biologia, e geologia;
>- oceanógraf@s sabem um pouco de tudo, mas nada em profundidade.


# `next(slides)`

O que todos acham que é:

. . .

<img src="images/photo-whale.jpg" style="width:750px">



# `next(slides)`

O que realmente é:

. . .

<img src="images/photo-fundeio-0.jpg" style="width:650px">


# `next(slides)`

Mas nem tudo é trabalho

<img src="images/photo-churrasco.jpg" style="width:650px">


# `next(slides)`

O mercado de trabalho...

. . .

```python
StopIteration
Traceback (most recent call last)
<ipython-input-8-943ae0641b78> in <module>()
----> 1 next(slides)

StopIteration:
```

<aside class="notes">
Academia está saturada
Boom do petróleo e atividades embarcadas passou
Formam 
O profissional precisa se re-inventar
</aside>


# ps aux | grep "work"

![](images/ioos_by_the_numbers_graphic2_feb2017-2.png)


# IOOS/RAs

![](images/IOOS-RAs.jpg)


# ps aux | grep "volunteer work"

<img src="images/logo-software-data-carpentry.png" style="width:550px">

![](images/logo-TheCarpentries.png)


# ps aux != "work"

<img src="images/dirty-dishes.jpg" style="width:750px">

<aside class="notes">
Todos precisamos de um hobby.
Depois de mundo tempo procurando um desisti e fiquei com
a atividade de lavar louças!
</aside>


# ps aux | grep "academia"

<img src="images/logo-CNPq.png" style="width:250px">

<img src="images/logo-anp.png" style="width:250px">

. . .

<img src="images/logo-fapesp.png" style="width:250px">


. . .

<img src="images/logo-fulbright.jpg" style="width:250px">


# if bad_results: break

<img src="images/logo-GSoC-2011.png" style="width:600px">

[climatecode](https://www.google-melange.com/archive/gsoc/2011/orgs/climatecode/projects/ocefpaf.html)


# Evasão da academia

![](images/wesphd.png)


# ps aux | grep "OSS work"

![](images/github-org.png)


# ps aux | grep "OSS work"

![](images/github-org-alt.png)


#

![](images/logo-ipython.png)

>- Apenas uma inspiração para **não** programadores:
>- Projeto inicial era de um oceanógrafo!
>- Fernando Perez é Físico e desenvolveu o projeto durante o doutorado.
>- Minha participação foi pequena: `nbconvert`


#

![](images/logo-scitools.png)

>- Comunidade do UK Met Office no GitHub
>- Todo o trabalho deles é OSS
>- Um exemplo de como um órgão governamental deve agir!

. . .

[https://github.com/SciTools](https://github.com/SciTools)


# Iris

![](images/iris.png)


# Cartopy

![](images/cartopy.png)


#

![](images/logo-TEOS-10.jpg)

>- Começo turbulento
>- Muito academicismo e pouco Software
>- SCOR/IAPSO Working group 127


# 

![](images/borg.jpg)


#

![](images/logo-pyoceans.jpg)

>- Uma organização aberta a toda comunidade oceanográfica que se interessa por programação.
>- A ideia é não ter vínculos com governo, empresas, universidades, etc.
>- Um espaço aberto à todos.


# gridgeo

<img src="images/gridgeo-0.png" style="width:750px">


# gridgeo

<img src="images/gridgeo-1.png" style="width:750px">


# python-ctd

```python
from ctd import DataFrame
cast = DataFrame.from_cnv('g01l06s01.cnv')
downcast, upcast = cast.split()
fix, ax = downcast['t090c'].plot()
```

<img src="images/python-ctd.png" style="width:450px">


# pocean-core

```python
attributes = {
  'global': {
    'title': 'Fake mooring',
    'summary': 'Vector current meter ADCP @ 10 m',
    'institution': 'Restaurant at the end of the universe',
    'cdm_timeseries_variables': 'station',
    'subsetVariables': 'depth',
  },
  'longitude': {
    'units': 'degrees_east',
    'standard_name': 'longitude',
  },
   ...
}
```


# pocean-core

```xml
netcdf fake_buoy {
  dimensions:
  	station = 1 ;
  variables:
  	double longitude(station) ;
  	longitude:axis = "X" ;
  	longitude:units = "degrees_east" ;
  	longitude:standard_name = "longitude" ;
  // global attributes:
  	:Conventions = "CF-1.6" ;
  	:cdm_data_type = "Timeseries" ;
  	:summary = "Vector current meter ADCP @ 10 m" ;
  	:institution = "Restaurant at the end of the universe" ;
    }
```


# erddapy

```python
from erddapy import ERDDAP

constraints = {'time>=': '2016-07-10T00:00:00Z',
               'time<=': '2017-02-10T00:00:00Z',
               'latitude>=': 38.0, 'latitude<=': 41.0,
               'longitude>=': -72.0, 'longitude<=': -69.0,}

variables = ['depth', 'temperature',]

e = ERDDAP(server='https://data.ioos.us/gliders/erddap',
    constraints=constraints,
    variables=variables,
)
```


# erddapy

<img src="images/erddapy.png" style="width:700px">


# folium

<img src="images/folium-tweets.png" style="width:700px">

#

![](images/logo-conda-forge.svg)

>- provavelmente o projeto de maior alcance fora de área de Met/Ocean
>- comunidade com crescimento orgânico e rápido
>- missão: facilitar a instalação de software


# Por que?

![](images/pip_install_gdal.jpg)


# community

![](images/conda-forge-community.png)


# @conda-forge/core

![](images/conda-forge-core.png)


# objetivo

![](images/lotr-one-ring-to-rule-them-all-one-channel-to-rule-them-all-conda-forge.jpg)


#

![](images/logo-ioos.jpg)

>- Segue os moldes do UK Met Office.
>- Gerencia Software, uso das tecnologias, dados, e projetos no GitHub.
>- O objetivo principal é melhorar a passagem do conhecimento através de várias gerências.

# Data Demo Center

<img src="images/IOOS-data-demo-center.png" style="width:650px">


[https://ioos.github.io/notebooks_demos](https://ioos.github.io/notebooks_demos)

# Code Gallery

<img src="images/code-gallery.png" style="width:650px">

# Notebook time!

. . .

<a href="http://nbviewer.jupyter.org/github/ocefpaf/PythonSulKeynote/blob/gh-pages/notebooks/turtles.ipynb"><img src="images/notebook-obis.png" style="width:300px"></a>

. . .

<a href="http://nbviewer.jupyter.org/github/ocefpaf/PythonSulKeynote/blob/gh-pages/notebooks/wave_height_assessment.ipynb"><img src="images/notebook-catalog.png" style="width:300px"></a>


. . .

<a href="http://nbviewer.jupyter.org/github/ocefpaf/PythonSulKeynote/blob/gh-pages/notebooks/gistemp.ipynb"><img src="images/notebook-gistemp.png" style="width:300px"></a>


# Já que o assunto é Ciência

>- Quantos aqui tem um diploma em ciência básica?
>- Quantos não mais praticam essa ciência no dia-a-dia?
>- Quem se (re-)encontrou na área de tecnologia/data science?


# Quem faz ciência?

>- constrói e organiza conhecimento
>- testa explicações sobre o universo:
>- sistematicamente,
>- objetivamente,
- de forma transparente,
>- e reprodutível.


# Ciência conta com:

>- revisão pelos pares
>- ceticismo
>- transparência
>- atribuição
>- prestação de contas
>- colaboração
>- e impacto!


# Exemplo: missão da UFSC

Qualidade, Inovação, Atuação, Inclusão, Internacionalização,
Liberdade e responsabilidade, Autonomia, Democrática e plural,
Otimização administrativa, Transparência, Ética.

<aside class="notes">
Não é nem um pouco diferente do que é atualmente praticado nas comunidades de tecnologia aqui em Floripa.
</aside>


# E "codar" ciência?

<iframe width="711" height="533" src="https://www.youtube.com/embed/ZyjCqQEUa8o?start=1771" frameborder="0" allow="encrypted-media" allowfullscreen></iframe>



# O ponto é

Ciência não é tão diferente assim de programação!


# O que eu, profissional da tecnologia, tenho isso?

<iframe width="711" height="533" src="https://www.youtube.com/embed/kaGS4YXwciQ?start=1294" frameborder="0" allow="encrypted-media" allowfullscreen></iframe>


# Por que devo me importar?

<div class="row">
<div class="column">![](images/Cassino.png)</div>
<div class="column">![](images/length-floripa.png)</div>
</div>

[clique aqui para ver o notebook](http://nbviewer.jupyter.org/gist/ocefpaf/3f1765577d11e0cac3ee905e49936460)


# Colocando a mão na massa!

<img src="images/sla-map.png" style="width:700px">


[http://pangeo.pydata.org](http://pangeo.pydata.org)


# sea-surface-height.ipynb

<img src="images/pangeo-ssh.png" style="width:700px">

# sea-surface-height.ipynb

<img src="images/hovmoller.png" style="width:700px">


# *Scientific Software pledge*

>- Desenvolver Software aberto desde o início, sempre que possível.
>- Contribuir para a sustentabilidade do Software que uso e dependo.
>- Aplicar práticas propostas de engenharia de software de acordo com as necessidades e recursos reais do projeto.

# *Scientific Software pledge..*

>- Ajudar os pesquisadores a melhorar a qualidade do seu software sem julgar.
>- Publicar as contribuições intelectuais do meu software de pesquisa.
>- Documentar (incluindo instruções de uso e exemplos de entrada e saída), pacotes, *releases*, e versões arquivadas do meu software.


# Perguntas?

![](images/disco.gif)