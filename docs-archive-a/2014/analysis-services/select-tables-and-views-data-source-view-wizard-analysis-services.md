---
title: Selecionar tabelas e exibições (Assistente de exibição da fonte de dados) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.selecttablesandviews.f1
ms.assetid: ea7d1232-f213-46e9-90d9-0fd616ca003d
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac7159255ef526d871ed8906fc873d9f16d2eb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684382"
---
# <a name="select-tables-and-views-data-source-view-wizard-analysis-services"></a><span data-ttu-id="ceb61-102">Selecionar Tabelas e Exibições (Assistente de Exibição da Fonte de Dados) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="ceb61-102">Select Tables and Views (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="ceb61-103">Use a página **Selecionar Tabelas e Exibições** para selecionar as tabelas ou exibições da fonte de dados que você deseja incluir na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ceb61-103">Use the **Select Tables and Views** page to select the tables or views from the data source that you want to include in the data source view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ceb61-104">Opções</span><span class="sxs-lookup"><span data-stu-id="ceb61-104">Options</span></span>  
 <span data-ttu-id="ceb61-105">**Objetos disponíveis**</span><span class="sxs-lookup"><span data-stu-id="ceb61-105">**Available objects**</span></span>  
 <span data-ttu-id="ceb61-106">Lista as tabelas e exibições no esquema da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ceb61-106">Lists the tables and views in the data source schema.</span></span> <span data-ttu-id="ceb61-107">O nome do esquema será usado como um prefixo do nome de todos os objetos se mais de um esquema for listado.</span><span class="sxs-lookup"><span data-stu-id="ceb61-107">The schema name prefixes the name of every object if more than one schema is listed.</span></span> <span data-ttu-id="ceb61-108">Se apenas um esquema for listado, o nome do objeto não terá o nome do esquema como prefixo.</span><span class="sxs-lookup"><span data-stu-id="ceb61-108">If only one schema is listed, the schema's name does not prefix the object names.</span></span>  
  
 <span data-ttu-id="ceb61-109">Para reordenar a lista em ordem crescente ou decrescente, clique em **Nome** ou em **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="ceb61-109">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="ceb61-110">**Objetos incluídos**</span><span class="sxs-lookup"><span data-stu-id="ceb61-110">**Included objects**</span></span>  
 <span data-ttu-id="ceb61-111">Lista as tabelas e exibições a serem incluídas na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ceb61-111">Lists the tables and views to include in the data source view.</span></span>  
  
 <span data-ttu-id="ceb61-112">Para reordenar a lista em ordem crescente ou decrescente, clique em **Nome** ou em **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="ceb61-112">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="ceb61-113">**Filter**</span><span class="sxs-lookup"><span data-stu-id="ceb61-113">**Filter**</span></span>  
 <span data-ttu-id="ceb61-114">Filtra os objetos listados em **Objetos disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="ceb61-114">Filters the objects listed under **Available objects**.</span></span> <span data-ttu-id="ceb61-115">Digite uma cadeia de caracteres e, em seguida, clique em **Filtro** para listar apenas os nomes que contêm uma cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="ceb61-115">Type a string, and then click **Filter** to list only the names that contain a specified string.</span></span> <span data-ttu-id="ceb61-116">Para localizar uma cadeia de caracteres exata, inclua a cadeia de caracteres entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="ceb61-116">To find an exact string of characters, enclose the string between double quotation marks.</span></span> <span data-ttu-id="ceb61-117">O filtro não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ceb61-117">The filter is not case sensitive.</span></span>  
  
 <span data-ttu-id="ceb61-118">É possível incluir os caracteres curinga listados na tabela a seguir em qualquer lugar na cadeia de caracteres do filtro.</span><span class="sxs-lookup"><span data-stu-id="ceb61-118">You can include the wildcard characters listed in the following table anywhere in the filter string.</span></span>  
  
|<span data-ttu-id="ceb61-119">Caractere curinga</span><span class="sxs-lookup"><span data-stu-id="ceb61-119">Wildcard character</span></span>|<span data-ttu-id="ceb61-120">Valor</span><span class="sxs-lookup"><span data-stu-id="ceb61-120">Value</span></span>|  
|------------------------|-----------|  
|**\***|<span data-ttu-id="ceb61-121">Qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ceb61-121">Any string of characters</span></span>|  
|**%**|<span data-ttu-id="ceb61-122">Qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ceb61-122">Any string of characters</span></span>|  
|<span data-ttu-id="ceb61-123">**?**</span><span class="sxs-lookup"><span data-stu-id="ceb61-123">**?**</span></span>|<span data-ttu-id="ceb61-124">Um único caractere</span><span class="sxs-lookup"><span data-stu-id="ceb61-124">A single character</span></span>|  
|<span data-ttu-id="ceb61-125">**"** *String* **"**</span><span class="sxs-lookup"><span data-stu-id="ceb61-125">**"** *string* **"**</span></span>|<span data-ttu-id="ceb61-126">Uma cadeia de caracteres literal.</span><span class="sxs-lookup"><span data-stu-id="ceb61-126">A literal string of characters.</span></span> <span data-ttu-id="ceb61-127">Este caractere curinga corresponderá a qualquer subcadeia de caracteres dentro do nome do objeto.</span><span class="sxs-lookup"><span data-stu-id="ceb61-127">This wildcard character will match any substring within the object name.</span></span>|  
  
 <span data-ttu-id="ceb61-128">**Mostrar objetos do sistema**</span><span class="sxs-lookup"><span data-stu-id="ceb61-128">**Show system objects**</span></span>  
 <span data-ttu-id="ceb61-129">Exibe objetos do sistema em **Objetos disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="ceb61-129">Displays system objects under **Available objects**.</span></span> <span data-ttu-id="ceb61-130">Essa opção estará disponível apenas se o provedor da fonte de dados expuser objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="ceb61-130">This option is available only if the data source provider exposes system objects.</span></span> <span data-ttu-id="ceb61-131">A remoção de um objeto do sistema da lista **Objetos incluídos** seleciona automaticamente essa opção.</span><span class="sxs-lookup"><span data-stu-id="ceb61-131">Removing a system object from the **Included objects** list automatically selects this option.</span></span>  
  
 <span data-ttu-id="ceb61-132">**Adicionar tabelas relacionadas**</span><span class="sxs-lookup"><span data-stu-id="ceb61-132">**Add related tables**</span></span>  
 <span data-ttu-id="ceb61-133">Adiciona todas as tabelas que estão relacionadas às tabelas listadas em **Objetos incluídos**.</span><span class="sxs-lookup"><span data-stu-id="ceb61-133">Adds all the tables that are related to those listed under **Included objects**.</span></span> <span data-ttu-id="ceb61-134">Essa opção não adiciona exibições.</span><span class="sxs-lookup"><span data-stu-id="ceb61-134">This option does not add views.</span></span> <span data-ttu-id="ceb61-135">No entanto ela adiciona tabelas particionadas.</span><span class="sxs-lookup"><span data-stu-id="ceb61-135">However, this option does add partitioned tables.</span></span> <span data-ttu-id="ceb61-136">Se você selecionar critérios de correspondência de nomes na página **Correspondência de Nomes** do assistente, essa opção também incluirá tabelas relacionadas lógicas de acordo com os critérios selecionados.</span><span class="sxs-lookup"><span data-stu-id="ceb61-136">If you select name-matching criteria on the **Name Matching** page of the wizard, this option also includes logically related tables according to the criteria you select.</span></span> <span data-ttu-id="ceb61-137">Tabelas também serão incluídas se estiverem relacionadas a tabelas relacionadas recém-adicionadas e se tiverem uma estrutura idêntica a da tabela original.</span><span class="sxs-lookup"><span data-stu-id="ceb61-137">Tables are also included if they are related to the newly added related tables, and if they have an identical structure to the original table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb61-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ceb61-138">See Also</span></span>  
 <span data-ttu-id="ceb61-139">[Ajuda F1 do assistente de exibição da fonte de dados &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ceb61-139">[Data Source View Wizard F1 Help &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span></span>  
 [<span data-ttu-id="ceb61-140">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="ceb61-140">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
