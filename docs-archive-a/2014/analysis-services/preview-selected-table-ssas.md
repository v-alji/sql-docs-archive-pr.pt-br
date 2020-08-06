---
title: Visualizar tabela selecionada (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.previewselecttable.f1
ms.assetid: b6b34b5a-43b3-4a75-9f3b-b2ad1084b1b6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25eb4d4424223449052ab1f65b41cf270da81fb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685334"
---
# <a name="preview-selected-table-ssas"></a><span data-ttu-id="dcfd1-102">Visualizar Tabela Selecionada (SSAS)</span><span class="sxs-lookup"><span data-stu-id="dcfd1-102">Preview Selected Table (SSAS)</span></span>
  <span data-ttu-id="dcfd1-103">Esta página do **Assistente de Importação de Tabela** o habilita a visualizar os dados na tabela selecionada, para selecionar as colunas a serem incluídas na importação de dados e para filtrar os dados nas colunas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-103">This page of the **Table Import Wizard** enables you to preview the data in the selected table, to select the columns to include in the data import, and to filter data in the selected columns.</span></span> <span data-ttu-id="dcfd1-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="dcfd1-105">Nem todas as linhas na tabela são exibidas.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-105">Not all the rows in the table are displayed.</span></span> <span data-ttu-id="dcfd1-106">No entanto, os filtros definidos serão aplicados a todos os dados na tabela durante a importação.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-106">However, the filters that you set will be applied to all of the data in the table during import.</span></span>  
  
 <span data-ttu-id="dcfd1-107">Para fontes de dados que usam a autenticação do Windows, as credenciais do usuário atual são usadas para buscar os dados exibidos na caixa de diálogo Visualizar e Filtrar.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the data displayed in the Preview and Filter dialog.</span></span> <span data-ttu-id="dcfd1-108">Para outras fontes de dados, as credenciais fornecidas na cadeia de conexão são usadas para buscar os dados.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
 <span data-ttu-id="dcfd1-109">A aparência de dados nesta página não garante que a importação terá êxito.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-109">The appearance of data on this page does not guarantee import will succeed.</span></span> <span data-ttu-id="dcfd1-110">Se o nome do usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do banco de dados selecionado, a importação falhará.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-110">If the user name specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="dcfd1-111">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="dcfd1-111">UI element list</span></span>  
 <span data-ttu-id="dcfd1-112">**Caixa de seleção no cabeçalho da coluna**</span><span class="sxs-lookup"><span data-stu-id="dcfd1-112">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="dcfd1-113">Marque a caixa de seleção para incluir a coluna na importação de dados.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-113">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="dcfd1-114">Desmarque a caixa de seleção para remover a coluna da importação de dados.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-114">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="dcfd1-115">**Botão de seta para baixo no cabeçalho da coluna**</span><span class="sxs-lookup"><span data-stu-id="dcfd1-115">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="dcfd1-116">Filtre dados na coluna.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-116">Filter data in the column.</span></span>  
  
 <span data-ttu-id="dcfd1-117">**Limpar Filtros de Linha**</span><span class="sxs-lookup"><span data-stu-id="dcfd1-117">**Clear Row Filters**</span></span>  
 <span data-ttu-id="dcfd1-118">Remova todos os filtros aplicados aos dados nas colunas.</span><span class="sxs-lookup"><span data-stu-id="dcfd1-118">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
