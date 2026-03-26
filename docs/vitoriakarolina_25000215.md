# Avaliação — Engenharia de Software
## Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante

**Aluno:** Vitória Karolina Santos Silva
**RA:** 25000215 
**Data:** 25/03/2026

---

## 1. Definição do MVP

O meu MVP foca no que é mais importante para a operação do dia a dia da farmácia: **vendas, estoque e clientes**. A ideia é que o sistema consiga ser usado no balcão sem problemas e ajude a controlar o estoque de forma automática.  

### O que está dentro do MVP:
- Cadastro e identificação de clientes.  
- Consulta de produtos pelo nome ou código.  
- Registro de vendas, tanto à vista quanto a prazo.  
- Verificação de estoque antes da venda e atualização automática depois.  
- Emissão de comprovante de venda.  
- Registro de contas a receber quando a venda é a prazo.  
- Avisos simples de erro, como produto sem estoque ou cliente não cadastrado.  

### O que está fora do MVP:
- Relatórios avançados para matriz (produtos mais vendidos, produtos nunca vendidos).  
- Controle completo de contas a pagar, impostos e outras despesas.  
- Gestão de usuários e permissões complexa.  
- Integração em tempo real entre unidades diferentes.  
- Compras automáticas ou previsão de estoque.  

### Por que essas escolhas:
Decidi focar no **essencial para atender o cliente e não ter erros de estoque**.  
Se essas partes funcionarem bem, o sistema já ajuda bastante no dia a dia da farmácia.  


---

## 2. Documentação dos Casos de Uso

### UC01 — Realizar Venda
**Ator:** Atendente  
**Descrição:** Permite que o atendente registre a venda de produtos, verificando estoque e tratando vendas à vista ou a prazo.  
**Pré-condições:** Produto cadastrado; cliente cadastrado ou pode ser cadastrado na hora.  
**Pós-condições:** Venda registrada, estoque atualizado, conta a receber criada se venda for a prazo.  

**Fluxo Principal:**  
1. Buscar produto pelo nome, código ou fabricante  
2. Verificar estoque  
3. Registrar produto na venda  
4. Calcular valor total  
5. Cadastrar cliente se necessário  
6. Registrar conta a receber se for venda a prazo  
7. Emitir comprovante e finalizar venda  

**Fluxos Alternativos / Exceções:**  
- FA01 — Produto sem estoque → avisar e não registrar o item  
- FA02 — Cliente não cadastrado e não deseja cadastrar → registrar venda sem vincular cliente  

**Relacionamentos:**  
- Include: UC03 — Cadastrar Cliente  
- Extend: nenhum  

**Diagrama de Atividade:**  

<img width="478" height="717" alt="uc01" src="https://github.com/user-attachments/assets/57891b21-1f2f-4737-84cf-663d708c5542" />

---

### UC02 — Consultar Produto
**Ator:** Atendente  
**Descrição:** Consulta informações de produtos cadastrados.  
**Pré-condições:** Produto cadastrado.  
**Pós-condições:** Produto encontrado ou mensagem de erro se não existir.  

**Fluxo Principal:**  
1. Digitar nome ou código do produto  
2. Sistema busca produto  
3. Exibir informações  

**Fluxos Alternativos / Exceções:**  
- FA01 — Produto não encontrado → mensagem de erro  

**Relacionamentos:** nenhum  

**Diagrama de Atividade:**  

<img width="496" height="311" alt="uc02" src="https://github.com/user-attachments/assets/bbe707d5-54f1-44fe-920d-275aa4bc1058" />


---

### UC03 — Cadastrar Cliente
**Ator:** Atendente  
**Descrição:** Permite cadastrar um novo cliente no sistema.  
**Pré-condições:** Nenhuma.  
**Pós-condições:** Cliente cadastrado e disponível para vendas futuras.  

**Fluxo Principal:**  
1. Abrir tela de cadastro  
2. Inserir dados do cliente  
3. Salvar cadastro  

**Fluxos Alternativos / Exceções:**  
- FA01 — Dados incompletos → mostrar mensagem de erro  

**Relacionamentos:** nenhum  

**Diagrama de Atividade:**  

<img width="369" height="366" alt="uc03" src="https://github.com/user-attachments/assets/65bbe40f-3054-4f7a-a0d8-1b8a06dc1327" />

---

### UC04 — Registrar Compra
**Ator:** Gerente / Financeiro  
**Descrição:** Registrar compras de fornecedores e atualizar estoque e contas a pagar.  
**Pré-condições:** Produto e fornecedor cadastrados.  
**Pós-condições:** Compra registrada, estoque atualizado, conta a pagar criada.  

**Fluxo Principal:**  
1. Selecionar fornecedor  
2. Inserir produtos e quantidades  
3. Calcular valor total  
4. Salvar compra  
5. Atualizar estoque  
6. Gerar conta a pagar  

**Fluxos Alternativos / Exceções:**  
- FA01 — Dados incorretos → cancelar registro e mostrar mensagem de erro  

**Relacionamentos:** nenhum  
**Diagrama de Atividade:**  

<img width="340" height="476" alt="uc04" src="https://github.com/user-attachments/assets/2c32cee5-b25e-4ffb-8053-370e8b1962bc" />


---

### UC05 — Atualizar Estoque
**Ator:** Gerente  
**Descrição:** Ajustar quantidade de produtos no estoque (perda, reposição ou transferência).  
**Pré-condições:** Produto cadastrado.  
**Pós-condições:** Estoque atualizado corretamente.  

**Fluxo Principal:**  
1. Selecionar produto  
2. Informar quantidade e motivo  
3. Confirmar atualização  

**Fluxos Alternativos / Exceções:**  
- FA01 — Quantidade inválida → mostrar mensagem de erro  

**Relacionamentos:** nenhum  
**Diagrama de Atividade:**  

<img width="387" height="366" alt="uc05" src="https://github.com/user-attachments/assets/fb953d8c-5c3d-4a94-8394-62741e49a01e" />


---

### UC06 — Gerar Relatório
**Ator:** Gerente / Financeiro  
**Descrição:** Gerar relatórios de vendas, estoque ou financeiro.  
**Pré-condições:** Dados cadastrados no sistema.  
**Pós-condições:** Relatório gerado e exibido.  

**Fluxo Principal:**  
1. Selecionar tipo de relatório  
2. Definir período e filtros  
3. Gerar relatório  

**Fluxos Alternativos / Exceções:**  
- FA01 — Dados insuficientes → mostrar mensagem de erro  

**Relacionamentos:** nenhum  
**Diagrama de Atividade:**  

<img width="309" height="366" alt="uc06" src="https://github.com/user-attachments/assets/b73c7c25-c508-4b19-9608-63046b802dc5" />


---

### UC07 — Registrar Conta a Pagar
**Ator:** Financeiro  
**Descrição:** Lançar pagamentos de fornecedores ou despesas da farmácia.  
**Pré-condições:** Fornecedor ou despesa cadastrados.  
**Pós-condições:** Conta a pagar registrada.  

**Fluxo Principal:**  
1. Selecionar fornecedor/despesa  
2. Informar valor e data de vencimento  
3. Salvar registro  

**Fluxos Alternativos / Exceções:**  
- FA01 — Dados inválidos → mostrar mensagem de erro  

**Relacionamentos:** nenhum  
**Diagrama de Atividade:**  

<img width="360" height="366" alt="uc07" src="https://github.com/user-attachments/assets/77cb3c51-d3a5-4687-bb96-760168084da2" />


---

### UC08 — Registrar Conta a Receber
**Ator:** Financeiro  
**Descrição:** Lançar valores a receber de clientes ou convênios.  
**Pré-condições:** Cliente ou convênio cadastrado.  
**Pós-condições:** Conta a receber registrada.  

**Fluxo Principal:**  
1. Selecionar cliente/convênio  
2. Informar valor e data de vencimento  
3. Salvar registro  

**Fluxos Alternativos / Exceções:**  
- FA01 — Dados inválidos → mostrar mensagem de erro  

**Relacionamentos:** nenhum  
**Diagrama de Atividade:**  

<img width="370" height="366" alt="uc08" src="https://github.com/user-attachments/assets/ba9537a2-1f06-4586-9525-bcc172847baa" />


---

### UC09 — Validar Receita
**Ator:** Farmacêutico  
**Descrição:** Verifica autenticidade da receita e autoriza venda de medicamento controlado.  
**Pré-condições:** Receita apresentada pelo cliente.  
**Pós-condições:** Venda autorizada ou negada.  

**Fluxo Principal:**  
1. Receber receita  
2. Verificar validade  
3. Autorizar venda se válida  

**Fluxos Alternativos / Exceções:**  
- FA01 — Receita inválida → negar venda e informar cliente  

**Relacionamentos:** nenhum  
**Diagrama de Atividade:**  

<img width="489" height="311" alt="uc09" src="https://github.com/user-attachments/assets/a6a11777-5737-492d-b9a3-eb128ccf9ac7" />


---

### UC10 — Gerenciar Usuários
**Ator:** Administrador  
**Descrição:** Permite adicionar, editar ou remover usuários e controlar permissões.  
**Pré-condições:** Administrador logado.  
**Pós-condições:** Alterações aplicadas corretamente.  

**Fluxo Principal:**  
1. Abrir painel de administração  
2. Selecionar ação (adicionar, editar, remover)  
3. Confirmar alteração  

**Fluxos Alternativos / Exceções:**  
- FA01 — Dados inválidos → mostrar mensagem de erro  

**Relacionamentos:** nenhum  
**Diagrama de Atividade:**  

<img width="342" height="366" alt="uc10" src="https://github.com/user-attachments/assets/b1a179be-401d-4e69-86ed-bc5dacef5298" />

