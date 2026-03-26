# Sistema de Gestão de Farmácia - Saúde & Vida

## Regras de Negócio

1. O sistema não permite vender produto sem estoque disponível.  
2. Toda venda realizada atualiza automaticamente o estoque.  
3. Vendas a prazo geram um registro em contas a receber.  
4. Compras feitas com fornecedores geram contas a pagar.  
5. Produtos com quantidade abaixo do mínimo devem gerar alerta para o gerente.  

---

## Requisitos Funcionais

1. O sistema permite cadastrar clientes.  
2. O sistema permite consultar produtos por nome ou código.  
3. O sistema registra vendas.  
4. O sistema verifica o estoque antes de finalizar a venda.  
5. O sistema registra compras de fornecedores.  
6. O sistema controla contas a pagar.  
7. O sistema controla contas a receber.  
8. O sistema emite comprovante de venda.  
9. O sistema gera relatórios de vendas.  

---

## Requisitos Não Funcionais

1. O sistema deve ser fácil de usar.  
2. O sistema deve responder rapidamente às consultas.  
3. O sistema deve garantir a segurança dos dados.  
4. O sistema deve estar disponível durante o horário de funcionamento.  

---

## Casos de Uso 

### UC1: Realizar Venda

**Ator:** Atendente  

**Descrição:** O atendente realiza a venda de produtos no sistema.

**Fluxo Principal:**
1. Buscar produto  
2. Verificar estoque  
3. Registrar produto na venda  
4. Calcular valor total  
5. Cadastrar cliente (se necessário)  
6. Registrar conta a receber (se venda a prazo)  
7. Finalizar venda  

**Fluxo Alternativo:** Produto sem estoque → sistema informa indisponibilidade  



**Diagrama de Atividade:**

<img width="478" height="717" alt="uc01" src="https://github.com/user-attachments/assets/23dfcbc3-ca2f-4795-afee-adbc82b6baf4" />


---

### UC2: Consultar Produto

**Ator:** Atendente  

**Descrição:** Consulta informações de um produto.  

**Fluxo Principal:**  
1. Digitar nome ou código do produto  
2. Sistema retorna informações  

**Fluxo Alternativo:** Produto não encontrado → mostrar mensagem  



**Diagrama de Atividade:**

<img width="496" height="311" alt="uc02" src="https://github.com/user-attachments/assets/36560eac-5a2c-4ccb-bf34-315398822bf8" />


---

### UC3: Cadastrar Cliente

**Ator:** Atendente  

**Descrição:** Cadastra um novo cliente no sistema.  

**Fluxo Principal:**  
1. Abrir cadastro  
2. Inserir dados do cliente  
3. Salvar cadastro  

**Fluxo Alternativo:** Dados inválidos → mostrar erro  



**Diagrama de Atividade:**

<img width="369" height="366" alt="uc03" src="https://github.com/user-attachments/assets/84c9f66f-ee5d-43fd-b46c-ba54fbaea571" />


---

### UC4: Registrar Compra

**Ator:** Gerente / Financeiro  

**Descrição:** Registra compras realizadas junto a fornecedores.  

**Fluxo Principal:**  
1. Selecionar fornecedor  
2. Adicionar produtos e quantidades  
3. Calcular valor total  
4. Registrar compra  
5. Atualizar estoque  
6. Gerar conta a pagar  

**Fluxo Alternativo:** Dados incorretos → mostrar erro  



**Diagrama de Atividade:**

<img width="340" height="476" alt="uc04" src="https://github.com/user-attachments/assets/12c8b8bd-4a7a-43ba-a43d-869f436b41e1" />


---

### UC5: Atualizar Estoque

**Ator:** Gerente  

**Descrição:** Atualiza quantidade de produtos no estoque.  

**Fluxo Principal:**  
1. Selecionar produto  
2. Informar quantidade e motivo (perda, reposição, transferência)  
3. Confirmar atualização  

**Fluxo Alternativo:** Quantidade inválida → mostrar erro  



**Diagrama de Atividade:**

<img width="387" height="366" alt="uc05" src="https://github.com/user-attachments/assets/37e84ebc-701f-4491-94f0-b34954723b9d" />


---

### UC6: Gerar Relatório

**Ator:** Gerente / Financeiro  

**Descrição:** Gera relatórios de vendas, estoque ou financeiro.  

**Fluxo Principal:**  
1. Selecionar tipo de relatório  
2. Selecionar período/filtros  
3. Sistema gera relatório  

**Fluxo Alternativo:** Relatório não gerado → mostrar erro  



**Diagrama de Atividade:**

<img width="309" height="366" alt="uc06" src="https://github.com/user-attachments/assets/1df6dc5a-8032-4409-961c-e8a5e069aa8f" />


---

### UC7: Registrar Conta a Pagar

**Ator:** Financeiro  

**Descrição:** Lança pagamentos de fornecedores e despesas da farmácia.  

**Fluxo Principal:**  
1. Selecionar fornecedor ou despesa  
2. Informar valor e vencimento  
3. Salvar registro  

**Fluxo Alternativo:** Dados inválidos → mostrar erro  



**Diagrama de Atividade:**

<img width="360" height="366" alt="uc07" src="https://github.com/user-attachments/assets/e1771ad4-f5d2-45d3-9d7f-2512401a99fb" />


---

### UC8: Registrar Conta a Receber

**Ator:** Financeiro  

**Descrição:** Lança valores a receber de clientes.  

**Fluxo Principal:**  
1. Selecionar cliente/convênio  
2. Informar valor e vencimento  
3. Salvar registro  

**Fluxo Alternativo:** Dados inválidos → mostrar erro  



**Diagrama de Atividade:**

<img width="370" height="366" alt="uc08" src="https://github.com/user-attachments/assets/e546abee-31e1-4a7b-b134-c34aec13e275" />


---

### UC9: Validar Receita

**Ator:** Farmacêutico  

**Descrição:** Verifica autenticidade da receita e autoriza venda de medicamento controlado.  

**Fluxo Principal:**  
1. Receber receita  
2. Verificar validade  
3. Autorizar venda  

**Fluxo Alternativo:** Receita inválida → negar venda  



**Diagrama de Atividade:**

<img width="489" height="311" alt="uc09" src="https://github.com/user-attachments/assets/ea5c2ca5-b3fe-4754-b1bf-4f7f48048a32" />


---

### UC10: Gerenciar Usuários

**Ator:** Administrador  

**Descrição:** Adiciona, edita ou remove usuários e controla permissões.  

**Fluxo Principal:**  
1. Abrir painel de administração  
2. Selecionar ação (adicionar, editar, remover)  
3. Confirmar alteração  

**Fluxo Alternativo:** Dados inválidos → mostrar erro  



**Diagrama de Atividade:**

<img width="342" height="366" alt="uc10" src="https://github.com/user-attachments/assets/184fba57-2013-482b-90d1-59a97aab3569" />


---
