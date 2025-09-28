Visão Geral e Objetivo -
Este projeto foi desenvolvido para automatizar a gestão de licenças operacionais, substituindo a demorada verificação manual de planilhas. A solução usa um script em Python que lê os dados de vencimento de uma planilha Excel (projeto_automacao.xlsx), aplica formatação de status e envia alertas. O principal diferencial é a centralização das notificações: em vez de enviar e-mails individuais, o sistema consolida todos os alertas em um único resumo para o gestor.

Estrutura de Dados e Lógica do Script -
O script depende de uma planilha Excel de estrutura fixa. As colunas essenciais para o funcionamento são:

A coluna A (Nome do Cliente), utilizada para personalizar o conteúdo do e-mail.

A coluna D (Vencimento da Licença), que contém a data crucial para o cálculo.

A coluna G (Status), onde o script aplica o resultado do processamento.

A lógica de coloração e status é definida com base na data atual:

Se a licença vencer em mais de 30 dias, o status é marcado como EM DIA (cor verde) e nenhum alerta é enviado.

Se faltarem até 30 dias para o vencimento, o status muda para PRÓXIMO VENCIMENTO (cor amarela) e o cliente é incluído no alerta consolidado.

Se a data de vencimento for no passado (vencida), o status é VENCIDO (cor vermelha) e o cliente também é incluído no alerta.

Sistema de Notificação por E-mail -
A funcionalidade de e-mail foi projetada para otimizar o tempo do gestor. O script percorre todas as linhas e armazena os dados dos clientes em situação de alerta (amarela ou vermelha). No final do processamento da planilha, ele envia um único e-mail contendo uma lista organizada de todas as licenças que exigem atenção imediata.

Uso de Inteligência Artificial (IA) no Projeto -
Em nome da transparência e do uso ético de recursos modernos, informamos que ferramentas de Inteligência Artificial (IA) foram utilizadas durante o desenvolvimento.

O papel da IA foi estritamente auxiliar, sendo aplicada para otimização de trechos de código, sugestão de estruturas de dados (como a lógica de consolidação de e-mails) e, principalmente, na elaboração da documentação técnica e didática do projeto, incluindo este próprio README e o Diário de Bordo.

Todo o código-fonte foi escrito, revisado, testado e validado manualmente pelo desenvolvedor, garantindo a autoria da lógica de negócio e a responsabilidade total pela funcionalidade final.

Como Utilizar (Usuário Final) - 
Para executar a automação, não é necessário ter o Python instalado. O programa está empacotado em um executável (.exe):

Feche o Excel: É fundamental que o arquivo projeto_automacao.xlsx esteja fechado antes da execução.

Organização: O executável (automacao.exe) e a planilha de dados (projeto_automacao.xlsx) devem estar na mesma pasta.

Execução: Dê um duplo clique no arquivo automacao.exe. O Prompt de Comando (CMD) será exibido e, após alguns segundos, o programa encerrará.

Verificação: A planilha estará atualizada com as cores e o e-mail resumo terá sido enviado para o gestor.

Requisitos de Desenvolvimento -
Para manutenção ou modificações no código-fonte (automacao.py), o ambiente de desenvolvimento deve ter Python 3.x e as seguintes bibliotecas instaladas: openpyxl, smtplib, e as bibliotecas do email. Para gerar um novo executável, utilize a ferramenta PyInstaller.
