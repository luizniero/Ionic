# JSON que serão consumidos no trabalho - IONIC

## **OBS: Todas as requisições estão sendo feitas via POST.**

## **Requisições do Projeto:**

### **1. Validação do login de usuário:**
  - A app enviará um JSON para o webservice contendo o usuário e senha;
  - O Webservice deverá receber o JSON e verificar no BD se o ID para aquele usuário existe. Caso exista, o servidor retornará um JSON com 1, além de retornar também o nome e o ID dos dependentes desse mesmo usuário. Se não existir, deverá retornar 0. Caso não exista dependentes, retornar null.
  - *O JSON deve conter os seguintes campos:*
    1) validacao (Campo que deverá conter 0 ou 1).  Tratá o número 2 também, no mesmo arquivo.;
    2) dependentes (Array de dependentes):
        - numero_cartao_sus;
        - nome (nome do dependente);
        - data_nasc;
        - cod_usuario (para referenciar na hora de puxar os dependentes do usuário cadastrado);
        
        
        
 ### **2. Cadastrar novos usuários:**
  - A app deverá enviar um JSON para o webservice com os campos: nome, usuario e senha.
  - O Webservice deverá receber o JSON e cadastrar o novo usuário no BD. Caso o cadastro seja bem sucedido, deverá retornar um JSON com o campo validacao nos mesmos moldes do item 1. (validacao = idUsuario (!= 0), se bem sucedido, caso contrário validacao = 0.)
  
  
  
### **3. Carregar carteira de vacinação:**
  - A app enviará um JSON para o webservice com o campo Número cartão sus.
  - O webservice vai receber o JSON e consultar a carteira de vacina do usuário. Caso a consulta seja bem sucedida, deverá retornar 1, além de um array contendo as aplicações de vacina, caso contrário 0. Caso não exista vacinas, retornar null.
  - *O JSON dever conter os seguintes campos:*
      1) validacao (Campo de deverá conter 0 ou 1)
      2) vacinas (Array de vacinas tomadas pelo usuário):
          - nome_vacina;
          - numero_da_dose;
          - tipo_da_dose;
          - data_aplicacao;
### **4. Cadastrar aplicação de vacina:**
  - A app enviará para o servidor um JSON com os seguintes campos: Número cartão sus, Nome vacina, Dose, Data aplicação.
  - O webservice receberá o JSON e vai cadastrar uma nova aplicação de vacina. Caso o cadastro seja bem sucedido, deverá retornar 1, além do Número cartão sus e também um array contendo as aplicações de vacina. Senão, retornará 0.
  - *O JSON dever ter o mesmo formato do item 3*.


------------------------------------------------------------------------------------------------------------------------------------

# Entradas
As entradas serão enviadas em JSON via método POST para o servidor e elas devem seguir o formato a seguir:
## **1.Entrada Login:**
  - login;
  - senha;
    
## **2.Entrada Cadastro de Novo Usuário:**
  - nome;
  - numero_cartao;
  - usuario;
  - senha;
  - data_nascimento;
 
## **3.Entrada carregar Carteira de Vacinação:**
  - numero_cartao_sus;
  
## **4. Entrada Cadastrar Aplicação de Vacina:**
