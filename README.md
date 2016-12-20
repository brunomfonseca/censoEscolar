# Censo Escolar 2015


## Visualização da Informação

Fonte dos Dados: [Microdados do INEP](http://download.inep.gov.br/microdados/micro_censo_escolar_2015.zip)

[Clique aqui](https://brunomfonseca.github.io/censoEscolar/) para acessar a visualização criada.


## Resumo do trabalho

Os dados foram importados para database MySQL, de onde foram gerados arquivos JSON através de queries para as seguintes métricas:

% de alunos (por UF e por região):

- com acesso a internet
- sexo
- área urbana x área rural
- com abastecimento de água
- com biblioteca e/ou sala de leitura
- com energia elétrica


O mapa foi obtido através de Shapefile baixado no site *Global Administrative Areas* (<http://gadm.org/>).

Os arquivos no formato Shapefile foram convertidos para TopoJSON através do *mapshaper* (<http://mapshaper.org/>). Para reduzir o tamanho dos arquivos, reduzindo assim o tempo de carregamento da visualização, utilizei o recurso que o mapshaper oferece para simplificação do mapa (usei a técnica padrão indicada pelo site, "Visvalingam / weighted area"). O Shapefile original tinha ~ 10 MB, após utilizar esta técnica o arquivo TopoJSON ficou com menos de 300 KB.

O mapa gerado continha um erro que foi corrigido via edição manual do arquivo TopoJSON - o mapa exibia um pequeno trecho dentro do território de Amazonas como sendo Santa Catarina (!).

A visualização foi escrita utilizando D3.js.


