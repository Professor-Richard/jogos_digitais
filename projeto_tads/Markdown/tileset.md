Tutorial de Tilemaps no Godot 4.0

Tilemaps para criar cenários de jogos 2D.
1. Configurando o Nó TileMap

    Em sua cena 2D, adicione um novo nó filho clicando com o botão direito e procurando por "TileMap".

    Renomeie o nó (por exemplo, "Nível") e posicione-o na árvore de cena, geralmente antes do nó do jogador para que ele seja renderizado por baixo.

2. Entendendo a Interface do TileMap

    Com o nó TileMap selecionado, você verá três novas abas: "Tiles", "Patterns" e "Layers".

    Ao lado dessas abas estão as ferramentas de desenho: lápis (desenhar), linha, retângulo, balde de tinta, conta-gotas (selecionar tipo de tile) e borracha.

3. Criando um TileSet

    Ao contrário das versões anteriores do Godot, você cria TileSets diretamente na aba "TileSet" na parte inferior do editor (ao lado da aba "TileMap").

    Clique no botão "+" e escolha "AtlasTexture" ou, de forma mais simples, arraste sua imagem de tile (por exemplo, uma folha de sprite PNG) do dock FileSystem para o painel TileSet.

    O Godot perguntará se você quer criar automaticamente os tiles do atlas; diga "Sim".

4. Desenhando com Tiles

    Volte para a aba "TileMap".

    Selecione o tile desejado no painel TileSet.

    Use as ferramentas de desenho:

        Lápis: Clique para colocar um único tile.

        Clique esquerdo: Desenhar.

        Clique direito: Apagar.

        Shift + Clique esquerdo: Desenhar uma linha.

        Shift + Clique direito: Apagar uma linha.

        Shift + Ctrl + Clique esquerdo: Desenhar um retângulo.

        Shift + Ctrl + Clique direito: Apagar uma seleção retangular.

        Ferramenta Retângulo: Clique e arraste para desenhar um retângulo preenchido com o tile selecionado.

        Borracha: Clique para apagar os tiles.

5. Trabalhando com Camadas (Layers)

    As camadas permitem organizar diferentes elementos do seu tilemap (por exemplo, chão, decorações, elementos em primeiro plano) sem precisar de múltiplos nós TileMap.

    No Inspector, em "Propriedades do TileMap", encontre a seção "Layers".

    Renomeie a camada padrão (por exemplo, "Chão").

    Clique no botão "+" para adicionar novas camadas (por exemplo, "Árvores", "Decorações").

    Você pode selecionar em qual camada está desenhando no menu suspenso no painel de edição do TileMap.

    Objetos em camadas mais altas serão renderizados por cima dos objetos em camadas mais baixas. Você pode alternar a visibilidade da camada usando o ícone de "olho" ao lado de cada nome de camada.

6. Editando Definições de Tiles (na aba TileSet)

    Às vezes, a criação automática de tiles não é perfeita, especialmente para objetos maiores como árvores.

    Vá para a aba "TileSet" na parte inferior.

    Apagando Tiles: Selecione os tiles indesejados e clique com o botão direito -> "Excluir".

    Modificando Regiões de Tiles:

        Selecione um tile. Você verá alças vermelhas.

        Arraste essas alças para ajustar a região que o tile cobre no atlas. Isso é útil para combinar vários tiles pequenos em um único tile selecionável maior.

    Criando Novos Tiles Manualmente: Se você apagar um tile e precisar dele de volta, ou quiser definir uma região de tile personalizada:

        Clique com o botão direito em uma área vazia do seu atlas -> "Criar Tile".

        Como alternativa, vá para a sub-aba "Setup" dentro do painel TileSet, selecione a região que você quer para o novo tile e clique em "Aplicar".

7. Usando Padrões (Patterns)

    A aba "Patterns" permite salvar e reutilizar rapidamente arranjos de tiles.

    Na aba "TileMap", selecione um grupo de tiles que você já colocou no seu mapa.

    Arraste esta seleção do seu mapa para o painel "Patterns".

    Agora, você pode selecionar este padrão salvo e clicar no seu mapa para colocar todo o arranjo de uma vez.

8. Adicionando Colisões

    Vá para a aba "TileSet".

    No painel que lista seus atlases, clique no atlas que contém os tiles para os quais você quer adicionar colisão. Isso expandirá um novo conjunto de opções abaixo dele.

    Selecione a seção "Physics Layers".

    Clique em "Adicionar Elemento" para criar uma nova camada de física para seus tiles.

    Agora, mude para o modo "Selecionar" dentro do painel TileSet (se ainda não estiver selecionado).

    Selecione um ou vários tiles no seu atlas.

    Nas propriedades de "Physics" que aparecem (geralmente no lado direito do painel TileSet), você pode definir a forma da colisão:

        Desenho Manual: Clique em pontos para desenhar uma forma de polígono.

        Colisão Automática de Tile Completo: Selecione o(s) tile(s) e pressione 'F'. Isso criará uma forma de colisão que preenche o tile inteiro.

        Limpar Colisão: Selecione o(s) tile(s) e pressione 'C' para remover a forma de colisão.

9. Colisões de Sentido Único (Plataformas)

    Para tiles que devem funcionar como plataformas (o jogador pode pular por baixo, mas aterrissar em cima):

        Selecione o nó TileMap.

        Vá para a aba "TileSet".

        Selecione a camada de física que você criou.

        Nas propriedades dessa camada de física (no Inspector ou na seção do painel TileSet), encontre as propriedades de "Polygon".

        Habilite "One Way Collision" (Colisão de Sentido Único).

        Você verá setas nas suas formas de colisão no editor do TileSet indicando a direção em que é possível passar.

10. Posicionamento Aleatório de Tiles

    Este recurso é útil para fazer grandes áreas parecerem mais variadas sem precisar colocar cada tile manualmente.

    Na aba "TileMap", selecione várias variações de um tipo de tile (por exemplo, diferentes tiles de grama) do seu TileSet.

    Clique no ícone de "dado" nas ferramentas de desenho.

    Agora, quando você desenhar com o lápis ou outras ferramentas, o Godot escolherá aleatoriamente entre os tiles selecionados para colocar, criando uma aparência mais orgânica.

        Você pode ajustar o valor de "scatter" (por exemplo, 0.2) para controlar a frequência com que ele troca de tiles. Um valor de 0 significa que ele tentará variar mais frequentemente dentro do intervalo selecionado.

11. Propriedades do TileSet

    Estas propriedades aparecem no Inspector quando o TileSet é selecionado no FileSystem.

        Tamanho do Tile (Tile Size): Certifique-se de que isso corresponda ao tamanho dos seus tiles individuais na sua folha de sprite (por exemplo, 16x16 pixels).

        Forma do Tile (Tile Shape): Geralmente "Square" (Quadrado), mas existem outras opções para tiles isométricos ou hexagonais.