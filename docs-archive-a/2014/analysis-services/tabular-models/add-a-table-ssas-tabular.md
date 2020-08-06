---
title: Adicionar uma tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d713c432-db99-4983-acc1-52b0fdd58bd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80c22c992a89ed2cb3db84809b47a7cd08cb514
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581476"
---
# <a name="add-a-table-ssas-tabular"></a><span data-ttu-id="e342b-102">Adicionar uma tabela (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="e342b-102">Add a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="e342b-103">Este tópico descreve como adicionar uma tabela de uma fonte de dados da qual você tem dados previamente importados em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="e342b-103">This topic describes how to add a table from a data source from which you have previously imported data into your model.</span></span> <span data-ttu-id="e342b-104">Para adicionar uma tabela da mesma fonte de dados, você pode usar a conexão de fonte de dados existente.</span><span class="sxs-lookup"><span data-stu-id="e342b-104">To add a table from the same data source, you can use the existing data source connection.</span></span> <span data-ttu-id="e342b-105">É recomendado sempre usar uma única conexão ao importar qualquer número de tabelas de uma única fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e342b-105">It is recommended you always use a single connection when importing any number of tables from a single data source.</span></span>  
  
### <a name="to-add-a-table-from-an-existing-data-source"></a><span data-ttu-id="e342b-106">Para adicionar uma tabela de uma fonte de dados existente</span><span class="sxs-lookup"><span data-stu-id="e342b-106">To add a table from an existing data source</span></span>  
  
1.  <span data-ttu-id="e342b-107">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique no menu **Modelo** e em **Conexões Existentes**.</span><span class="sxs-lookup"><span data-stu-id="e342b-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="e342b-108">Na página **Conexões existentes** , selecione a conexão para a fonte de dados que tem a tabela que você deseja adicionar e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e342b-108">On the **Existing Connections** page, select the connection to the data source that has the table you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="e342b-109">Na página **Selecionar Tabelas e Exibições** , selecione a tabela da fonte de dados que você deseja adicionar a seu modelo.</span><span class="sxs-lookup"><span data-stu-id="e342b-109">On the **Select Tables and Views** page, select the table from the data source you want to add to your model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e342b-110">A página **Selecionar Tabelas e Exibições** não mostrará tabelas que foram importadas previamente como marcadas.</span><span class="sxs-lookup"><span data-stu-id="e342b-110">The **Select Tables and Views** page will not show tables that were previously imported as checked.</span></span>  <span data-ttu-id="e342b-111">Se você selecionar uma tabela que foi importada previamente usando esta conexão, e você não deu à tabela um nome amigável diferente, um 1 será acrescentado ao nome amigável.</span><span class="sxs-lookup"><span data-stu-id="e342b-111">If you select a table that was previously imported using this connection, and you did not give the table a different friendly name, a 1 will be appended to the friendly name.</span></span> <span data-ttu-id="e342b-112">Você não precisa selecionar novamente nenhuma tabela que foi previamente importada usando esta conexão.</span><span class="sxs-lookup"><span data-stu-id="e342b-112">You do not need to re-select any tables that were previously imported by using this connection.</span></span>  
  
4.  <span data-ttu-id="e342b-113">Se necessário, use **Visualizar e Filtrar** para selecionar somente certas colunas ou aplicar filtros aos dados a serem importados.</span><span class="sxs-lookup"><span data-stu-id="e342b-113">If necessary, use **Preview & Filter** to select only certain columns or apply filters to the data to be imported.</span></span>  
  
5.  <span data-ttu-id="e342b-114">Clique em **Concluir** para importar a nova tabela.</span><span class="sxs-lookup"><span data-stu-id="e342b-114">Click **Finish** to import the new table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e342b-115">Ao importar várias tabelas ao mesmo tempo de uma única fonte de dados, as relações entre essas tabelas na origem serão automaticamente criadas no modelo.</span><span class="sxs-lookup"><span data-stu-id="e342b-115">When importing multiple tables at the same time from a single data source, any relationships between those tables at the source will automatically be created in the model.</span></span> <span data-ttu-id="e342b-116">Ao adicionar uma tabela posteriormente, porém, você pode precisar criar relações manualmente no modelo entre tabelas recém-adicionadas e as tabelas que foram previamente importadas.</span><span class="sxs-lookup"><span data-stu-id="e342b-116">When adding a table later; however, you may need to manually create relationships in the model between newly added tables and the tables that were previously imported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e342b-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e342b-117">See Also</span></span>  
 <span data-ttu-id="e342b-118">[Importar dados &#40;SSAS de tabela&#41;](../import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="e342b-118">[Import Data &#40;SSAS Tabular&#41;](../import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="e342b-119">Excluir uma tabela &#40;SSAS Tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="e342b-119">Delete a Table &#40;SSAS Tabular&#41;</span></span>](delete-a-table-ssas-tabular.md)  
  
  
