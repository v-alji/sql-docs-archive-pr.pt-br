---
title: Detalhes de associação de tabela (caixa de diálogo origem da partição) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitiontableselection.f1
ms.assetid: 67d05389-81ae-4a6b-947b-986d37ec72b1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10845e18a2b7c74a8ed3aeec42f710b9706dc94a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572722"
---
# <a name="table-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="3418c-102">Detalhes de Associação de Tabela (caixa de diálogo Origem da Partição) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="3418c-102">Table Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3418c-103">Use a opção **Associação de Tabela** na caixa de diálogo **Origem da Partição** para especificar a tabela de fatos que fornece os dados para a partição.</span><span class="sxs-lookup"><span data-stu-id="3418c-103">Use the **Table Binding** option in the **Partition Source** dialog box to specify the fact table that provides the data for the partition.</span></span> <span data-ttu-id="3418c-104">É possível exibir este painel selecionando **Associação de Tabela** da opção **Tipo de Associação** na caixa de diálogo **Origem da Partição** .</span><span class="sxs-lookup"><span data-stu-id="3418c-104">You can display this pane by selecting **Table Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3418c-105">Opções</span><span class="sxs-lookup"><span data-stu-id="3418c-105">Options</span></span>  
 <span data-ttu-id="3418c-106">**Grupo de medidas**</span><span class="sxs-lookup"><span data-stu-id="3418c-106">**Measure group**</span></span>  
 <span data-ttu-id="3418c-107">Exibe o grupo de medidas desta partição.</span><span class="sxs-lookup"><span data-stu-id="3418c-107">Displays the measure group for this partition.</span></span>  
  
 <span data-ttu-id="3418c-108">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="3418c-108">**Look in**</span></span>  
 <span data-ttu-id="3418c-109">Selecione a fonte de dados ou exibição da fonte de dados que contém as tabelas de origem desta partição.</span><span class="sxs-lookup"><span data-stu-id="3418c-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="3418c-110">A exibição da fonte de dados usada pelo grupo de medidas selecionado é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="3418c-110">The data source view used by the selected measure group is selected by default.</span></span>  
  
 <span data-ttu-id="3418c-111">**Filtrar tabelas**</span><span class="sxs-lookup"><span data-stu-id="3418c-111">**Filter tables**</span></span>  
 <span data-ttu-id="3418c-112">Digite a cadeia de caracteres usada para restringir, por nome de tabela, as tabelas exibidas em **Tabelas disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="3418c-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="3418c-113">**Localizar tabelas**</span><span class="sxs-lookup"><span data-stu-id="3418c-113">**Find tables**</span></span>  
 <span data-ttu-id="3418c-114">Selecione para atualizar a lista de tabelas em **Tabelas disponíveis**, restringindo ainda mais a lista, se uma cadeia de caracteres tiver sido especificada em **Filtrar tabelas**.</span><span class="sxs-lookup"><span data-stu-id="3418c-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="3418c-115">**Tabelas Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="3418c-115">**Available tables**</span></span>  
 <span data-ttu-id="3418c-116">Clique para selecionar a tabela a ser usada como uma tabela de origem para a partição.</span><span class="sxs-lookup"><span data-stu-id="3418c-116">Click to select the table to use as a source table for the partition.</span></span>  
  
 <span data-ttu-id="3418c-117">Se nenhum filtro for especificado em **Filtrar tabelas**, todas as tabelas da fonte de dados ou exibição da fonte de dados especificadas em **Examinar** que forem semelhantes em estrutura à tabela de fatos usada pelo grupo de medidas especificado em **Grupo de medidas** serão listadas.</span><span class="sxs-lookup"><span data-stu-id="3418c-117">If no filter is specified in **Filter tables**, all tables in the data source or data source view specified in **Look in** that are similar in structure to the fact table used by the measure group specified in **Measure group** are listed.</span></span>  
  
 <span data-ttu-id="3418c-118">Se um filtro for especificado em **Filtrar tabelas**, a lista será restringida ainda mais comparando o filtro com os nomes das tabelas que atendem aos critérios acima.</span><span class="sxs-lookup"><span data-stu-id="3418c-118">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the above criteria.</span></span> <span data-ttu-id="3418c-119">Apenas as tabelas que contêm a cadeia de caracteres especificada em **Filtrar tabelas** são exibidas.</span><span class="sxs-lookup"><span data-stu-id="3418c-119">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3418c-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3418c-120">See Also</span></span>  
 [<span data-ttu-id="3418c-121">Caixa de diálogo origem da partição &#40;Analysis Services-dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="3418c-121">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
