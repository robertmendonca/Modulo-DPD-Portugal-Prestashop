# RGC DPD PT - Módulo DPD Portugal para PrestaShop

Módulo gratuito de integração **DPD Portugal** para lojas **PrestaShop 8 e PrestaShop 9**.

Permite disponibilizar métodos de envio DPD no checkout da loja e criar expedições diretamente a partir das encomendas no backoffice do PrestaShop.

> **Versão atual:** v1.1.13  
> **Compatibilidade:** PrestaShop 8.x e 9.x  
> **Estado:** testado e validado em PrestaShop 8 e PrestaShop 9  
> **Distribuição:** Portugal Continental, Ilhas, Espanha e Internacional, de acordo com os serviços contratados com a DPD.

---

## Principais funcionalidades

- Entrega DPD ao domicílio.
- Entrega em pontos DPD Pickup/Shop.
- DPD Fresh, quando contratado.
- Serviços para Portugal Continental e Ilhas.
- Serviços para Espanha.
- Serviços internacionais.
- Apresentação automática dos métodos de envio disponíveis no checkout.
- Pesquisa e seleção de pontos Pickup através de lista e mapa.
- Configuração de preços de portes por serviço.
- Criação de expedições DPD diretamente na encomenda.
- Geração e acesso à etiqueta de transporte em PDF.
- Registo automático do número de tracking no PrestaShop.
- Gestão de diferentes contas DPD por serviço.
- Ferramentas de diagnóstico para apoio em caso de erro.

---

## Requisitos

Para utilizar o módulo é necessário:

- PrestaShop 8.x ou 9.x.
- Contrato ativo com a DPD.
- Credenciais fornecidas pela DPD.
- Conta DPD de 8 dígitos para cada serviço contratado.
- Serviços pretendidos ativos e autorizados pela DPD.
- Chave Pickup/MyPudo, caso utilize entregas em pontos Pickup/Shop.

Sem uma conta DPD válida, o módulo pode ser instalado e configurado, mas não será possível criar expedições reais.

---

## Serviços suportados

| Serviço | Entrega |
|---|---|
| DPD Portugal Home | Domicílio em Portugal Continental |
| DPD Portugal Shop | Pontos Pickup/Shop em Portugal Continental |
| DPD Portugal Fresh | Entrega DPD Fresh |
| DPD Portugal Ilhas | Madeira e Açores |
| DPD Espanha Home | Domicílio em Espanha |
| DPD Espanha Shop | Pontos Pickup/Shop em Espanha |
| DPD Internacional Home | Domicílio internacional |
| DPD Internacional Shop | Pontos Pickup/Shop internacional |

A disponibilidade de cada serviço depende do contrato do cliente com a DPD.

---

## Instalação

1. Descarregue o ficheiro ZIP da versão mais recente do módulo.
2. Entre no backoffice do PrestaShop.
3. Aceda a **Módulos > Gestor de módulos**.
4. Clique em **Carregar um módulo**.
5. Selecione o ficheiro ZIP.
6. Aguarde a instalação.
7. Abra a configuração do módulo **RGC DPD PT**.

Não é necessário executar comandos no servidor para uma instalação normal.

---

## Configuração

Depois da instalação, abra a configuração do módulo.

### 1. Credenciais DPD

Introduza:

- Utilizador da API DPD.
- Password da API DPD.

Depois de guardar, utilize o botão de teste disponível no módulo para confirmar que a ligação à DPD está correta.

### 2. Contas DPD

Ative apenas os serviços que fazem parte do seu contrato.

Para cada serviço configure:

- estado ativo ou inativo;
- conta DPD de 8 dígitos;
- nome que será apresentado ao cliente no checkout.

Os serviços estão organizados entre **Home** e **Pickup**.

### 3. Dados do expedidor

Preencha os dados da empresa ou loja que envia as encomendas:

- nome;
- email;
- telefone;
- morada;
- código postal;
- localidade;
- país.

Estes dados devem corresponder aos dados associados ao contrato DPD.

### 4. Operação

Configure, quando aplicável:

- peso máximo;
- número de volumes;
- formato da etiqueta;
- opções DPD disponíveis para a sua conta.

### 5. Portes

Defina o preço de envio que pretende cobrar ao cliente para cada serviço DPD ativo.

---

## Depois de configurar

Recomendamos fazer uma encomenda de teste antes de disponibilizar os novos métodos de envio aos clientes.

Confirme que:

1. O serviço DPD correto aparece no checkout.
2. O preço dos portes está correto.
3. Nos serviços Pickup, é possível escolher um ponto de entrega.
4. A encomenda aparece corretamente no backoffice.
5. É possível criar a expedição DPD.
6. A etiqueta PDF é gerada corretamente.
7. O tracking fica associado à encomenda.

---

## Entrega em pontos Pickup/Shop

Quando o cliente escolhe um serviço DPD Pickup/Shop:

1. O módulo pesquisa os pontos disponíveis próximos da morada de entrega.
2. O cliente pode consultar os pontos numa lista ou no mapa.
3. O cliente seleciona o ponto pretendido.
4. O ponto escolhido fica associado à encomenda.

A encomenda só pode avançar com um ponto Pickup selecionado quando esse tipo de entrega estiver ativo.

---

## Criar uma expedição DPD

A expedição é criada manualmente no backoffice, permitindo que a loja decida quando a encomenda está pronta para envio.

Para criar a expedição:

1. Aceda a **Encomendas**.
2. Abra a encomenda pretendida.
3. Localize o bloco **DPD Portugal**.
4. Clique em **Criar expedição DPD**.
5. Aguarde a confirmação.
6. Abra ou descarregue a etiqueta PDF.
7. Imprima a etiqueta e prepare a encomenda.

Depois da criação da expedição, o módulo associa automaticamente o tracking DPD à encomenda.

---

## Atualização do módulo

Para atualizar:

1. Faça uma cópia de segurança da loja.
2. Descarregue a versão mais recente do módulo.
3. Faça a atualização através do Gestor de Módulos do PrestaShop.
4. Abra novamente a configuração do módulo.
5. Confirme as configurações.
6. Faça uma encomenda de teste.

As atualizações preservam as configurações existentes sempre que possível.

---

## Problemas comuns

### Os métodos DPD não aparecem no checkout

Confirme:

- se o módulo está ativo;
- se o serviço DPD está ativado;
- se a conta DPD correspondente está preenchida;
- se a morada do cliente está completa;
- se o país de entrega é suportado pelo serviço;
- se o peso da encomenda está dentro do limite configurado.

### Não aparecem pontos Pickup

Confirme:

- se o serviço Pickup está ativo;
- se possui contrato DPD para Pickup/Shop;
- se a conta DPD de Pickup está configurada;
- se o cliente introduziu um código postal válido.

### Não é possível criar a expedição

Confirme:

- as credenciais DPD;
- a conta DPD associada ao serviço;
- os dados do expedidor;
- a morada e contacto do destinatário;
- se o serviço utilizado está ativo no contrato DPD.

O módulo inclui uma área de diagnóstico que pode ser utilizada para obter mais informação antes de contactar o suporte.

---

## Segurança e privacidade

As credenciais DPD ficam guardadas na instalação do cliente e devem ser tratadas como informação confidencial.

Nunca publique em fóruns, issues ou screenshots públicos:

- passwords DPD;
- chaves Pickup/MyPudo;
- etiquetas reais;
- dados pessoais de clientes;
- dados completos de encomendas.

O módulo não envia para a RGC Consulting passwords DPD, dados de clientes, dados de encomendas ou etiquetas.

---

## Suporte

O módulo é disponibilizado gratuitamente.

Cada cliente tem direito a **15 minutos gratuitos de apoio inicial através da DPD** para instalação ou primeira configuração.

Suporte técnico adicional:

**35 EUR + IVA por cada pack de 30 minutos.**

O apoio pode incluir:

- instalação assistida;
- configuração das contas DPD;
- configuração dos serviços;
- validação das transportadoras;
- análise de problemas no checkout;
- validação do fluxo Pickup;
- análise de erros na criação de expedições.

Ao pedir suporte, indique sempre:

- endereço da loja;
- versão do PrestaShop;
- versão do módulo;
- serviço DPD utilizado;
- descrição do problema;
- passos para reproduzir o erro.

Não envie passwords ou outras credenciais por canais públicos.

---

## Créditos

Desenvolvido por **RGC Consulting** em parceria com a **DPD Portugal** para integração dos serviços DPD em lojas PrestaShop.

## Apoie o meu trabalho

Se este projeto ajudou, considere apoiar o desenvolvimento:

[![Buy Me a Coffee](https://github.com/user-attachments/assets/e5e0b7a8-4ec3-4a20-b5c8-07301078a283)](https://www.buymeacoffee.com/robertmendonca)
