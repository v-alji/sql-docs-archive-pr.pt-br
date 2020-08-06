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
# <a name="dataset-properties-dialog-box-query"></a><span data-ttu-id="af7e8-102">Caixa de diálogo Propriedades do Conjunto de Dados, Consulta</span><span class="sxs-lookup"><span data-stu-id="af7e8-102">Dataset Properties Dialog Box, Query</span></span>
  <span data-ttu-id="af7e8-103">Selecione **Consulta** na caixa de diálogo **Propriedades do Conjunto de Dados** para escolher uma fonte de dados e criar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="af7e8-103">Select **Query** on the **Dataset Properties** dialog box to choose a data source and create a query.</span></span>  
  
 <span data-ttu-id="af7e8-104">A caixa de diálogo **Propriedades do Conjunto de Dados** inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="af7e8-104">The **Dataset Properties** dialog box includes the following:</span></span>  
  
-   [<span data-ttu-id="af7e8-105">Caixa de diálogo Propriedades do Conjunto de Dados, Parâmetros</span><span class="sxs-lookup"><span data-stu-id="af7e8-105">Dataset Properties Dialog Box, Parameters</span></span>](report-data/dataset-properties-dialog-box-parameters.md)  
  
-   [<span data-ttu-id="af7e8-106">Caixa de diálogo Propriedades do Conjunto de Dados, Campos</span><span class="sxs-lookup"><span data-stu-id="af7e8-106">Dataset Properties Dialog Box, Fields</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-fields.md)  
  
-   [<span data-ttu-id="af7e8-107">Caixa de diálogo Propriedades do Conjunto de Dados, Opções</span><span class="sxs-lookup"><span data-stu-id="af7e8-107">Dataset Properties Dialog Box, Options</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-options.md)  
  
-   [<span data-ttu-id="af7e8-108">Caixa de diálogo Propriedades do Conjunto de Dados, Filtros</span><span class="sxs-lookup"><span data-stu-id="af7e8-108">Dataset Properties Dialog Box, Filters</span></span>](report-data/dataset-properties-dialog-box-filters.md)  
  
## <a name="options"></a><span data-ttu-id="af7e8-109">Opções</span><span class="sxs-lookup"><span data-stu-id="af7e8-109">Options</span></span>  
 <span data-ttu-id="af7e8-110">**Nome**</span><span class="sxs-lookup"><span data-stu-id="af7e8-110">**Name**</span></span>  
 <span data-ttu-id="af7e8-111">Digite um nome para o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="af7e8-111">Type a name for the dataset.</span></span> <span data-ttu-id="af7e8-112">O nome não pode ser igual a um nome de alguma região de dados ou grupo no relatório.</span><span class="sxs-lookup"><span data-stu-id="af7e8-112">The name cannot be the same as a name for any data region or group in the report.</span></span>  
  
 <span data-ttu-id="af7e8-113">**Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="af7e8-113">**Data Source**</span></span>  
 <span data-ttu-id="af7e8-114">Selecione a fonte de dados na qual deseja basear o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="af7e8-114">Select the data source on which to base the dataset.</span></span> <span data-ttu-id="af7e8-115">Para criar uma nova fonte de dados, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="af7e8-115">To create a new data source, click **New**.</span></span>  
  
 <span data-ttu-id="af7e8-116">**Tipo de consulta**</span><span class="sxs-lookup"><span data-stu-id="af7e8-116">**Query type**</span></span>  
 <span data-ttu-id="af7e8-117">Selecione o tipo de comando ou consulta que deseja usar no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="af7e8-117">Select the type of command or query to use for the dataset.</span></span> <span data-ttu-id="af7e8-118">Selecione **Texto** para executar uma consulta para recuperar dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="af7e8-118">Select **Text** to run a query to retrieve data from the database.</span></span> <span data-ttu-id="af7e8-119">Selecione **Tabela** para usar o recurso **TableDirect** do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para selecionar todos os campos de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="af7e8-119">Select **Table** to use the **TableDirect** feature of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to select all the fields within a table.</span></span> <span data-ttu-id="af7e8-120">Selecione **Procedimento Armazenado** para executar um procedimento armazenado pelo nome.</span><span class="sxs-lookup"><span data-stu-id="af7e8-120">Select **Stored Procedure** to run a stored procedure by name.</span></span> <span data-ttu-id="af7e8-121">**Texto** é selecionado por padrão e é usado para a maioria das consultas.</span><span class="sxs-lookup"><span data-stu-id="af7e8-121">**Text** is selected by default and is used for most queries.</span></span> <span data-ttu-id="af7e8-122">Para editar a consulta de fonte de dados selecionada, clique em **Designer de Consulta**.</span><span class="sxs-lookup"><span data-stu-id="af7e8-122">To edit the selected data source query, click **Query Designer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af7e8-123">Nem todos os tipos de consulta são suportados por todas as fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="af7e8-123">Not all query types are supported by all data sources.</span></span> <span data-ttu-id="af7e8-124">Por exemplo, **Tabela** é suportado somente pelos tipos de fonte de dados **OLE DB** e **ODBC**.</span><span class="sxs-lookup"><span data-stu-id="af7e8-124">For example, **Table** is supported only by data source types **OLE DB** and **ODBC**.</span></span>  
  
 <span data-ttu-id="af7e8-125">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="af7e8-125">**Query**</span></span>  
 <span data-ttu-id="af7e8-126">Esta opção é exibida quando você escolhe o tipo de comando **Texto** .</span><span class="sxs-lookup"><span data-stu-id="af7e8-126">This option appears when you choose the **Text** command type option.</span></span> <span data-ttu-id="af7e8-127">Digite uma consulta ou importe uma consulta preexistente clicando em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="af7e8-127">Type a query or import a pre-existing query by clicking **Import**.</span></span> <span data-ttu-id="af7e8-128">Clique no botão **expressão** (*FX*) para editar a expressão.</span><span class="sxs-lookup"><span data-stu-id="af7e8-128">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af7e8-129">Se você usou um designer de consulta para criar uma consulta, o texto da consulta será exibido nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="af7e8-129">If you used a query designer to build a query, the text of the query appears in this box.</span></span>  
  
 <span data-ttu-id="af7e8-130">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="af7e8-130">**Table name**</span></span>  
 <span data-ttu-id="af7e8-131">Digite o nome da tabela que deseja usar como um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="af7e8-131">Enter the name of the table that you want to use as a dataset.</span></span> <span data-ttu-id="af7e8-132">Esta opção é exibida quando você seleciona **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="af7e8-132">This option appears when you select **Table**.</span></span>  
  
 <span data-ttu-id="af7e8-133">**Selecionar ou digitar nome do procedimento armazenado**</span><span class="sxs-lookup"><span data-stu-id="af7e8-133">**Select or enter stored procedure name**</span></span>  
 <span data-ttu-id="af7e8-134">Digite ou escolha o nome do procedimento armazenado que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="af7e8-134">Type or choose the name of the stored procedure that you want to use.</span></span> <span data-ttu-id="af7e8-135">Clique no botão **expressão** (*FX*) para editar a expressão.</span><span class="sxs-lookup"><span data-stu-id="af7e8-135">Click the **Expression** (*fx*) button to edit the expression.</span></span> <span data-ttu-id="af7e8-136">Esta opção é exibida quando você escolhe o tipo de comando Procedimento Armazenado.</span><span class="sxs-lookup"><span data-stu-id="af7e8-136">This option appears when you choose the Stored Procedure command type option.</span></span>  
  
 <span data-ttu-id="af7e8-137">**Tempo limite (em segundos)**</span><span class="sxs-lookup"><span data-stu-id="af7e8-137">**Time out (in seconds)**</span></span>  
 <span data-ttu-id="af7e8-138">Digite o número de segundos até que a consulta expire. O padrão é 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="af7e8-138">Type the number of seconds until the query times out. The default is 30 seconds.</span></span> <span data-ttu-id="af7e8-139">O valor para **Tempo Limite** deve ser vazio ou maior que zero.</span><span class="sxs-lookup"><span data-stu-id="af7e8-139">The value for **Time out** must be empty or greater than zero.</span></span> <span data-ttu-id="af7e8-140">Se for vazio, a consulta não terá um tempo limite.</span><span class="sxs-lookup"><span data-stu-id="af7e8-140">If it is empty, the query does not time out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7e8-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af7e8-141">See Also</span></span>  
 <span data-ttu-id="af7e8-142">[Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="af7e8-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="af7e8-143">[Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="af7e8-143">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="af7e8-144">[Designers de consulta &#40;Construtor de Relatórios&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="af7e8-144">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 [<span data-ttu-id="af7e8-145">Designers de Consulta do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="af7e8-145">Reporting Services Query Designers</span></span>](../../2014/reporting-services/reporting-services-query-designers.md)  
  
  
