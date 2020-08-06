---
title: Propriedades do repositório de filestore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Income property
- InitialBonus property
- PercentScanPerPrice property
- FileStore properties
- BackgroundTrimCost property
- Tax property
- PerformanceTrace property
- MinimumBalance property
- UnbufferedThreshold property
- BackgroundTrimAmount property
- MaximumBalance property
- MemoryLimitMin property
- MemoryLimit property
ms.assetid: 580cf0aa-7425-4d48-aa8d-128f5b488fcd
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc81273b55dea5820ef80f34c22d293492eb8055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686396"
---
# <a name="filestore-properties"></a><span data-ttu-id="3460b-102">Propriedades FileStore</span><span class="sxs-lookup"><span data-stu-id="3460b-102">Filestore Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="3460b-103">oferece suporte às propriedades do servidor de armazenamento de arquivos listadas nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3460b-103">supports the filestore server properties listed in the following tables.</span></span> <span data-ttu-id="3460b-104">Estas são todas as propriedades avançadas que não devem ser alteradas, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-104">These are all advanced properties that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span> <span data-ttu-id="3460b-105">Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="3460b-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="3460b-106">**Aplica-se a:** modo de servidor multidimensional e tabular</span><span class="sxs-lookup"><span data-stu-id="3460b-106">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3460b-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="3460b-107">Properties</span></span>  
 `MemoryLimit`  
 <span data-ttu-id="3460b-108">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-108">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryLimitMin`  
 <span data-ttu-id="3460b-109">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PercentScanPerPrice`  
 <span data-ttu-id="3460b-110">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PerformanceTrace`  
 <span data-ttu-id="3460b-111">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-111">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RandomFileAccessMode`  
 <span data-ttu-id="3460b-112">Uma propriedade Booliana que indica se os arquivos de banco de dados e arquivos armazenados em cache são acessados em modo de acesso aleatório ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="3460b-112">A Boolean property that indicates whether database files and cached files are accessed in random file access mode.</span></span> <span data-ttu-id="3460b-113">Essa propriedade é desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="3460b-113">This property is off by default.</span></span> <span data-ttu-id="3460b-114">Por padrão, o Analysis Services não define o sinalizador de acesso ao arquivo aleatório ao abrir arquivos de dados de partição para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="3460b-114">By default, Analysis Services does not set the random file access flag when opening partition data files for read access.</span></span>  
  
 <span data-ttu-id="3460b-115">Em sistemas avançados, especialmente os com recursos de memória grandes e vários nós NUMA, pode ser vantajoso usar acesso aleatório ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="3460b-115">On high-end systems, particularly those with large memory resources and multiple NUMA nodes, it can be advantageous to use random file access.</span></span> <span data-ttu-id="3460b-116">No modo de acesso aleatório, o Windows ignora operações de mapeamento de página que leem dados do disco no cache de arquivo do sistema, diminuindo, portanto, a contenção no cache.</span><span class="sxs-lookup"><span data-stu-id="3460b-116">In random access mode, Windows bypasses page mapping operations that read data from disk into the system file cache, thereby lowering contention on the cache.</span></span>  
  
 <span data-ttu-id="3460b-117">Você precisará executar testes de comparação para determinar se o desempenho da consulta melhorou como o resultado da alteração desta propriedade.</span><span class="sxs-lookup"><span data-stu-id="3460b-117">You will need to run comparison tests to determine whether query performance is improved as the result of changing this property.</span></span> <span data-ttu-id="3460b-118">Para conhecer as práticas recomendadas sobre como fazer testes de comparação, inclusive limpar o cache e evitar erros comuns, consulte [Guia de operações do SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="3460b-118">For best practices on running comparison tests, including clearing the cache and avoiding common mistakes, see the [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span> <span data-ttu-id="3460b-119">Para obter informações adicionais sobre as compensações de usar essa propriedade, consulte [https://support.microsoft.com/kb/2549369](https://support.microsoft.com/kb/2549369) .</span><span class="sxs-lookup"><span data-stu-id="3460b-119">For additional information on the tradeoffs of using this property, see [https://support.microsoft.com/kb/2549369](https://support.microsoft.com/kb/2549369).</span></span>  
  
 <span data-ttu-id="3460b-120">Para exibir ou modificar esta propriedade no Management Studio, habilite a lista de propriedades avançadas na página de propriedades do servidor.</span><span class="sxs-lookup"><span data-stu-id="3460b-120">To view or modify this property in Management Studio, enable the advanced properties list in the server properties page.</span></span> <span data-ttu-id="3460b-121">Você também pode alterar a propriedade no arquivo msmdsrv.ini.</span><span class="sxs-lookup"><span data-stu-id="3460b-121">You can also change the property in the msmdsrv.ini file.</span></span> <span data-ttu-id="3460b-122">Reiniciar o servidor é recomendado depois de definir esta propriedade; caso contrário, os arquivos que já estão abertos continuarão sendo acessados no modo anterior.</span><span class="sxs-lookup"><span data-stu-id="3460b-122">Restarting the server is recommended after setting this property; otherwise files that are already open will continue to be accessed in the previous mode.</span></span>  
  
 `UnbufferedThreshold`  
 <span data-ttu-id="3460b-123">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-123">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="memory-model-category"></a><span data-ttu-id="3460b-124">Categoria de modelo de memória</span><span class="sxs-lookup"><span data-stu-id="3460b-124">Memory Model Category</span></span>  
 `MemoryModel\Tax`  
 <span data-ttu-id="3460b-125">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-125">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\Income`  
 <span data-ttu-id="3460b-126">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\MaximumBalance`  
 <span data-ttu-id="3460b-127">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-127">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\MinimumBalance`  
 <span data-ttu-id="3460b-128">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-128">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\InitialBonus`  
 <span data-ttu-id="3460b-129">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3460b-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3460b-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3460b-130">See Also</span></span>  
 <span data-ttu-id="3460b-131">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="3460b-131">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="3460b-132">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="3460b-132">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
