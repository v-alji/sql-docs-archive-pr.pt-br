---
title: Construtor de Relatórios no SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10428"
helpviewer_keywords:
- overview of Report Builder
- getting started
ms.assetid: 55bf4f9c-d037-412f-ae57-3fc39ce32fa5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b2fb8994272eb24594239551d623021f7b87694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570492"
---
# <a name="report-builder-in-sql-server-2014"></a>Construtor de Relatórios no SQL Server 2014
  O Construtor de Relatórios é um ambiente de criação de relatório para usuários comerciais que preferem trabalhar no ambiente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office. Quando você cria um relatório, especifica onde obter os dados, que dados obter e como exibir os dados. Ao executar o relatório, o processador de relatório obtém todas as informações especificadas, recupera os dados e os combina ao layout de relatório para gerar o relatório. Você pode visualizar os relatórios no Construtor de Relatórios ou publicá-los em um servidor de relatório ou em um servidor de relatório no modo integrado do SharePoint, onde outras pessoas poderão executá-lo.  
  
 O relatório nesta ilustração caracteriza uma matriz com grupos de linhas e colunas, minigráficos, indicadores e um gráfico de pizza resumido na célula de canto, acompanhada de um mapa com dois conjuntos de dados geográficos representados pela cor e pelo tamanho do círculo.  
  
 ![rs_GettingStartedReport](../media/rs-gettingstartedreport.gif "rs_GettingStartedReport")  
  
##  <a name="jump-start-report-creation"></a><a name="JumpStartReptCreation"></a>Iniciar a criação de relatório  
  
-   **Inicie seu relatório withreport partes** criadas por outra pessoa na sua equipe. As partes de relatório são itens de relatório que foram publicados separadamente em um servidor de relatório ou em um site do SharePoint integrado a um servidor de relatório. Elas podem ser reutilizadas em outros relatórios. Itens de relatório como tabelas, matrizes, gráficos e imagens podem ser publicados como partes de relatório.  
  
-   **Comece com um conjunto de um DataSet compartilhado** criado por outra pessoa na sua equipe. Os conjuntos de dados compartilhados são consultas baseadas em uma fonte de dados compartilhados salvos em um servidor de relatório ou em um site do SharePoint integrado a um servidor de relatório.  
  
-   **Comece com o Assistente de tabela, matriz ou gráfico**. Escolha uma conexão de fonte de dados, arraste e solte campos para criar uma consulta de conjunto de dados, selecione um layout e um estilo e personalize seu relatório.  
  
-   **Comece com o Assistente de mapa** para criar relatórios que exibem dados agregados em uma tela de fundo geográfica ou geométrica. Os dados de mapa podem ser dados espaciais de uma consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] ou um arquivo de forma ESRI (Environmental Systems Research Institute, Inc.). Também é possível adicionar um plano de fundo de peça de mapa do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Bing.  
  

  
##  <a name="design-your-report"></a><a name="DesignRept"></a>Criar seu relatório  
  
-   **Crie relatórios com tabela, matriz, gráfico e layouts de relatório de forma livre.** Crie relatórios de tabela para dados baseados em coluna, relatórios de matriz (como relatórios de Tabela Dinâmica ou referência cruzada) para dados resumidos, relatórios de gráfico para dados gráficos e relatórios de forma livre para qualquer outra coisa. Os relatórios podem inserir outros relatórios e gráficos, junto com listas, gráficos e controles para aplicativos dinâmicos baseados na Web.  
  
-   **Gere relatórios de uma variedade de fontes de dados.** Crie relatórios usando dados de qualquer tipo de fonte de dados que tenha um [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provedor de dados gerenciado, provedor de OLE DB ou fonte de dados ODBC. Você pode criar relatórios que usam dados relacionais e multidimensionais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], Oracle, Hyperion e outros bancos de dados. Você pode usar uma extensão de processamento de dados XML para recuperar dados de qualquer fonte de dados XML. Também é possível usar funções com valor de tabela para projetar fontes de dados personalizadas.  
  
-   **Modifique relatórios existentes.** Usando Construtor de Relatórios, você pode personalizar e atualizar relatórios que foram criados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] Report Designer.  
  
-   **Modifique seus dados** filtrando, agrupando e classificando dados ou adicionando fórmulas ou expressões.  
  
-   **Adicione gráficos, medidores, minigráficos e indicadores** para resumir dados em um formato visual e apresentar grandes volumes de informações agregadas de forma concisa.  
  
-   **Adicione recursos interativos**, como mapas do documento, botões para mostrar/ocultar e links de detalhamento para sub-relatórios e relatórios detalhados. Use parâmetros e filtros para filtrar dados para exibições personalizadas.  
  
-   **Insira ou referencie imagens** e outros recursos, incluindo conteúdo externo.  
  

  
##  <a name="manage-your-report"></a><a name="ManageRpt"></a>Gerenciar seu relatório  
  
-   **Salve a definição do relatório** no computador ou no servidor de relatório, no qual você pode gerenciá-lo e compartilhá-lo com outras pessoas.  
  
-   **Escolha um formato de apresentação** ao abrir o relatório ou depois de abri-lo. Selecione formatos orientados à Web, orientados à página e de aplicativo da área de trabalho. Os formatos incluem HTML, MHTML, PDF, XML, CSV, TIFF, Word e Excel.  
  
-   **Configure assinaturas.** Depois de publicar o relatório no servidor de relatório ou em um servidor de relatório no modo integrado do SharePoint, você poderá configurá-lo para ser executado em um determinado horário, criar um histórico do relatório e configurar assinaturas de email.  
  
-   **Gere feeds de dados** de seu relatório usando a extensão de renderização Atom do Reporting Services.  
  
> [!NOTE]  
>  Os relatórios publicados são gerenciados em um servidor de relatório ou um servidor de relatório no modo integrado do SharePoint por um administrador do servidor de relatório. Os administradores de servidor de relatório podem definir a segurança, estabelecer as propriedades e agendar operações, como histórico de relatório e entrega de relatório de email. Também podem criar agendas e fontes de dados compartilhadas e disponibilizá-las para uso geral. Os administradores também gerenciam todas as pastas de servidor de relatório. A possibilidade de executar tarefas de gerenciamento depende das permissões de usuário.  
  

  
##  <a name="in-this-section"></a><a name="InThisSection"></a> Nesta seção  
 [Novidades no Construtor de Relatórios para SQL Server 2014](../what-s-new-in-report-builder-for-sql-server-2014.md)  
 Descreve os novos recursos nesta versão do Construtor de Relatórios, inclusive mapas.  
  
 [Tutorial: Criando um relatório de gráfico rápido offline](tutorial-create-a-quick-chart-report-offline-report-builder.md)  
 Apresenta o Construtor de Relatórios e os assistentes disponíveis para ajudá-lo a criar relatórios. O tutorial fornece um conjunto de dados com o qual trabalhar, de modo que você não precise se conectar a uma fonte de dados para começar.  
  
 [Planejando um relatório &#40;Construtor de Relatórios&#41;](../report-design/planning-a-report-report-builder.md)  
 Fornece informações sobre o que você deve considerar antes de começar a criar seu relatório.  
  
 [Conceitos de criação de relatórios &#40;Construtor de Relatórios e SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md)  
 Define os conceitos-chave usados em toda a documentação do Construtor de Relatórios.  
  
 [Modo de exibição de Design de relatório &#40;Construtor de Relatórios&#41;](report-design-view-report-builder.md)  
 Explica os diferentes painéis e regiões da exibição de design de relatório.  
  
 [Modo de exibição de design de conjunto de &#40;compartilhado Construtor de Relatórios&#41;](shared-dataset-design-view-report-builder.md)  
 Explica os diferentes painéis e regiões da exibição de design do conjunto de dados compartilhados.  
  
 [Atalhos de teclado &#40;Construtor de Relatórios&#41;](keyboard-shortcuts-report-builder.md)  
 Descreve as teclas de atalho disponíveis para navegar e criar relatórios no Construtor de Relatórios.  
  
 [Iniciar Construtor de Relatórios &#40;Construtor de Relatórios&#41;](start-report-builder.md)  
 Explica como iniciar as duas versões diferentes do Construtor de Relatórios: autônoma e [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)].  
  
  
