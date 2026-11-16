# Bixiga Delivery — interface refinada

## O que foi melhorado
- Vitrine de delivery com navegação inspirada em padrões de usabilidade de marketplaces: busca, categorias, cards de produto, sacola lateral no desktop e sacola fixa no mobile.
- Layout responsivo: navegação horizontal e cards compactos em celulares; categorias laterais, vitrine em colunas e sacola fixa em desktops.
- Carregamento do cardápio com `AbortController`, estados de carregamento e tratamento de erro.
- Imagens com `loading="lazy"` e `decoding="async"` para reduzir trabalho inicial do navegador.
- Painel administrativo com aba **Aparência e Imagens** para configurar banner, capa, logo e cor principal.
- Campos para URL de imagem em categorias e produtos no gerenciamento do cardápio.
- Metadados de aplicação, viewport móvel, compressão HTTP e remoção do cabeçalho `X-Powered-By`.

## Personalização disponível nesta versão
No painel `/admin`, selecione uma unidade e abra **Aparência e Imagens**:
- Banner principal: URL pública da imagem horizontal.
- Capa do cardápio: URL pública da imagem.
- Logo: URL pública da imagem quadrada.
- Cor principal: seletor de cor.

Na aba **Cardápio**:
- URL da imagem de cada categoria.
- URL da imagem de cada pizza/produto.

As imagens devem estar hospedadas em uma URL pública HTTPS. O formulário não faz upload binário do computador. Para upload direto e armazenamento permanente, integrar Cloudinary ou S3 e proteger a rota de upload com autenticação e autorização.

## Importante sobre o estado do projeto
Esta entrega continua sendo uma **prévia funcional de interface**, pois a base recebida usa `mockStore` em memória. Isso significa que alterações podem desaparecer quando o processo reiniciar ou quando a aplicação for executada em outra instância/serverless. Não use este modo como operação real de delivery ou produção. Antes de publicar para clientes, conectar PostgreSQL/Prisma, implementar autenticação real nas rotas administrativas, persistência de mídia e validação de pedidos/preços no servidor.

## Executar localmente
```bash
npm install
npm run dev
```
Abra `http://localhost:3000` e `/admin` para ver o painel.
