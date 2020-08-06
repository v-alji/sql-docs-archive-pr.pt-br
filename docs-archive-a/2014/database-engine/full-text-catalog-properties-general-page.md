---
title: Propriedades do catálogo de texto completo (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.general.f1
ms.assetid: d1f66762-2d40-4f24-b635-a417d22ee79a
author: rothja
ms.author: jroth
ms.openlocfilehash: 483601c53db6c8a806ea8c53f771fd4f2608293b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684854"
---
# <a name="full-text-catalog-properties-general-page"></a><span data-ttu-id="8cc30-102">Propriedades do Catálogo de Texto Completo (página Geral)</span><span class="sxs-lookup"><span data-stu-id="8cc30-102">Full-Text Catalog Properties (General Page)</span></span>
  <span data-ttu-id="8cc30-103">Esta seção mostra as opções e funções disponíveis na página **Geral** da caixa de diálogo **Propriedades do Catálogo de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="8cc30-103">This section shows the options and functions available on the **General** page of the **Full-Text Catalog Properties** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8cc30-104">Nos bancos de dados do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] , um catálogo de texto completo é um conceito lógico que se refere a um grupo de índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-104">For [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] databases, a full-text catalog is a logical concept that refers to a group of full-text indexes.</span></span> <span data-ttu-id="8cc30-105">O catálogo de texto completo é um objeto virtual que não pertence a nenhum grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8cc30-105">The full-text catalog is a virtual object that does not belong to any filegroup.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8cc30-106">Opções</span><span class="sxs-lookup"><span data-stu-id="8cc30-106">Options</span></span>  
  
### <a name="properties"></a><span data-ttu-id="8cc30-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8cc30-107">Properties</span></span>  
 <span data-ttu-id="8cc30-108">**Catálogo Padrão**</span><span class="sxs-lookup"><span data-stu-id="8cc30-108">**Default Catalog**</span></span>  
 <span data-ttu-id="8cc30-109">Exibe se o catálogo é o catálogo padrão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8cc30-109">Displays whether the catalog is the default catalog for the database.</span></span>  
  
 <span data-ttu-id="8cc30-110">**Status de População**</span><span class="sxs-lookup"><span data-stu-id="8cc30-110">**Population Status**</span></span>  
 <span data-ttu-id="8cc30-111">Indica o status do catálogo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-111">Indicates the status of the catalog.</span></span> <span data-ttu-id="8cc30-112">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="8cc30-112">Possible values are:</span></span>  
  
-   <span data-ttu-id="8cc30-113">**Idle**</span><span class="sxs-lookup"><span data-stu-id="8cc30-113">**Idle**</span></span>  
  
-   <span data-ttu-id="8cc30-114">**Rastreamento em andamento**</span><span class="sxs-lookup"><span data-stu-id="8cc30-114">**Crawl in Progress**</span></span>  
  
-   <span data-ttu-id="8cc30-115">**Em pausa**</span><span class="sxs-lookup"><span data-stu-id="8cc30-115">**Paused**</span></span>  
  
-   <span data-ttu-id="8cc30-116">**Acelerado**</span><span class="sxs-lookup"><span data-stu-id="8cc30-116">**Throttled**</span></span>  
  
-   <span data-ttu-id="8cc30-117">**Recuperação**</span><span class="sxs-lookup"><span data-stu-id="8cc30-117">**Recovering**</span></span>  
  
-   <span data-ttu-id="8cc30-118">**Desligamento**</span><span class="sxs-lookup"><span data-stu-id="8cc30-118">**Shutdown**</span></span>  
  
-   <span data-ttu-id="8cc30-119">**População incremental em andamento**</span><span class="sxs-lookup"><span data-stu-id="8cc30-119">**Incremental population in progress**</span></span>  
  
-   <span data-ttu-id="8cc30-120">**Criando índice**</span><span class="sxs-lookup"><span data-stu-id="8cc30-120">**Building index**</span></span>  
  
-   <span data-ttu-id="8cc30-121">**O disco está em pausa total**</span><span class="sxs-lookup"><span data-stu-id="8cc30-121">**Disk is full-Paused**</span></span>  
  
-   <span data-ttu-id="8cc30-122">**Controle de alterações**</span><span class="sxs-lookup"><span data-stu-id="8cc30-122">**Change tracking**</span></span>  
  
 <span data-ttu-id="8cc30-123">**Contagem de Itens**</span><span class="sxs-lookup"><span data-stu-id="8cc30-123">**Item Count**</span></span>  
 <span data-ttu-id="8cc30-124">Exibe o número de itens de texto completo no catálogo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-124">Displays the number of full-text items in the catalog.</span></span>  
  
 <span data-ttu-id="8cc30-125">**Tamanho do Catálogo**</span><span class="sxs-lookup"><span data-stu-id="8cc30-125">**Catalog Size**</span></span>  
 <span data-ttu-id="8cc30-126">Exibe o tamanho, em megabytes, do catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-126">Displays the size, in megabytes, of the full-text catalog.</span></span>  
  
 <span data-ttu-id="8cc30-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8cc30-127">**Name**</span></span>  
 <span data-ttu-id="8cc30-128">Nome do catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-128">The name of the full-text catalog.</span></span>  
  
 <span data-ttu-id="8cc30-129">**Diferenciar Acentos**</span><span class="sxs-lookup"><span data-stu-id="8cc30-129">**Accent Sensitive**</span></span>  
 <span data-ttu-id="8cc30-130">Exiba ou modifique se o catálogo é sensível a sinais diacríticos, como til ( **~** ), acento agudo (**́**) ou trema (**̈**).</span><span class="sxs-lookup"><span data-stu-id="8cc30-130">View or modify whether the catalog is sensitive to diacritical marks, such as a tilde (**~**), acute accent mark (**´**), or umlaut (**¨**).</span></span> <span data-ttu-id="8cc30-131">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="8cc30-131">Valid values are:</span></span>  
  
-   <span data-ttu-id="8cc30-132">**Não**</span><span class="sxs-lookup"><span data-stu-id="8cc30-132">**No**</span></span>  
  
-   <span data-ttu-id="8cc30-133">**Sim**</span><span class="sxs-lookup"><span data-stu-id="8cc30-133">**Yes**</span></span>  
  
-   <span data-ttu-id="8cc30-134">Para obter informações sobre sinais diacríticos, consulte [sinais diacríticos](https://www.merriam-webster.com/dictionary/diacritic) no dicionário Merriam-Webster.</span><span class="sxs-lookup"><span data-stu-id="8cc30-134">For information about diacritical marks, see [Diacritic](https://www.merriam-webster.com/dictionary/diacritic) in the Merriam-Webster dictionary.</span></span>  
  
 <span data-ttu-id="8cc30-135">**Data da Última População**</span><span class="sxs-lookup"><span data-stu-id="8cc30-135">**Last Population Date**</span></span>  
 <span data-ttu-id="8cc30-136">Exibe a data em que o catálogo foi populado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="8cc30-136">Displays the date the catalog was last populated.</span></span>  
  
 <span data-ttu-id="8cc30-137">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="8cc30-137">**Owner**</span></span>  
 <span data-ttu-id="8cc30-138">Proprietário do catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-138">The owner of the full-text catalog.</span></span>  
  
 <span data-ttu-id="8cc30-139">**Contagem de Chaves Exclusivas**</span><span class="sxs-lookup"><span data-stu-id="8cc30-139">**Unique Key Count**</span></span>  
 <span data-ttu-id="8cc30-140">Número de palavras exclusivas que formam o índice de texto completo para o catálogo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-140">The number of unique words that make up the full-text index for the catalog.</span></span>  
  
### <a name="catalog-action"></a><span data-ttu-id="8cc30-141">Ação do Catálogo</span><span class="sxs-lookup"><span data-stu-id="8cc30-141">Catalog Action</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8cc30-142">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="8cc30-142">**None**</span></span>|<span data-ttu-id="8cc30-143">Não executa operações de **Otimizar catálogo**, **Recriar catálogo**nem **Repopular catálogo** .</span><span class="sxs-lookup"><span data-stu-id="8cc30-143">Does not perform **Optimize catalog**, **Rebuild catalog**, or **Repopulate catalog** operations.</span></span>|  
|<span data-ttu-id="8cc30-144">**Otimizar catálogo**</span><span class="sxs-lookup"><span data-stu-id="8cc30-144">**Optimize catalog**</span></span>|<span data-ttu-id="8cc30-145">Otimiza a utilização de espaço do catálogo e melhora o desempenho de consultas.</span><span class="sxs-lookup"><span data-stu-id="8cc30-145">Optimizes the space utilization of the catalog and improves query performance.</span></span> <span data-ttu-id="8cc30-146">Também melhora a exatidão da classificação de relevância de resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8cc30-146">It also improves the accuracy of relevance ranking of search results.</span></span><br /><br /> <span data-ttu-id="8cc30-147">Esta ação executa ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="8cc30-147">This action executes ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span></span>|  
|<span data-ttu-id="8cc30-148">**Recriar catálogo**</span><span class="sxs-lookup"><span data-stu-id="8cc30-148">**Rebuild catalog**</span></span>|<span data-ttu-id="8cc30-149">Exclui e recria o catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-149">Deletes and rebuilds the full-text catalog.</span></span> <span data-ttu-id="8cc30-150">Esta operação deve ser executada se uma propriedade de catálogo fundamental for alterada, como distinção de acentos.</span><span class="sxs-lookup"><span data-stu-id="8cc30-150">This operation must be performed if a fundamental catalog property is changed, such as accent sensitivity.</span></span><br /><br /> <span data-ttu-id="8cc30-151">Para que a recriação seja bem-sucedida, o grupo de arquivos em que reside o catálogo de texto completo deve estar online ou poder ser lido-gravado.</span><span class="sxs-lookup"><span data-stu-id="8cc30-151">For the rebuild to succeed, the filegroup the full-text catalog resides in must be online or read-writeable.</span></span> <span data-ttu-id="8cc30-152">Após a recriação, o índice de texto completo será populado novamente.</span><span class="sxs-lookup"><span data-stu-id="8cc30-152">After the rebuild, the full-text index will be repopulated.</span></span><br /><br /> <span data-ttu-id="8cc30-153">Esta ação executa ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span><span class="sxs-lookup"><span data-stu-id="8cc30-153">This action executes ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span></span>|  
|<span data-ttu-id="8cc30-154">**Repopular catálogo**</span><span class="sxs-lookup"><span data-stu-id="8cc30-154">**Repopulate catalog**</span></span>|<span data-ttu-id="8cc30-155">Atualiza o catálogo com alterações recentes dos dados.</span><span class="sxs-lookup"><span data-stu-id="8cc30-155">Updates the catalog with recent changes to the data.</span></span> <span data-ttu-id="8cc30-156">Esta opção requer tempo para manutenção do catálogo.</span><span class="sxs-lookup"><span data-stu-id="8cc30-156">This option does require catalog downtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cc30-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8cc30-157">See Also</span></span>  
 [<span data-ttu-id="8cc30-158">Popular índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="8cc30-158">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
