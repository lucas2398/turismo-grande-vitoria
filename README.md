# 🌎 Turismo na Grande Vitória

Site de curadoria pessoal de pontos turísticos, restaurantes e experiências na região da Grande Vitória — ES. O projeto nasceu da vontade de reunir num só lugar os lugares que eu conheço e recomendo, com uma experiência de uso que vai além de uma lista estática.

🔗 **[Ver o site ao vivo](#)** ← substitua pelo link do GitHub Pages quando ativar

---

## Funcionalidades

- **Pontos turísticos** com mapa integrado, links para sites oficiais e informações de acesso
- **Restaurantes e cafés** organizados por cidade
- **Página Explorar** — busca cruzada entre pontos turísticos e restaurantes: filtre por cidade ou clique num ponto turístico para ver o que tem por perto
- **Favoritos** — marque seus locais preferidos; ficam salvos no navegador
- **Visitados** — marque o que você já conheceu
- **Ignorados** — esconda o que não te interessa
- **Planejador de rota** — selecione múltiplos locais e abra a rota diretamente no Google Maps
- **Modal de mapa** — visualize a localização de cada ponto sem sair da página
- **Dark mode** — com preferência salva entre sessões
- **Responsivo** — funciona em desktop e celular

---

## Tecnologias

- HTML5 semântico
- CSS3 com variáveis customizadas (`--primary`, `--accent`, etc.) para theming consistente
- JavaScript vanilla — sem frameworks, sem dependências externas
- `localStorage` para persistir favoritos, visitados e preferência de tema entre sessões
- Google Maps Embed API para os modais de mapa
- Fórmula de Haversine para cálculo de distância geográfica entre pontos

---

## Estrutura do projeto

```
turismo-grande-vitoria/
├── index.html          # Página inicial com hero e mapa geral
├── OndeVisitar.html    # Pontos turísticos por cidade
├── OndeComer.html      # Restaurantes e cafés
├── OndeIrDicas.html    # Dicas rápidas de lugares legais
├── Explorar.html       # Busca cruzada pontos × restaurantes
├── style.css           # Estilos globais + dark mode + responsividade
└── script.js           # Lógica compartilhada: favoritos, mapa, rota, tema
```

---

## Decisões técnicas

**Por que JavaScript vanilla?**
O projeto não precisa de reatividade complexa ou gerenciamento de estado global. Vanilla JS mantém o código legível, sem camada de abstração desnecessária, e deixa claro o que cada função faz — o que importa para um projeto de portfólio.

**Por que `localStorage` e não um backend?**
O site é completamente estático — não há servidor, não há banco de dados. `localStorage` resolve o caso de uso (persistir preferências pessoais do usuário na mesma máquina) sem adicionar complexidade de infraestrutura.

**Como funciona o Explorar?**
Cada ponto turístico tem coordenadas (`lat`/`lng`) extraídas dos embed URLs do Google Maps. Ao selecionar um ponto, o JS filtra os restaurantes da mesma cidade e, quando há coordenadas disponíveis para os dois lados, calcula a distância real em km usando a fórmula de Haversine. Quando corrigir os links dos restaurantes para o padrão com embed URL, a distância ativa automaticamente.

**Por que múltiplas páginas e não uma SPA?**
Com o volume de conteúdo atual, páginas separadas são mais simples de manter e de entender. A página Explorar resolve o caso de uso de busca cruzada sem precisar migrar tudo para um único arquivo. URLs distintas também permitem compartilhar links diretos para cada seção.

---

## Como rodar localmente

Não há build step. Clone o repositório e abra qualquer `.html` diretamente no navegador:

```bash
git clone https://github.com/lucas2398/turismo-grande-vitoria.git
cd turismo-grande-vitoria
# Abra o index.html no seu navegador
```

Para evitar restrições de segurança do browser com iframes locais, prefira usar uma extensão como [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) no VS Code.

---

## Próximos passos

- [ ] Corrigir `OndeComer.html` com embed URLs e coordenadas no padrão do `OndeVisitar`
- [ ] Adicionar filtros por tipo de local (museu, praia, mirante, parque) no `OndeVisitar`
- [ ] Busca por texto livre em tempo real
- [ ] Melhorias visuais na identidade do site

---

## Autor

**Lucas** — [github.com/lucas2398](https://github.com/lucas2398)
