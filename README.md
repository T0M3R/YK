# YK Studio — Galeria

Site estático preparado para GitHub Pages e edição de obras pelo Pages CMS.

## O que está incluído

- `index.html`: site original. O CSS, a estrutura visual e o design foram preservados; a única adaptação é a leitura do catálogo e das imagens editáveis.
- `content/artworks.json`: catálogo das 12 obras iniciais, com títulos PT/EN, técnica, dimensões, categoria, descrições e preços.
- `.pages.yml`: configuração do Pages CMS para editar obras, preços e imagens.
- `media/`: pasta de destino para imagens enviadas pelo CMS.
- `.github/workflows/pages.yml`: publicação automática no GitHub Pages.
- `.nojekyll`: evita processamento Jekyll automático.

## 1. Publicar no GitHub Pages

1. Crie um repositório no GitHub.
2. Envie **todo o conteúdo desta pasta ZIP** para a raiz do repositório (não envie a pasta externa que contém os arquivos).
3. No GitHub, abra **Settings → Pages**.
4. Em **Build and deployment**, selecione **GitHub Actions**.
5. A publicação será iniciada automaticamente pelo workflow `Deploy to GitHub Pages`.
6. Aguarde o workflow terminar e abra o endereço mostrado em **Settings → Pages**.

## 2. Conectar ao Pages CMS

1. Acesse [Pages CMS](https://app.pagescms.org/) e entre com sua conta GitHub.
2. Autorize o Pages CMS a acessar o repositório onde publicou o site.
3. Selecione o repositório e a branch de publicação (normalmente `main`).
4. O Pages CMS detectará o arquivo `.pages.yml`.
5. Abra **Obras da galeria** para editar as obras.

## 3. Alterar obras, preços e imagens

Dentro de **Obras da galeria**:

- Edite títulos em português e inglês.
- Atualize ano, técnica, dimensões, orientação e categoria.
- Altere `Preço em reais (R$)` e `Preço em dólares (US$)`.
- Envie uma imagem em **Imagem da obra**. O arquivo será salvo em `media/` e o site passará a usá-lo nas miniaturas, galeria, detalhes e lightbox.
- Atualize as descrições em português e inglês.
- Salve as alterações. O Pages CMS grava as mudanças no GitHub; o workflow publica a nova versão automaticamente.

**Importante sobre preços:** informe apenas números, por exemplo `4200` e `840`. O site formata os valores automaticamente como `R$ 4.200` e `$840`, e os cálculos de preço/parcelamento usam os campos numéricos.

**Importante sobre imagens:** se o campo de imagem ficar vazio, o site mantém o comportamento ilustrativo original baseado em `picsum.photos`. Para o portfólio real, substitua essas imagens pelas fotografias/arquivos definitivos das obras.

## 4. Adicionar ou remover obras

A lista inteira fica em `content/artworks.json`. Pelo Pages CMS, use os controles da lista **Obras** para adicionar, reordenar ou remover itens. Preserve os campos `title`, `medium`, `story`, `priceBRL` e `priceUSD` no formato apresentado.

## 5. Observações

- Não há banco de dados, servidor pago ou chave de API.
- Pages CMS grava os arquivos diretamente no GitHub; GitHub Pages hospeda o site.
- O site busca `content/artworks.json` usando caminho relativo, funcionando também em repositórios GitHub Pages de projeto (`usuario.github.io/nome-do-repositorio/`).
- O catálogo embutido no HTML funciona como fallback se o JSON não puder ser carregado.
- O arquivo HTML conserva o layout, cores, tipografia, animações e componentes originais. A adaptação de CMS não redesenha a interface.
