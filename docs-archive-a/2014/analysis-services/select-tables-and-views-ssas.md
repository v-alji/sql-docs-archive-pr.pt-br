---
title: Selecionar tabelas e exibições (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviews.f1
ms.assetid: 5e8121cc-03f0-4168-98cf-63c5c032bb0b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 891da51478670122f5dbce8fdd7be55c98c898c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684383"
---
# <a name="select-tables-and-views-ssas"></a><span data-ttu-id="27511-102">Selecionar tabelas e exibições (SSAS)</span><span class="sxs-lookup"><span data-stu-id="27511-102">Select Tables and Views (SSAS)</span></span>
  <span data-ttu-id="27511-103">Esta página do **Assistente de Importação de Tabela** o habilita a selecionar as tabelas e exibições das quais você deseja importar dados.</span><span class="sxs-lookup"><span data-stu-id="27511-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="27511-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="27511-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="27511-105">A aparência de tabelas e exibições nesta página não garante que essa importação terá êxito.</span><span class="sxs-lookup"><span data-stu-id="27511-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="27511-106">Se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do banco de dados selecionado, a importação falhará.</span><span class="sxs-lookup"><span data-stu-id="27511-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="27511-107">Para fontes de dados que usam a autenticação do Windows, as credenciais do usuário atual são usadas para buscar as tabelas e exibições na caixa de diálogo Selecionar Tabelas e Exibições.</span><span class="sxs-lookup"><span data-stu-id="27511-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="27511-108">Para outras fontes de dados, as credenciais fornecidas na cadeia de conexão são usadas para buscar os dados.</span><span class="sxs-lookup"><span data-stu-id="27511-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="27511-109">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="27511-109">UI element list</span></span>  
 <span data-ttu-id="27511-110">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="27511-110">**Server**</span></span>  
 <span data-ttu-id="27511-111">Exibe o servidor ao qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="27511-111">Displays the server that you are connected to.</span></span>  
  
 <span data-ttu-id="27511-112">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="27511-112">**Database**</span></span>  
 <span data-ttu-id="27511-113">Exibe o banco de dados que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="27511-113">Displays the database that you selected.</span></span>  
  
 <span data-ttu-id="27511-114">**Tabelas e Exibições**</span><span class="sxs-lookup"><span data-stu-id="27511-114">**Tables and Views**</span></span>  
 <span data-ttu-id="27511-115">Lista as tabelas e exibições no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="27511-115">Lists the tables and views in the database.</span></span> <span data-ttu-id="27511-116">Marque a caixa de seleção ao lado de cada tabela e exibição que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="27511-116">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="27511-117">**Tabela de origem**</span><span class="sxs-lookup"><span data-stu-id="27511-117">**Source Table**</span></span>  
 <span data-ttu-id="27511-118">Especifica o nome da tabela de origem com base no tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="27511-118">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="27511-119">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="27511-119">**Schema**</span></span>  
 <span data-ttu-id="27511-120">Especifica o esquema no qual a tabela de origem está contida.</span><span class="sxs-lookup"><span data-stu-id="27511-120">Specifies the schema in which the source table is contained.</span></span> <span data-ttu-id="27511-121">Dependendo do tipo de banco de dados, um esquema funciona como um contêiner para outros objetos, como tabelas, além de também se rpossível indicar a propriedade desses objetos.</span><span class="sxs-lookup"><span data-stu-id="27511-121">Depending on the type of database, a schema functions as a container for other objects, such as tables, and can also indicate ownership of those objects.</span></span>  
  
 <span data-ttu-id="27511-122">**Nome amigável**</span><span class="sxs-lookup"><span data-stu-id="27511-122">**Friendly Name**</span></span>  
 <span data-ttu-id="27511-123">Especifica o nome amigável da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="27511-123">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="27511-124">Por padrão, a coluna exibe o nome da tabela de origem que aparece na coluna **Tabela de Origem** .</span><span class="sxs-lookup"><span data-stu-id="27511-124">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span> <span data-ttu-id="27511-125">Altere o nome se você quiser usar um nome diferente do nome usado no banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="27511-125">Change the name if you want to use a different name than the name used in the source database.</span></span>  
  
 <span data-ttu-id="27511-126">**Detalhes do Filtro**</span><span class="sxs-lookup"><span data-stu-id="27511-126">**Filter Details**</span></span>  
 <span data-ttu-id="27511-127">Quando um filtro é aplicado aos dados que estão sendo importados, exibe o filtro de importação de dados na caixa de diálogo **Detalhes do Filtro**.</span><span class="sxs-lookup"><span data-stu-id="27511-127">When a filter has been applied to the data that is being imported, displays the data import filter in the **Filter Details** dialog box.</span></span> <span data-ttu-id="27511-128">Para obter mais informações, consulte [Detalhes do filtro &#40;SSAS&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="27511-128">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="27511-129">**Visualização e Filtro**</span><span class="sxs-lookup"><span data-stu-id="27511-129">**Preview and Filter**</span></span>  
 <span data-ttu-id="27511-130">Exibe a caixa de diálogo **Visualizar Tabela Selecionada**, que é usada para aplicar um filtro aos dados que estão sendo importados.</span><span class="sxs-lookup"><span data-stu-id="27511-130">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="27511-131">Para obter mais informações, consulte [Visualizar Tabela Selecionada &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="27511-131">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="27511-132">**Selecionar Tabelas Relacionadas**</span><span class="sxs-lookup"><span data-stu-id="27511-132">**Select Related Tables**</span></span>  
 <span data-ttu-id="27511-133">Seleciona essas tabelas e exibições relacionadas a tabelas e exibições já selecionadas para importação.</span><span class="sxs-lookup"><span data-stu-id="27511-133">Selects for import those tables and views that are related to the tables and views that you have already selected.</span></span>  
  
  
