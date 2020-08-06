---
title: Especificar informações de origem (Assistente para partições) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifydsvandfacttables.f1
ms.assetid: b6c13587-c690-45d9-af90-b3d652afc55b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 088a8abf7b143b68766f22af37f8ff4fa2065d65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581494"
---
# <a name="specify-source-information-partition-wizard"></a><span data-ttu-id="87dc2-102">Especificar Informações sobre a Origem (Assistente para Partições)</span><span class="sxs-lookup"><span data-stu-id="87dc2-102">Specify Source Information (Partition Wizard)</span></span>
  <span data-ttu-id="87dc2-103">Use a página **Especificar Informações sobre a Origem** para selecionar o grupo de medidas no qual criar a partição e também a exibição da fonte de dados e as tabelas de filtro da partição.</span><span class="sxs-lookup"><span data-stu-id="87dc2-103">Use the **Specify Source Information** page to select the measure group in which to create the partition, and also the data source view and filter tables for your partition.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="87dc2-104">Se você especificar uma tabela em **Tabelas Disponíveis** que seja usada por outra partição, deverá fornecer uma consulta na página **Restringir Linhas** ou arriscar duplicação de dados no cubo.</span><span class="sxs-lookup"><span data-stu-id="87dc2-104">If you specify a table in **Available Tables** that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="87dc2-105">Opções</span><span class="sxs-lookup"><span data-stu-id="87dc2-105">Options</span></span>  
 <span data-ttu-id="87dc2-106">**Grupo de medidas**</span><span class="sxs-lookup"><span data-stu-id="87dc2-106">**Measure group**</span></span>  
 <span data-ttu-id="87dc2-107">Selecione um grupo de medidas para esta partição.</span><span class="sxs-lookup"><span data-stu-id="87dc2-107">Select a measure group for this partition.</span></span>  
  
 <span data-ttu-id="87dc2-108">**Examinar**</span><span class="sxs-lookup"><span data-stu-id="87dc2-108">**Look in**</span></span>  
 <span data-ttu-id="87dc2-109">Selecione a fonte de dados ou exibição da fonte de dados que contém as tabelas de origem desta partição.</span><span class="sxs-lookup"><span data-stu-id="87dc2-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="87dc2-110">A exibição da fonte de dados usada pelo grupo de medidas é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="87dc2-110">The data source view used by the measure group is selected by default.</span></span>  
  
 <span data-ttu-id="87dc2-111">**Filtrar tabelas**</span><span class="sxs-lookup"><span data-stu-id="87dc2-111">**Filter tables**</span></span>  
 <span data-ttu-id="87dc2-112">Digite a cadeia de caracteres usada para restringir, por nome de tabela, as tabelas exibidas em **Tabelas disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="87dc2-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="87dc2-113">**Localizar tabelas**</span><span class="sxs-lookup"><span data-stu-id="87dc2-113">**Find tables**</span></span>  
 <span data-ttu-id="87dc2-114">Selecione para atualizar a lista de tabelas em **Tabelas disponíveis**, restringindo ainda mais a lista, se uma cadeia de caracteres tiver sido especificada em **Filtrar tabelas**.</span><span class="sxs-lookup"><span data-stu-id="87dc2-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="87dc2-115">**Tabelas Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="87dc2-115">**Available tables**</span></span>  
 <span data-ttu-id="87dc2-116">Selecione as tabelas a serem usadas como tabelas de origem para partições.</span><span class="sxs-lookup"><span data-stu-id="87dc2-116">Select the tables to use as source tables for partitions.</span></span> <span data-ttu-id="87dc2-117">O **Assistente para Partições** cria uma partição para cada tabela selecionada em **Tabelas Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="87dc2-117">The **Partition Wizard** creates one partition for each table selected in **Available tables**.</span></span>  
  
 <span data-ttu-id="87dc2-118">Se nenhum filtro for especificado em **Filtrar tabelas**, essa opção listará todas as tabelas da fonte de dados ou exibição da fonte de dados que são especificadas em **Examinar** e que são semelhantes em estrutura à tabela de fatos usada pelo grupo de medidas especificado em **Grupo de medidas**.</span><span class="sxs-lookup"><span data-stu-id="87dc2-118">If no filter is specified in **Filter tables**, this option lists all tables in the data source or data source view that are specified in **Look in** and that are similar in structure to the fact table used by the measure group specified in **Measure group**.</span></span>  
  
 <span data-ttu-id="87dc2-119">Se um filtro for especificado em **Filtrar tabelas**, a lista será restringida ainda mais comparando o filtro com os nomes das tabelas que atendem aos critérios anteriores.</span><span class="sxs-lookup"><span data-stu-id="87dc2-119">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the previous criteria.</span></span> <span data-ttu-id="87dc2-120">Apenas as tabelas que contêm a cadeia de caracteres especificada em **Filtrar tabelas** são exibidas.</span><span class="sxs-lookup"><span data-stu-id="87dc2-120">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87dc2-121">Se mais de uma tabela for selecionada, a página **Restringir Linhas** não poderá ser exibida e as linhas não poderão ser restringidas para as partições criadas a partir das tabelas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="87dc2-121">If more than one table is selected, the **Restrict Rows** page cannot be displayed and rows cannot be restricted for the partitions created from the selected tables.</span></span> <span data-ttu-id="87dc2-122">Para restringir linhas para cada partição, execute o Assistente para Partições uma vez para cada tabela da qual uma partição deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="87dc2-122">To restrict rows for each partition, run the Partition Wizard once for each table from which a partition is to be created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87dc2-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="87dc2-123">See Also</span></span>  
 [<span data-ttu-id="87dc2-124">Partições &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="87dc2-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
