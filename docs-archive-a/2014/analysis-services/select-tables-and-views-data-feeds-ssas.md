---
title: Selecionar tabelas e exibições (feeds de dados) (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviewsdf.f1
ms.assetid: 6c4fafe0-e02e-47d1-b8bc-e70e872690af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 46c317ecf2a87adcde264e8d6d7e822eb833b8b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572724"
---
# <a name="select-tables-and-views-data-feeds-ssas"></a><span data-ttu-id="f5a43-102">Selecionar tabelas e exibições (feeds de dados) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="f5a43-102">Select Tables and Views (Data Feeds) (SSAS)</span></span>
  <span data-ttu-id="f5a43-103">Esta página do **Assistente de Importação de Tabela** o habilita a selecionar as tabelas e exibições das quais você deseja importar dados.</span><span class="sxs-lookup"><span data-stu-id="f5a43-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="f5a43-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="f5a43-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="f5a43-105">A aparência de tabelas e exibições nesta página não garante que essa importação terá êxito.</span><span class="sxs-lookup"><span data-stu-id="f5a43-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="f5a43-106">Se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do banco de dados selecionado, a importação falhará.</span><span class="sxs-lookup"><span data-stu-id="f5a43-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="f5a43-107">Para fontes de dados que usam a autenticação do Windows, as credenciais do usuário atual são usadas para buscar as tabelas e exibições na caixa de diálogo Selecionar Tabelas e Exibições.</span><span class="sxs-lookup"><span data-stu-id="f5a43-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="f5a43-108">Para outras fontes de dados, as credenciais fornecidas na cadeia de conexão são usadas para buscar os dados.</span><span class="sxs-lookup"><span data-stu-id="f5a43-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f5a43-109">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="f5a43-109">UI element list</span></span>  
 <span data-ttu-id="f5a43-110">**URL do feed de dados**</span><span class="sxs-lookup"><span data-stu-id="f5a43-110">**Data feed URL**</span></span>  
 <span data-ttu-id="f5a43-111">Exibe a URL do feed de dados que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="f5a43-111">Displays the URL for the data feed that you selected.</span></span>  
  
 <span data-ttu-id="f5a43-112">**Tabelas e exibições**</span><span class="sxs-lookup"><span data-stu-id="f5a43-112">**Tables and views**</span></span>  
 <span data-ttu-id="f5a43-113">Lista as tabelas e exibições do feed de dados.</span><span class="sxs-lookup"><span data-stu-id="f5a43-113">Lists the tables and views in the data feed.</span></span> <span data-ttu-id="f5a43-114">Marque a caixa de seleção ao lado de cada tabela e exibição que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="f5a43-114">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="f5a43-115">**Tabela de origem**</span><span class="sxs-lookup"><span data-stu-id="f5a43-115">**Source Table**</span></span>  
 <span data-ttu-id="f5a43-116">Especifica o nome da tabela de origem com base no tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f5a43-116">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="f5a43-117">**Nome amigável**</span><span class="sxs-lookup"><span data-stu-id="f5a43-117">**Friendly Name**</span></span>  
 <span data-ttu-id="f5a43-118">Especifica o nome amigável da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="f5a43-118">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="f5a43-119">Por padrão, a coluna exibe o nome da tabela de origem que aparece na coluna **Tabela de Origem** .</span><span class="sxs-lookup"><span data-stu-id="f5a43-119">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span>  
  
 <span data-ttu-id="f5a43-120">**Detalhes do Filtro**</span><span class="sxs-lookup"><span data-stu-id="f5a43-120">**Filter Details**</span></span>  
 <span data-ttu-id="f5a43-121">Exibe o filtro de importação de dados na caixa de diálogo **Detalhes do filtro** quando um filtro é aplicado aos dados sendo importados.</span><span class="sxs-lookup"><span data-stu-id="f5a43-121">Displays the data import filter in the **Filter Details** dialog box, when a filter has been applied to the data that is being imported.</span></span> <span data-ttu-id="f5a43-122">Para obter mais informações, consulte [Detalhes do filtro &#40;SSAS&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="f5a43-122">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="f5a43-123">**Visualização e Filtro**</span><span class="sxs-lookup"><span data-stu-id="f5a43-123">**Preview and Filter**</span></span>  
 <span data-ttu-id="f5a43-124">Exibe a caixa de diálogo **Visualizar Tabela Selecionada**, que é usada para aplicar um filtro aos dados que estão sendo importados.</span><span class="sxs-lookup"><span data-stu-id="f5a43-124">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="f5a43-125">Para obter mais informações, consulte [Visualizar Tabela Selecionada &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="f5a43-125">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="f5a43-126">**Selecionar Tabelas Relacionadas**</span><span class="sxs-lookup"><span data-stu-id="f5a43-126">**Select Related Tables**</span></span>  
 <span data-ttu-id="f5a43-127">Selecione as tabelas relacionadas às tabelas e exibições que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="f5a43-127">Select tables that are related to the tables and views that you have selected.</span></span>  
  
  
