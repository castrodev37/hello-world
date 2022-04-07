# hello-world
Inicial studies

Graduação: UCAM - Análise e Desenvolvimento de Sistemas

Período: 2º

Gestor de equipes há 10 anos, como supervisor e coordenador, no ramo de call center e logística, resetando profissionalmente pela paixão em programar

Add: pull request and commit

* [Listar Preços Dinamicamente](#Listar-Preços-Dinamicamente)
* [Calcular Preço do Item da Lista](#Calcular-Preço-do-Item-da-Lista)
* [Incluir Variável Preço de Custo](#Incluir-Variável-Preço-de-Custo)
* [Exibir Preço Final](#Exibir-Preço-Final)


Usar links na documentação
Artigo
02/04/2022
11 minutos para o fim da leitura


Este artigo descreve como usar hiperlinks de páginas hospedadas em docs.microsoft.com. É fácil adicionar links em markdown com poucas variações de convenções. Os links direcionam os usuários para o conteúdo na mesma página, em páginas vizinhas ou em sites e URLs externos.

O back-end do site docs.microsoft.com usa o OPS (Open Publishing Services), que é compatível com o markdown em conformidade com CommonMark analisado pelo mecanismo de análise Markdig. Essa variante de markdown é compatível principalmente com o GitHub Flavored Markdown (GFM), já que a maioria dos documentos são armazenados no GitHub e podem ser editados lá. Mais funcionalidades são adicionadas pelas extensões de Markdown.

 Importante

Todos os links devem ser protegidos (https e não http) quando o destino tiver suporte para eles (a grande maioria tem).

Texto do link
As palavras que você inclui no texto do link devem ser amigáveis. Em outras palavras, devem ser palavras normais em português ou o título da página que o link abre.

 Importante

Não use "clique aqui". É ruim para a otimização do mecanismo de pesquisa e não descreve adequadamente o destino.

Correto:

For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).

For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://docs.microsoft.com/sql/t-sql/statements/set-transaction-isolation-level-transact-sql) reference.

Incorreto:

For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).

For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).

Links de um artigo para outro
Há dois tipos de hiperlinks com suporte no sistema de publicação: Links de URLs e links de arquivo.

Um link de URL pode ser um caminho de URL relativo à raiz de docs.microsoft.com ou uma URL absoluta que inclui a sintaxe de URL completa (por exemplo, https://github.com/MicrosoftDocs/PowerShell-Docs).

Use links de URL ao vincular o conteúdo fora do conjunto de documentos atual ou entre a referência gerada automaticamente e os artigos conceituais dentro do conjunto de documentos.
A maneira mais simples de criar um link relativo é copiar a URL do navegador e, em seguida, remover https://docs.microsoft.com/en-us do valor que você colar no markdown.
Não inclua localidades em URLs para as propriedades da Microsoft (por exemplo, remova "/en-us" da URL).
Um link de arquivo é usado para vincular de um artigo a outro dentro do conjunto de documentos.

Todos os caminhos de arquivo usam caracteres de barra (/) em vez de caracteres de barra invertida.

Um artigo é vinculado a outro artigo no mesmo diretório:

[link text](article-name.md)

Um artigo é vinculado a um artigo no diretório pai do diretório atual:

[link text](../article-name.md)

Um artigo é vinculado a um artigo no subdiretório do diretório atual:

[link text](directory/article-name.md)

Um artigo é vinculado a um artigo em um subdiretório do diretório pai do diretório atual:

[link text](../directory/article-name.md)

 Observação

Nenhum dos exemplos anteriores usa ~/ como parte do link. Para vincular a um caminho absoluto que começa na raiz do repositório, inicie o link com /. A inclusão de ~/ gera links inválidos ao navegar pelos repositórios de origem no GitHub. Iniciar o caminho com / resolve este problema corretamente.

Estrutura de links em docs.microsoft.com
O conteúdo publicado em docs.microsoft.com tem a seguinte estrutura de URL:


Copiar
https://docs.microsoft.com/<locale>/<product-service>/[<feature-service>]/[<subfolder>]/<topic>[?view=<view-name>]
Exemplos:


Copiar
https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-overview
https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-5.1.1
<locale> – identifica o idioma do artigo (exemplo: en-us ou de-de)
<product-service> – o nome do produto ou serviço (exemplo: powershell, dotnet ou azure)
[<feature-service>] – (opcional) o nome do recurso ou subserviço do produto (exemplo: csharp ou balanceador de carga)
[<subfolder>] – (opcional) o nome de uma subpasta em um recurso
<topic> – o nome do arquivo de artigo para o tópico (exemplo: load-balancer-overview ou visão geral)
[?view=\<view-name>] – (opcional) o nome da exibição usado pelo seletor de versão para o conteúdo que tem várias versões disponíveis (exemplo: azps-3.5.0)
 Dica

Na maioria dos casos, os artigos no mesmo conjunto de documentos têm o mesmo fragmento de URL . Por exemplo:

Mesmo conjunto de documentos
https://docs.microsoft.com/dotnet/core/get-started
https://docs.microsoft.com/dotnet/framework/install
Conjuntos de documentos diferentes
https://docs.microsoft.com/dotnet/core/get-started
https://docs.microsoft.com/visualstudio/whats-new
Links com indicadores
Para um link de indicador que direciona a um título no arquivo atual, use um símbolo de hash seguido pelas palavras minúsculas do título. Remova a pontuação do título e substitua espaços por traços:

markdown

Copiar
[Managed Disks](#managed-disks)
Para vincular a um título de indicador em outro artigo, use o link relativo ao arquivo ou relativo ao site além de um símbolo de hash, seguido pelas palavras do título. Remova a pontuação do título e substitua espaços por traços:

markdown

Copiar
[Managed Disks](../../linux/overview.md#managed-disks)
Você também pode copiar o link do indicador da URL. Para localizar a URL, passe o mouse sobre a linha do título em docs.microsoft.com. Você verá um ícone de link ser exibido:

Link icon in article heading

Clique no ícone de link e copie o texto de âncora do indicador da URL (ou seja, a parte após o hash).

 Observação

A Extensão do Docs também tem ferramentas para ajudar a criar links.

Links do tipo âncora explícitos
Adicionar links do tipo âncora explícitos que usam a marca HTML <a> não é obrigatório nem recomendado, exceto nas páginas de hub e de aterrissagem. Em vez disso, use os indicadores gerados automaticamente conforme descrito nos links do indicador. Para páginas de hub e de aterrissagem, declare as âncoras desta forma:


#Listar Preços Dinamicamente
bla, bla
