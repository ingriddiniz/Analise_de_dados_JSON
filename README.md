# Analise_de_dados_JSON
Análise de Dados JSON
O ficheiro [mammals.json](../scripts/projeto2/dados/mammals.json) possui uma listagem da taxonomia de todos os mamíferos registado na base de dados [ENSEMBL](http://www.ensembl.org/index.html).
Este ficheiro foi extraído a partir da API [seguinte](https://rest.ensembl.org/documentation/info/taxonomy_id) que permite consultar individualmente elementos da taxonomia. Também pode explorar a taxonomia no [site do NCBI](https://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi).

A intuição é que a taxonomia forma uma árvore: espécies concretas (como humanos) são folhas; nodos intermédios da árvore são sub-categorias na hierarquia de mamíferos. 

Foram escritos programas Python que respondem às seguintes questões:

* Quantas espécies de mamíferos (folhas da árvore) estão registadas?
A função `totalEspecies`, retorna um número inteiro.
* Qual é o parente mais próximo entre duas espécies?
A função `parenteMaisProximo`, recebe o nome de duas espécies, por exemplo homens (*Homo sapiens*) e macacos japoneses (*Macaca fuscata*), e retorna o nome científico da categoria respetiva.
* Complete a definição da função `desenhaGatos` que representa um diagrama circular da taxonomia da família dos gatos (*Felidae*), como a seguinte imagem

  Para isso, vamos utilizar a ferramenta [Graphviz](https://graphviz.org/) que gera diagramas a partir de ficheiros de texto no formato [DOT](https://graphviz.org/docs/layouts/dot/). Adapte o seguinte template, em que uma categoria `n1` com nome `label1` é a raiz da árvore, e três nodos `n2`, `n3` e `n4` são filhos da raiz.

```
graph G {
  layout=twopi
  ranksep=4;
  ratio=auto;
  
  n1 [root=True,label="label1",shape=plaintext]
  n1 -- { n2 n3 n4 }

}
```

Pode inspecionar o template de exemplo em visualizadores online como [este](https://edotor.net/). A função `desenhaGatos` deve gerar um ficheiro `gatos.dot`. A formatação (cores, tamanhos, formas, imagens, etc) do diagrama fica à escolha dos alunos; para isso, pode consultar a [documentação](https://graphviz.org/documentation/) do Graphviz. O resultado não tem que ser um diagrama igual ao demonstrado em cima, mas para obter nota máxima nesta alínea deve utilizar alguns elementos de formatação diferentes.
