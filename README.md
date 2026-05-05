# Aplicação de Streaming de Música e Vídeo para Criação de Playlists

## Visão Geral

Desenvolvemos uma aplicação de **streaming de músicas e vídeos** com foco principal na **criação, organização e reprodução de playlists**.

A ideia é funcionar de forma semelhante ao **Music.app da Apple**, porém com funcionalidades extras voltadas para facilitar a criação de playlists específicas, especialmente para uso em rituais, encontros, práticas, aulas ou momentos guiados.

O objetivo é permitir que **diferentes tipos de conteúdos** — músicas, áudios e vídeos — sejam organizados em uma mesma experiência, mesmo quando esses conteúdos vêm de fontes diferentes ou não estão disponíveis em plataformas tradicionais.

## Objetivo Principal

A aplicação foi pensada para facilitar a **criação de playlists personalizadas**, permitindo que o usuário:

- Organize músicas, áudios e vídeos
- Monte playlists para momentos específicos
- Encontre rapidamente conteúdos já existentes no servidor
- Edite informações das mídias
- Evite duplicação de arquivos no armazenamento
- Use conteúdos vindos de diferentes fontes
- Personalize trechos de reprodução, como início e fim de músicas ou vídeos
## Funcionalidades Principais

### 1. Criação e Organização de Playlists

O usuário poderá criar playlists com músicas, vídeos ou áudios já existentes no servidor.

A mesma música poderá estar presente em várias playlists sem que o arquivo precise ser duplicado fisicamente no servidor.

Isso ajuda a **economizar armazenamento** e manter uma biblioteca mais organizada.

### 2. Biblioteca Centralizada de Músicas e Vídeos

Os arquivos ficarão armazenados em um servidor, organizados por uma estrutura padrão de pastas:

```
/Nome do Artista ou Banda/Álbum/Música
```

**Exemplo:**

```
/Coldplay/A Rush of Blood to the Head/The Scientist.mp3
```

Quando uma música ou álbum não tiver metadados identificados, ela poderá aparecer com nomes genéricos, como:

```
/Unknown Artist/Unknown Album/Nome da Música
```

Essa estrutura pode variar dependendo das informações disponíveis. Por exemplo:

```
/Unknown Artist/Álbum Conhecido/Música
```

ou:

```
/Artista Conhecido/Unknown Album/Música
```

### 3. Evitar Duplicação de Arquivos

A estrutura do sistema foi pensada para **impedir que a mesma música seja salva várias vezes** no servidor.

Como uma mesma música pode fazer parte de várias playlists, o ideal é que exista apenas um arquivo original armazenado, e as playlists apenas façam referência a esse arquivo.

Isso evita:

- Consumo desnecessário de armazenamento
- Múltiplas cópias da mesma música
- Dificuldade de organização
- Inconsistências entre versões duplicadas

### 4. Edição de Metadados

A aplicação permitirá **editar os principais metadados** das músicas, vídeos e áudios.

Exemplos de metadados editáveis:

- Nome da música
- Artista ou banda
- Álbum
- Gênero
- Ano
- Capa do álbum
- Imagem personalizada
- Informações adicionais relevantes

Essa funcionalidade é importante para melhorar a busca, a organização visual e a experiência de navegação dentro da aplicação.

### 5. Edição de Início e Fim de Músicas ou Vídeos

A aplicação terá a funcionalidade de **cortar ou ajustar o ponto inicial e final** de uma música, áudio ou vídeo.

Por exemplo, alguns vídeos do YouTube começam com pedidos para seguir o canal, curtir o vídeo ou assistir uma introdução longa. Nesse caso, será possível configurar a mídia para começar diretamente no ponto desejado, indo direto ao conteúdo principal.

**Exemplo:**

- Vídeo original: começa em `0:00`
- Reprodução na playlist: começa em `1:35`

Também será possível definir um ponto final, caso o conteúdo tenha encerramentos, propagandas, falas finais ou partes que não sejam necessárias para o uso pretendido.

## Integrações Externas

A aplicação utiliza alguns **serviços e bibliotecas externas** para oferecer determinadas funcionalidades.

### 1. API da Apple

A API da Apple pode ser utilizada para **buscar metadados das músicas**, como:

- Nome do álbum
- Nome do artista
- Capa
- Informações da faixa
- Dados relacionados ao conteúdo musical

Isso ajuda a preencher automaticamente informações que estejam ausentes ou incompletas.

### 2. Biblioteca yt-dlp

A aplicação também utiliza uma biblioteca da comunidade chamada **yt-dlp**, usada para trabalhar com vídeos e áudios de plataformas como o YouTube.

Como essa biblioteca é mantida pela comunidade e depende do funcionamento de plataformas externas, é importante deixar claro que essa funcionalidade pode sofrer impactos no futuro.

**Possíveis problemas:**

- Mudanças no YouTube
- Restrições de uso
- Alterações na biblioteca
- Limites de acesso
- Bloqueios temporários
- Necessidade de atualização técnica
- Perda temporária ou permanente de alguma funcionalidade

Caso isso aconteça, será necessário avaliar alternativas ou ajustar a aplicação.

## Limitações e Riscos Técnicos

Como algumas funcionalidades dependem de **serviços externos gratuitos** ou **bibliotecas mantidas por terceiros**, existem riscos que precisam ser considerados.

### Possíveis Limitações

- APIs gratuitas podem ter limites de requisições
- Algumas plataformas podem mudar suas regras
- Bibliotecas externas podem parar de funcionar
- Determinados recursos podem exigir manutenção constante
- Algumas funcionalidades podem ficar indisponíveis temporariamente
- O comportamento pode variar de acordo com rede, IP, sistema operacional ou atualizações externas

### Exemplo de Impacto

Se uma plataforma alterar a forma como os vídeos são disponibilizados, uma funcionalidade de download ou importação pode parar de funcionar até que seja corrigida.

Nesses casos, as opções seriam:

- Atualizar a biblioteca utilizada
- Alterar a integração
- Buscar uma alternativa técnica
- Remover ou limitar determinada funcionalidade
- Deixar a funcionalidade temporariamente indisponível

### Limites de Uso das APIs Externas

Algumas APIs gratuitas podem **limitar o número de requisições** feitas em determinado período.

Esses limites geralmente podem estar relacionados a:

- IP da rede
- Conta de desenvolvedor
- Chave de API
- Volume de requisições
- Frequência de uso
- Regras da própria plataforma

Quando isso acontecer, o ideal é aguardar o limite ser liberado ou revisar a forma como a aplicação está usando essas APIs, para evitar excesso de chamadas desnecessárias.

## Ideias Futuras

### 1. Importar Playlists do Spotify

Uma funcionalidade interessante seria permitir que o usuário **cole o link de uma playlist do Spotify**.

A aplicação poderia então ler a playlist e importar ao menos a referência das músicas.

Como baixar músicas diretamente do Spotify é bem mais complicado e possui restrições, a ideia não seria necessariamente baixar o conteúdo automaticamente.

Em vez disso, o app poderia:

- Importar o nome das músicas
- Importar artistas
- Importar álbuns
- Verificar se a música já existe no servidor
- Marcar músicas pendentes
- Permitir adicionar links do YouTube manualmente
- Sugerir buscas automáticas
- Montar uma playlist-base para ser completada depois

**Exemplo de fluxo:**

1. Usuário cola o link da playlist do Spotify
2. O app lê a lista de músicas
3. O app verifica quais já existem no servidor
4. As músicas encontradas são vinculadas automaticamente
5. As músicas ausentes ficam como pendentes
6. O usuário adiciona manualmente ou busca uma fonte alternativa
## Benefícios da Aplicação

A aplicação oferece **benefícios importantes** para quem precisa organizar músicas, vídeos e áudios em playlists personalizadas.

**Principais benefícios:**

- Centralização dos conteúdos
- Organização por artista, álbum e música
- Economia de armazenamento
- Reutilização da mesma mídia em várias playlists
- Edição de metadados
- Melhor busca interna
- Possibilidade de personalizar trechos de reprodução
- Suporte a conteúdos que não existem em plataformas tradicionais
- Flexibilidade para criar playlists específicas para cada uso
- Possibilidade de importar referências de outras plataformas no futuro

## Pontos Importantes para os Usuários

É importante que os usuários saibam que **algumas funcionalidades dependem de serviços externos**.

Por isso, determinadas partes da aplicação podem não funcionar sempre da mesma forma.

Especialmente recursos ligados a:

- YouTube
- Spotify
- Apple Music / Apple API
- Bibliotecas externas
- APIs gratuitas
- Serviços de terceiros

Se alguma dessas plataformas mudar suas regras, limitar o uso ou alterar a forma de acesso, algumas funcionalidades da aplicação podem precisar de **ajustes técnicos**.
