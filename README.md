# RGC DPD PT - Módulo DPD Portugal para PrestaShop

Módulo gratuito de integração **DPD Portugal** para lojas **PrestaShop 8.x e 9.x**.

Este módulo permite configurar serviços DPD no checkout da loja, incluindo entrega ao domicílio e entrega em pontos Pickup/Shop, e criar expedições DPD a partir da encomenda no backoffice do PrestaShop.

> **Versão atual:** v1.0.2 
> **Nome do módulo:** RGC DPD PT  
> **Compatibilidade:** PrestaShop 8.x e 9.x  
> **PrestaShop 9.x:** testado com sucesso em ambiente de validação.  
> **Âmbito:** Portugal Continental, Portugal Ilhas, Espanha e Internacional, conforme os serviços contratados com a DPD.

---

## Índice

- [Para quem é este módulo](#para-quem-é-este-módulo)
- [Principais funcionalidades](#principais-funcionalidades)
- [Serviços DPD suportados](#serviços-dpd-suportados)
- [Requisitos](#requisitos)
- [Download e instalação](#download-e-instalação)
- [Dados necessários para configurar](#dados-necessários-para-configurar)
- [Configuração do módulo](#configuração-do-módulo)
- [Utilização no checkout](#utilização-no-checkout)
- [Criação de expedições DPD](#criação-de-expedições-dpd)
- [Atualização do módulo](#atualização-do-módulo)
- [Resolução rápida de problemas](#resolução-rápida-de-problemas)
- [Segurança](#segurança)
- [Suporte](#suporte)
- [Créditos](#créditos)

---

## Para quem é este módulo

Este módulo destina-se a clientes DPD que utilizam **PrestaShop** e pretendem integrar serviços DPD na sua loja online.

Para criar expedições reais, é obrigatório ter:

- contrato ativo com a DPD;
- credenciais API válidas;
- contas DPD de 8 dígitos para os serviços contratados;
- validação da DPD para os serviços que pretende utilizar, incluindo Pickup/Shop quando aplicável.

Sem estes dados, o módulo pode ser instalado, mas não conseguirá criar expedições reais.

---

## Principais funcionalidades

### No checkout da loja

- Apresenta métodos de envio DPD conforme a morada do cliente.
- Suporta entrega ao domicílio através de serviços Home.
- Suporta serviço DPD Fresh, quando contratado e validado pela DPD.
- Suporta entrega em pontos Pickup/Shop.
- Mostra lista e mapa de pontos Pickup quando o cliente escolhe um serviço Pickup/Shop.
- Exige a seleção de um ponto Pickup antes da finalização da encomenda.
- Usa ícones DPD nos métodos de envio e no mapa.

### No backoffice do PrestaShop

- Permite configurar as credenciais DPD visíveis ao cliente.
- Mantém endpoints técnicos e chaves internas protegidos da interface.
- Permite configurar contas DPD por serviço.
- Inclui configuração para DPD Fresh.
- Separa a configuração entre serviços **Home** e **Pickup**.
- Permite ativar a área Pickup apenas quando o cliente tem contrato DPD para esse serviço.
- Cria e repara automaticamente as transportadoras DPD no PrestaShop.
- Permite criar uma expedição DPD a partir da encomenda.
- Guarda a guia DPD e a etiqueta PDF.
- Atualiza o tracking da encomenda no PrestaShop.
- Disponibiliza área de diagnóstico com logs e informação útil para suporte.

---

## Serviços DPD suportados

O módulo trabalha por tipologia de serviço. Cada serviço deve ser ativado apenas se estiver contratado e validado pela DPD.

| Serviço | Tipo de entrega | Destino |
|---|---|---|
| DPD Portugal Home | Home | Portugal Continental |
| DPD Portugal Shop | Pickup/Shop | Portugal Continental |
| DPD Portugal Fresh | Home/Fresh | Portugal Continental |
| DPD Portugal Ilhas | Home | Madeira e Açores |
| DPD Espanha Home | Home | Espanha |
| DPD Espanha Shop | Pickup/Shop | Espanha |
| DPD Internacional Home | Home | Países diferentes de Portugal e Espanha |
| DPD Internacional Shop | Pickup/Shop | Países diferentes de Portugal e Espanha |

Cada serviço utiliza uma **conta DPD de 8 dígitos**. As contas devem ser fornecidas pela DPD.

---

## Requisitos

### Loja

- PrestaShop 8.x ou 9.x.
- Produtos físicos.
- Backoffice com permissão para instalar módulos.
- Países, zonas, moradas e transportadoras corretamente configurados.
- Checkout compatível com o fluxo padrão do PrestaShop.

### Servidor

Recomendado:

- PHP 8.1 ou superior.
- Extensão PHP `curl` ativa.
- Extensão PHP `json` ativa.
- Extensão PHP `openssl` ativa.
- Extensão PHP `soap` recomendada para pesquisa Pickup.

Para o mapa Pickup, o front office precisa conseguir carregar os recursos externos usados pelo Leaflet/OpenStreetMap.

---

## Download e instalação

### Opção recomendada: instalação por ZIP

1. Aceda ao repositório do módulo no GitHub.
2. Descarregue o ficheiro `.zip` da versão estável do módulo.
3. Entre no backoffice do PrestaShop.
4. Vá a **Módulos > Gestor de módulos**.
5. Clique em **Carregar um módulo**.
6. Selecione o ficheiro ZIP do módulo.
7. Aguarde o upload terminar.
8. Clique em **Instalar**.
9. Abra a configuração do módulo **RGC DPD PT**.

Não é necessário executar comandos técnicos no servidor para uma instalação normal pelo backoffice.

### Opção técnica: clonar o repositório

Para equipas técnicas que pretendem consultar ou validar o código:

```bash
git clone https://github.com/robertmendonca/DPD-PT-Prestashop.git
```

Depois de clonar, garanta que a pasta do módulo fica com o nome correto:

```text
rgcdpdpt
```

No PrestaShop, o módulo deve ficar em:

```text
/modules/rgcdpdpt
```

---

## Dados necessários para configurar

Antes de configurar o módulo, solicite à DPD os dados da sua conta.

Dados necessários:

- utilizador da API DPD;
- password da API DPD;
- contas DPD de 8 dígitos para cada serviço contratado;
- confirmação dos serviços contratados:
  - Portugal Home;
  - Portugal Shop/Pickup;
  - Portugal Fresh;
  - Portugal Ilhas;
  - Espanha Home;
  - Espanha Shop/Pickup;
  - Internacional Home;
  - Internacional Shop/Pickup;
- chave Pickup/MyPudo, caso utilize serviços Pickup/Shop;
- validação de produção pela DPD.

Os endpoints técnicos da API DPD e do serviço Pickup são mantidos internamente no módulo e não são exibidos ao cliente no backoffice.

---

## Modelo de pedido à DPD

Pode usar este texto para solicitar os dados necessários:

```text
Boa tarde,

Precisamos configurar o módulo RGC DPD PT para PrestaShop.

Podem enviar, por favor, os dados necessários para ativação em produção?

Dados necessários:
- utilizador da API DPD;
- password da API DPD;
- contas DPD de 8 dígitos para os serviços contratados;
- confirmação dos serviços ativos no contrato;
- chave Pickup/MyPudo, caso o cliente tenha serviço Pickup/Shop contratado.

Serviços pretendidos:
- Portugal Home;
- Portugal Shop/Pickup;
- Portugal Fresh;
- Portugal Ilhas;
- Espanha Home;
- Espanha Shop/Pickup;
- Internacional Home;
- Internacional Shop/Pickup.

Obrigado.
```

---

## Configuração do módulo

Depois de instalar, aceda à configuração do módulo e preencha as abas disponíveis.

### 1. Aba DPD

Nesta aba devem ser preenchidas apenas as credenciais fornecidas pela DPD:

- **Utilizador da API**
- **Password da API**

Os restantes endpoints técnicos são internos do módulo e não aparecem no backoffice.

Depois de guardar, use o botão **Testar OAuth DPD** para validar a autenticação.

---

### 2. Aba Contas DPD

Nesta aba são configuradas as contas DPD dos serviços contratados.

A aba está dividida em duas secções:

- **Home**
- **Pickup**

Configure:

- serviço ativo/inativo;
- conta DPD de 8 dígitos;
- nome visível da transportadora no checkout.

#### Home

Use esta secção para serviços de entrega ao domicílio.

Exemplos:

- DPD Portugal Home;
- DPD Portugal Fresh;
- DPD Portugal Ilhas;
- DPD Espanha Home;
- DPD Internacional Home.

#### Pickup

Use esta secção apenas se o cliente tiver contrato DPD para serviços Pickup/Shop.

A secção Pickup tem um botão de ativação. Ao ativar, o módulo apresenta um aviso para confirmar que o serviço só deve ser configurado quando existir contrato DPD para Pickup.

Quando ativado e guardado, o estado da secção Pickup fica persistente. Quando desativado e guardado, permanece desativado.

#### DPD Fresh

O serviço **DPD Portugal Fresh** aparece na secção **Home**, mas deve ser ativado apenas quando existir contrato DPD Fresh válido.

Quando uma encomenda utiliza o serviço DPD Fresh, o módulo adiciona ao payload da API DPD os campos específicos do serviço:

Por defeito:

- `fresh_pickup_date` é enviado como **D+1**;
- `fresh_expiration_date` é enviado com base na validade Fresh configurada, por defeito **D+5**.

---

### 3. Aba Dados do expedidor

Configure os dados do expedidor que serão utilizados pela DPD como origem das expedições, recolhas e etiquetas. Estes dados devem corresponder à morada e aos contactos associados ao contrato DPD.

Campos:

| Campo | Descrição | Exemplo |
|---|---|---|
| Nome do remetente | Nome de contacto do remetente | Loja Exemplo |
| E-mail do remetente | E-mail de contacto do remetente | geral@exemplo.pt |
| Indicativo do telefone do remetente | Indicativo telefónico | +351 |
| Telefone do remetente | Telefone fixo, se aplicável | 210 000 000 |
| Indicativo do telemóvel do remetente | Indicativo do telemóvel | +351 |
| Telemóvel do remetente | Telemóvel de contacto | 999 999 999 |
| Nome do expedidor | Nome legal ou comercial do expedidor | Loja Exemplo Lda. |
| Morada do expedidor | Morada de origem das expedições | Praça do Comércio |
| Código postal do expedidor | Código postal da morada de origem | 1100-148 |
| Localidade do expedidor | Localidade da morada de origem | Lisboa |
| País do expedidor — ISO2 | Código ISO2 do país | PT |

Para Portugal, o campo **País do expedidor — ISO2** deve ser:

```text
PT
```

---

### 4. Aba Operação

Configure os parâmetros operacionais do módulo:

- peso máximo permitido;
- Predict, se aplicável;
- número de volumes por defeito;
- validade Fresh em dias, quando aplicável;
- formato da etiqueta;
- ativação de logs.

---

### 5. Aba Portes

Defina o preço base de cada serviço DPD.

O módulo usa estes valores para apresentar o custo de envio no checkout. Apenas os serviços configurados e ativos na aba **Contas DPD** devem ser usados.

---

### 6. Aba Diagnóstico

Use esta área para:

- testar autenticação;
- verificar serviços ativos;
- consultar transportadoras configuradas;
- analisar mensagens de erro;
- recolher informação para suporte.

---

## Depois de configurar

Após qualquer alteração importante:

1. Clique em **Guardar configurações**.
2. Clique em **Reparar transportadoras**.
3. Limpe a cache do PrestaShop.
4. Faça uma encomenda de teste.
5. Confirme que o método DPD correto aparece no checkout.
6. Confirme que a criação da expedição funciona no backoffice.

---

## Utilização no checkout

### Entrega Home

O cliente escolhe o método DPD Home disponível para a sua morada e finaliza a compra normalmente.

### Entrega DPD Fresh

O cliente escolhe o método **DPD Portugal Fresh** disponível para a sua morada e finaliza a compra normalmente.

Ao criar a expedição no backoffice, o módulo envia automaticamente as datas Fresh exigidas pela API DPD.

### Entrega Pickup/Shop

Quando o cliente escolhe um serviço Pickup/Shop:

1. O módulo carrega os pontos próximos com base no código postal da morada de entrega.
2. O cliente pode escolher o ponto numa lista ou diretamente no mapa.
3. A seleção do ponto Pickup é obrigatória.
4. O ponto escolhido fica associado ao carrinho e à encomenda.

O botão **Procurar pontos Pickup** serve para atualizar a pesquisa, por exemplo quando o cliente altera o código postal.

---

## Criação de expedições DPD

A expedição não é criada automaticamente no momento da compra.

Esta decisão evita criar expedições para encomendas ainda não pagas, canceladas, pendentes de validação ou ainda em preparação.

Para criar a expedição:

1. Entre no backoffice do PrestaShop.
2. Vá a **Encomendas**.
3. Abra a encomenda pretendida.
4. Confirme que a encomenda está pronta para expedir.
5. No bloco **DPD Portugal**, clique em **Criar expedição DPD**.
6. Aguarde a resposta da DPD.
7. Abra ou descarregue a etiqueta PDF.
8. Imprima a etiqueta e prepare a encomenda.

Depois da criação da expedição, o módulo guarda:

- número da guia DPD;
- etiqueta PDF;
- tracking no PrestaShop;
- resposta da DPD para diagnóstico.

---

## Atualização do módulo

Para atualizar para uma nova versão:

1. Faça backup da loja e da base de dados.
2. Descarregue o novo ZIP do módulo.
3. Instale ou atualize pelo backoffice do PrestaShop.
4. Confirme que a versão foi atualizada.
5. Abra a configuração do módulo.
6. Clique em **Guardar configurações**.
7. Clique em **Reparar transportadoras**.
8. Limpe a cache do PrestaShop.
9. Teste o checkout e a criação de expedição.

---

## Resolução rápida de problemas

### Os métodos DPD não aparecem no checkout

Verifique:

- se o módulo está instalado e ativo;
- se os serviços DPD estão ativos na configuração;
- se as contas DPD de 8 dígitos estão preenchidas;
- se clicou em **Reparar transportadoras**;
- se a morada do cliente está completa;
- se o país/região é abrangido pelo serviço ativo;
- se o peso do carrinho não ultrapassa o limite configurado;
- se os produtos são físicos;
- se a cache do PrestaShop foi limpa.

### O mapa Pickup não aparece

Verifique:

- se o cliente selecionou um método Pickup/Shop;
- se a secção Pickup está ativa na aba **Contas DPD**;
- se o serviço Pickup/Shop correspondente está ativo;
- se a conta DPD de Pickup está configurada;
- se o cliente tem contrato DPD para Pickup;
- se a morada tem código postal válido;
- se a chave Pickup/MyPudo está configurada internamente;
- se o servidor consegue comunicar com o webservice Pickup;
- se o tema da loja não bloqueia JavaScript;
- se o front office consegue carregar recursos externos do mapa.

### A expedição DPD falha

Verifique:

- utilizador da API e password da API;
- endpoints de produção validados internamente no módulo;
- conta DPD associada ao serviço escolhido;
- permissões da conta na DPD;
- IP autorizado, se aplicável;
- morada do destinatário;
- telefone/telemóvel do destinatário;
- ponto Pickup selecionado, no caso de Pickup/Shop;
- validade Fresh configurada, no caso de DPD Fresh;
- mensagem apresentada na aba **Diagnóstico**.

### A guia não aparece, mas a etiqueta foi criada

Se a API devolver a etiqueta mas não devolver a guia num campo reconhecido, o bloco DPD da encomenda pode permitir:

- recuperar a guia a partir da resposta guardada;
- recuperar a guia a partir da etiqueta;
- inserir a guia manualmente.

---

## Segurança

Durante a instalação e ao guardar configurações, o módulo pode enviar à RGC Consulting um registo técnico simples contendo domínio da loja, versão do módulo, versão do PrestaShop, identificador da instalação e contas DPD configuradas.

Não são enviados dados de clientes, encomendas, passwords, tokens OAuth ou etiquetas.

Nunca publique em issues, screenshots, fóruns ou repositórios públicos:

- password da API;
- client secret;
- chave Pickup/MyPudo;
- tokens OAuth;
- etiquetas PDF reais;
- dados pessoais de clientes;
- moradas completas de clientes;
- payloads completos de expedições reais;
- logs com dados pessoais.

Se uma credencial for exposta por engano, contacte a DPD e solicite a substituição/rotação da credencial.

---
## Responsabilidade de configuração

O correto funcionamento do módulo depende de:

- credenciais DPD válidas;
- serviços contratados e ativos na DPD;
- contas DPD corretas por serviço;
- endpoints corretos para produção;
- configuração correta da loja PrestaShop;
- servidor com extensões PHP necessárias.

Alguns erros podem depender da validação da própria DPD, por exemplo credenciais inválidas, IP não autorizado, conta sem permissão para Pickup ou serviço contratado diferente do serviço configurado.

---

## Suporte

O módulo é disponibilizado gratuitamente.

Cada cliente tem direito a **15 minutos gratuitos de apoio inicial pela DPD** para instalação ou primeira configuração.

Após esse período, o suporte técnico adicional é cobrado em packs de:

```text
35 EUR + IVA por pack adicional de 30 minutos
```

O suporte pode incluir:

- instalação assistida;
- configuração das contas DPD;
- validação das transportadoras;
- análise de erros no checkout;
- análise de erros da API;
- validação do fluxo Pickup;
- testes de criação de expedição.

### Dados úteis para pedir suporte

Ao pedir suporte, envie:

```text
Loja: https://exemplo.pt
PrestaShop: 8.x / 9.x
PHP: 8.x
Módulo: v1.0.2
Ambiente: produção
Serviço DPD usado: Portugal Home / Portugal Shop / Portugal Fresh / Ilhas / Espanha / Internacional
Erro apresentado:
Passos para reproduzir:
```

Também pode ser útil enviar prints da configuração, da encomenda e da mensagem de erro, desde que não contenham credenciais nem dados pessoais sensíveis.

---

## Créditos

Desenvolvido por **RGC Consulting** para integração DPD Portugal em PrestaShop.

---

## Apoie o meu trabalho

Se este projeto ajudou, considere apoiar o desenvolvimento:

[![Buy Me a Coffee](https://github.com/user-attachments/assets/e5e0b7a8-4ec3-4a20-b5c8-07301078a283)](https://www.buymeacoffee.com/robertmendonca)
