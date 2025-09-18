# 📌 GestorLojaMVP
Aplicativo web MVP para gestão de cadastros de kits de uma loja de cestas de presente, para uso real no negócio, com ferramentas gratuitas e servidor local.

## ✨ Funcionalidades

1. Cadastro de Insumos

- Form com nome, custo, venda, tamanho e categoria.
- Listagem com busca rápida.

2. Cadastro de Categorias de Insumo

- Lista pré-carregada (comida, bebida, cosmético…)
- Mas com opção de adicionar mais.

3. Cadastro de Kits

- Seleciona categoria do kit.
- Busca insumos por nome → adiciona com quantidade.
- Calcula:
  - Preço de custo = (soma dos custos * quantidades) + impostos.
  - Preço sugerido = custo + margem.
- Permite editar manualmente o preço de venda real.

4. Cadastro de Categorias de Kit

- Café da manhã, maternidade, etc.

5. Cadastro de Taxas

- Apenas 1 registro ativo (margem padrão, imposto padrão).
- Pode atualizar.

6. Listagem de Kits

- Tabela com: nome, preço venda real.
- Botão Ver Descritivo (gera texto pronto).
- Botão Detalhes (abre modal).
- Botão de Editar Kit

7. Geração de Descritivo (automática ao salvar kit)

Exemplo:

"Este é o modelo Kit Café da Manhã Premium, ele contém:

- 1 Café 200g
- 2 Pães de queijo (50g cada)
- 1 Suco natural 500ml

E fica no valor de R$ 129,90."

## 🚀 Tecnologias Utilizadas

- Backend: Python + Node.js
- Frontend: React
- Banco de Dados: PostgreSQL
- Servidor ASGI: Uvicorn
- Containerização: Docker
- Versionamento: GitHub

## 📁 Modelagem de dados

Insumo

- id
- nome
- preço_custo
- preço_venda
- tamanho (ex: unidade, 200g, 1L)
- categoria_insumo_id

Categoria de Insumo

- id
- nome (comida, bebida, cosmético, etc.)

Kit

- id
- nome
- categoria_kit_id
- preco_custo (soma insumos + impostos)
- preco_venda_sugerido (custo + margem de lucro)
- preco_venda_real (editável manualmente)

Categoria de Kit

- id
- nome (café da manhã, maternidade, etc.)

KitInsumo (tabela de ligação Kit ↔ Insumos)

- id
- kit_id
- insumo_id
- quantidade

Taxas

- id
- margem_lucro (%)
- impostos (%)
