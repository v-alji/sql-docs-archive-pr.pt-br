---
title: Editar uma conexão de fonte de dados existente (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.selexistconn.f1
ms.assetid: 97e63f18-a01d-4c91-a411-e7e6d40a0647
author: minewiskan
ms.author: owend
ms.openlocfilehash: 675a0d1119e25a92231d3e74a79739cb2e96b6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582189"
---
# <a name="edit-an-existing-data-source-connection-ssas-tabular"></a><span data-ttu-id="786bc-102">Editar uma conexão de fonte de dados existente (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="786bc-102">Edit an Existing Data Source Connection (SSAS Tabular)</span></span>
  <span data-ttu-id="786bc-103">Este tópico descreve como editar as propriedades de uma conexão de fonte de dados existentes em um modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="786bc-103">This topic describes how to edit the properties of an existing data source connection in a tabular model.</span></span>  
  
 <span data-ttu-id="786bc-104">Depois de criar uma conexão com uma fonte de dados externa, você poderá modificá-la destas maneiras:</span><span class="sxs-lookup"><span data-stu-id="786bc-104">After you have created a connection to an external data source, you can later modify that connection in these ways:</span></span>  
  
-   <span data-ttu-id="786bc-105">Você pode alterar as informações da conexão, inclusive o arquivo, o feed ou o banco de dados usado como fonte, suas propriedades ou outras opções de conexão específicas do provedor.</span><span class="sxs-lookup"><span data-stu-id="786bc-105">You can change the connection information, including the file, feed, or database used as a source, its properties, or other provider-specific connection options.</span></span>  
  
-   <span data-ttu-id="786bc-106">Você pode alterar os mapeamentos de coluna e tabela, e remove referências a colunas que já não são mais usadas.</span><span class="sxs-lookup"><span data-stu-id="786bc-106">You can change table and column mappings, and remove references to columns that are no longer used.</span></span>  
  
-   <span data-ttu-id="786bc-107">Você pode alterar as tabelas, exibições ou colunas que obtém da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="786bc-107">You can change the tables, views, or columns that you get from the external data source.</span></span>  
  
## <a name="modify-a-connection"></a><span data-ttu-id="786bc-108">Modificar uma conexão</span><span class="sxs-lookup"><span data-stu-id="786bc-108">Modify a Connection</span></span>  
 <span data-ttu-id="786bc-109">Este procedimento descreve como modificar uma conexão de fonte de dados de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="786bc-109">This procedure describes how to modify a database data source connection.</span></span> <span data-ttu-id="786bc-110">Algumas opções para trabalhar com fontes de dados diferem dependendo do tipo de fonte de dados; porém, você deve poder identificar essas diferenças facilmente.</span><span class="sxs-lookup"><span data-stu-id="786bc-110">Some options for working with data sources differ depending on the data source type; however, you should be able to easily identify those differences.</span></span>  
  
#### <a name="to-change-the-external-data-source-used-by-a-current-connection"></a><span data-ttu-id="786bc-111">Para alterar a fonte de dados externa usada por uma conexão atual</span><span class="sxs-lookup"><span data-stu-id="786bc-111">To change the external data source used by a current connection</span></span>  
  
1.  <span data-ttu-id="786bc-112">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique no menu **Modelo** e em **Conexões Existentes**.</span><span class="sxs-lookup"><span data-stu-id="786bc-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="786bc-113">Selecione a conexão de fonte de dados que você deseja modificar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="786bc-113">Select the data source connection you want to modify, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="786bc-114">Na caixa de diálogo **Editar Conexão** , clique em **Procurar** para localizar outro banco de dados do mesmo tipo, mas com um nome ou local diferente.</span><span class="sxs-lookup"><span data-stu-id="786bc-114">In the **Edit Connection** dialog box, click **Browse** to locate another database of the same type but with a different name or location.</span></span>  
  
     <span data-ttu-id="786bc-115">Assim que você alterar o arquivo de banco de dados, será exibida uma mensagem indicando que é necessário salvar e atualizar as tabelas para ver os novos dados.</span><span class="sxs-lookup"><span data-stu-id="786bc-115">As soon as you change the database file, a message appears indicating that you need to save and refresh the tables in order to see the new data.</span></span>  
  
4.  <span data-ttu-id="786bc-116">Clique em **Salvar**e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="786bc-116">Click **Save**, and then click **Close**.</span></span>  
  
5.  <span data-ttu-id="786bc-117">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no **Modelo**, em **Processar**e em **Processar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="786bc-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model**, click **Process**, and then click **Process All**.</span></span>  
  
     <span data-ttu-id="786bc-118">As tabelas são reprocessadas usando a nova fonte de dados, mas com as seleções de dados originais.</span><span class="sxs-lookup"><span data-stu-id="786bc-118">The tables are re-processed using the new data source, but with the original data selections.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="786bc-119">Se a nova fonte de dados contiver tabelas adicionais que não estavam presentes na fonte de dados original, você deverá reabrir a conexão alterada e adicionar as tabelas.</span><span class="sxs-lookup"><span data-stu-id="786bc-119">If the new data source contains any additional tables that were not present in the original data source, you must re-open the changed connection and add the tables.</span></span>  
  
## <a name="edit-table-and-column-mappings-bindings"></a><span data-ttu-id="786bc-120">Editar mapeamentos de coluna e tabela (associações)</span><span class="sxs-lookup"><span data-stu-id="786bc-120">Edit Table and Column Mappings (Bindings)</span></span>  
 <span data-ttu-id="786bc-121">Este procedimento descreve como editar os mapeamentos depois que você alterar uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="786bc-121">This procedure describes how to edit the mappings after you change a data source.</span></span>  
  
#### <a name="to-edit-column-mappings-when-a-data-source-changes"></a><span data-ttu-id="786bc-122">Para editar mapeamentos de coluna quando uma fonte de dados é alterada</span><span class="sxs-lookup"><span data-stu-id="786bc-122">To edit column mappings when a data source changes</span></span>  
  
1.  <span data-ttu-id="786bc-123">No Designer de Modelo, selecione uma tabela.</span><span class="sxs-lookup"><span data-stu-id="786bc-123">In the model designer, select a table.</span></span>  
  
2.  <span data-ttu-id="786bc-124">Clique no menu **Tabela** e clique em **Propriedades da Tabela**.</span><span class="sxs-lookup"><span data-stu-id="786bc-124">Click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
     <span data-ttu-id="786bc-125">O nome da tabela selecionada é exibido na caixa **Nome da Tabela** .</span><span class="sxs-lookup"><span data-stu-id="786bc-125">The name of the selected table is displayed in the **Table Name** box.</span></span> <span data-ttu-id="786bc-126">A caixa **Nome da Origem** contém o nome da tabela na fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="786bc-126">The **Source Name** box contains the name of the table in the external data source.</span></span> <span data-ttu-id="786bc-127">Se as colunas forem nomeadas diferentemente na origem e no modelo, você poderá alternar entre os dois conjuntos de nomes de colunas selecionando a opção **Origem** ou **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="786bc-127">If columns are named differently in the source and in the model, you can toggle between the two sets of column names by selecting the options **Source** or **Model**.</span></span>  
  
3.  <span data-ttu-id="786bc-128">Para alterar a tabela usada como uma fonte de dados, em **Nome da Origem**, selecione uma tabela diferente da atual.</span><span class="sxs-lookup"><span data-stu-id="786bc-128">To change the table that is used as a data source, for **Source Name**, select a different table than the current one.</span></span>  
  
4.  <span data-ttu-id="786bc-129">Altere os mapeamentos de coluna se necessário:</span><span class="sxs-lookup"><span data-stu-id="786bc-129">Change column mappings if needed:</span></span>  
  
    1.  <span data-ttu-id="786bc-130">Para adicionar colunas que estão presentes na origem mas não no modelo, marque a caixa de seleção ao lado do nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="786bc-130">To add columns that are present in the source but not in the model, select the checkbox beside the column name.</span></span>  
  
         <span data-ttu-id="786bc-131">Os dados reais serão carregados no modelo na próxima vez que você atualizá-la.</span><span class="sxs-lookup"><span data-stu-id="786bc-131">The actual data will be loaded into the model the next time you refresh.</span></span>  
  
    2.  <span data-ttu-id="786bc-132">Se algumas colunas no modelo não estiverem mais disponíveis na fonte de dados atual, será exibida uma mensagem na área de notificação listando as colunas inválidas.</span><span class="sxs-lookup"><span data-stu-id="786bc-132">If some columns in the model are no longer available in the current data source, a message appears in the notification area that lists the invalid columns.</span></span> <span data-ttu-id="786bc-133">Não é necessário fazer mais nada.</span><span class="sxs-lookup"><span data-stu-id="786bc-133">You do not need to do anything else.</span></span>  
  
5.  <span data-ttu-id="786bc-134">Clique em **Salvar** para aplicar as alterações ao modelo.</span><span class="sxs-lookup"><span data-stu-id="786bc-134">Click **Save** to apply the changes to your model.</span></span>  
  
     <span data-ttu-id="786bc-135">Quando você salvar o conjunto atual de propriedades de tabela, uma mensagem poderá aparecer indicando que você precisa processar as tabelas.</span><span class="sxs-lookup"><span data-stu-id="786bc-135">When you save the current set of table properties, a message may appear indicating that you need to process the tables.</span></span> <span data-ttu-id="786bc-136">Clique em **Processar** para carregar dados atualizados no modelo.</span><span class="sxs-lookup"><span data-stu-id="786bc-136">Click **Process** to load updated data into your model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786bc-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="786bc-137">See Also</span></span>  
 <span data-ttu-id="786bc-138">[Processar dados &#40;SSAS de tabela&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="786bc-138">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="786bc-139">Fontes de dados com suporte &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="786bc-139">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
