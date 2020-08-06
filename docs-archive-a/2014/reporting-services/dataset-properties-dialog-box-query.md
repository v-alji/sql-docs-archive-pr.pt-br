---
title: Caixa de diálogo Propriedades do conjunto de, consulta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10160"
- sql12.rtp.rptdesigner.datasetproperties.query.f1
ms.assetid: 1fa34a4b-7de0-4e92-99fa-bc28a206773f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bffb14155d37e67333eb626747e1fcc54e618bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583387"
---
# <a name="dataset-properties-dialog-box-query"></a>Caixa de diálogo Propriedades do Conjunto de Dados, Consulta
  Selecione **Consulta** na caixa de diálogo **Propriedades do Conjunto de Dados** para escolher uma fonte de dados e criar uma consulta.  
  
 A caixa de diálogo **Propriedades do Conjunto de Dados** inclui o seguinte:  
  
-   [Caixa de diálogo Propriedades do Conjunto de Dados, Parâmetros](report-data/dataset-properties-dialog-box-parameters.md)  
  
-   [Caixa de diálogo Propriedades do Conjunto de Dados, Campos](../../2014/reporting-services/dataset-properties-dialog-box-fields.md)  
  
-   [Caixa de diálogo Propriedades do Conjunto de Dados, Opções](../../2014/reporting-services/dataset-properties-dialog-box-options.md)  
  
-   [Caixa de diálogo Propriedades do Conjunto de Dados, Filtros](report-data/dataset-properties-dialog-box-filters.md)  
  
## <a name="options"></a>Opções  
 **Nome**  
 Digite um nome para o conjunto de dados. O nome não pode ser igual a um nome de alguma região de dados ou grupo no relatório.  
  
 **Fonte de Dados**  
 Selecione a fonte de dados na qual deseja basear o conjunto de dados. Para criar uma nova fonte de dados, clique em **Novo**.  
  
 **Tipo de consulta**  
 Selecione o tipo de comando ou consulta que deseja usar no conjunto de dados. Selecione **Texto** para executar uma consulta para recuperar dados do banco de dados. Selecione **Tabela** para usar o recurso **TableDirect** do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para selecionar todos os campos de uma tabela. Selecione **Procedimento Armazenado** para executar um procedimento armazenado pelo nome. **Texto** é selecionado por padrão e é usado para a maioria das consultas. Para editar a consulta de fonte de dados selecionada, clique em **Designer de Consulta**.  
  
> [!NOTE]  
>  Nem todos os tipos de consulta são suportados por todas as fontes de dados. Por exemplo, **Tabela** é suportado somente pelos tipos de fonte de dados **OLE DB** e **ODBC**.  
  
 **Consulta**  
 Esta opção é exibida quando você escolhe o tipo de comando **Texto** . Digite uma consulta ou importe uma consulta preexistente clicando em **Importar**. Clique no botão **expressão** (*FX*) para editar a expressão.  
  
> [!NOTE]  
>  Se você usou um designer de consulta para criar uma consulta, o texto da consulta será exibido nesta caixa.  
  
 **Nome da tabela**  
 Digite o nome da tabela que deseja usar como um conjunto de dados. Esta opção é exibida quando você seleciona **Tabela**.  
  
 **Selecionar ou digitar nome do procedimento armazenado**  
 Digite ou escolha o nome do procedimento armazenado que deseja usar. Clique no botão **expressão** (*FX*) para editar a expressão. Esta opção é exibida quando você escolhe o tipo de comando Procedimento Armazenado.  
  
 **Tempo limite (em segundos)**  
 Digite o número de segundos até que a consulta expire. O padrão é 30 segundos. O valor para **Tempo Limite** deve ser vazio ou maior que zero. Se for vazio, a consulta não terá um tempo limite.  
  
## <a name="see-also"></a>Consulte Também  
 [Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md)   
 [Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-data/report-datasets-ssrs.md)   
 [Designers de consulta &#40;Construtor de Relatórios&#41;](../../2014/reporting-services/query-designers-report-builder.md)   
 [Designers de Consulta do Reporting Services](../../2014/reporting-services/reporting-services-query-designers.md)  
  
  
