---
title: Propriedades da memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LowMemoryLimit property
- MinimumAllocatedMemory property
- MidMemoryPrice property
- MemoryHeapType property
- memory [Analysis Services]
- DefaultPagesCountToReuse property
- TotalMemoryLimit property
- SessionMemoryLimit property
- VirtualMemoryLimit property
- WaitCountIfHighMemory property
- HighMemoryPrice property
- HeapTypeForObjects property
ms.assetid: 085f5195-7b2c-411a-9813-0ff5c6066d13
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f2d2e56c9a951cee27752bd57d55d185a9b6618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686387"
---
# <a name="memory-properties"></a><span data-ttu-id="15c02-102">Propriedades de memória</span><span class="sxs-lookup"><span data-stu-id="15c02-102">Memory Properties</span></span>
  <span data-ttu-id="15c02-103">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] oferece suporte às propriedades de memória do servidor listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="15c02-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports the server memory properties listed in the following table.</span></span> <span data-ttu-id="15c02-104">Para obter orientações sobre a configuração dessas propriedades, consulte [Guia de Operações do SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="15c02-104">For guidance in setting these properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 <span data-ttu-id="15c02-105">Os valores entre 1 e 100 representam percentuais da **Memória Física Total** ou do **Espaço de Endereço Virtual**, o que for menor.</span><span class="sxs-lookup"><span data-stu-id="15c02-105">Values between 1 and 100 represent percentages of **Total Physical Memory** or **Virtual Address Space**, whichever is less.</span></span> <span data-ttu-id="15c02-106">Os valores acima de 100 representam limites de memória em bytes.</span><span class="sxs-lookup"><span data-stu-id="15c02-106">Values over 100 represent memory limits in bytes.</span></span>  
  
 <span data-ttu-id="15c02-107">**Aplica-se a:** Modo de servidor multidimensional e tabular, a menos que indicado o contrário.</span><span class="sxs-lookup"><span data-stu-id="15c02-107">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="15c02-108">Propriedades</span><span class="sxs-lookup"><span data-stu-id="15c02-108">Properties</span></span>  
 `LowMemoryLimit`  
 <span data-ttu-id="15c02-109">Uma propriedade de número de ponto flutuante da precisão dupla de 64 bits assinada que define o ponto em que o servidor está com pouca memória, expressada como percentual da memória física total.</span><span class="sxs-lookup"><span data-stu-id="15c02-109">A signed 64-bit double-precision floating-point number property that defines the point at which the server is low on memory, expressed as percentage of total physical memory.</span></span> <span data-ttu-id="15c02-110">Quando este limite é atingido, a instância começa lentamente a limpar a memória de cache fechando sessões expiradas e descarregando cálculos não usados.</span><span class="sxs-lookup"><span data-stu-id="15c02-110">When this limit is reached, the instance will start to slowly clear memory out of caches by closing expired sessions and unloading unused calculations.</span></span> <span data-ttu-id="15c02-111">O servidor não liberará memória debaixo deste limite.</span><span class="sxs-lookup"><span data-stu-id="15c02-111">The server will not release memory below this limit.</span></span> <span data-ttu-id="15c02-112">O valor padrão é 65; o que indica que o limite de memória baixo é 65% de memória física ou o espaço de endereço virtual, o que for menor.</span><span class="sxs-lookup"><span data-stu-id="15c02-112">The default value is 65; which indicates the low memory limit is 65% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 `TotalMemoryLimit`  
 <span data-ttu-id="15c02-113">Define um limite que, quando alcançado, faz o servidor desalocar memória de maneira mais agressiva.</span><span class="sxs-lookup"><span data-stu-id="15c02-113">Defines a threshold that when reached, causes the server to deallocate memory more aggressively.</span></span> <span data-ttu-id="15c02-114">O valor padrão de 80% de memória física ou o espaço de endereço virtual, o que for menor.</span><span class="sxs-lookup"><span data-stu-id="15c02-114">The default value 80% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 <span data-ttu-id="15c02-115">Observe que `TotalMemoryLimit` deve ser sempre menor que `HardMemoryLimit`</span><span class="sxs-lookup"><span data-stu-id="15c02-115">Note that `TotalMemoryLimit` must always be less than `HardMemoryLimit`</span></span>  
  
 `HardMemoryLimit`  
 <span data-ttu-id="15c02-116">Especifica um limite de memória depois do qual a instância finaliza sessões de usuário ativas agressivamente para reduzir o uso da memória.</span><span class="sxs-lookup"><span data-stu-id="15c02-116">Specifies a memory threshold after which the instance aggressively terminates active user sessions to reduce memory usage.</span></span> <span data-ttu-id="15c02-117">Todas as sessões terminadas receberão um erro sobre terem sido canceladas por pressão de memória.</span><span class="sxs-lookup"><span data-stu-id="15c02-117">All terminated sessions will receive an error about being cancelled by memory pressure.</span></span> <span data-ttu-id="15c02-118">O valor padrão, zero (0), significa que o `HardMemoryLimit` será definido como um valor entre `TotalMemoryLimit` e a memória física total do sistema; se a memória física do sistema for maior que o espaço de endereço virtual do processo, o espaço de endereço virtual será usado para calcular o `HardMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="15c02-118">The default value, zero (0), means the `HardMemoryLimit` will be set to a midway value between `TotalMemoryLimit` and the total physical memory of the system; if the physical memory of the system is larger than the virtual address space of the process, then virtual address space will be used instead to calculate `HardMemoryLimit`.</span></span>  
  
 `VirtualMemoryLimit`  
 <span data-ttu-id="15c02-119">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-119">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `VertiPaqPagingPolicy`  
 <span data-ttu-id="15c02-120">Especifica o comportamento de paginação no evento que o servidor é executa com pouca memória.</span><span class="sxs-lookup"><span data-stu-id="15c02-120">Specifies the paging behavior in the event the server runs low on memory.</span></span> <span data-ttu-id="15c02-121">Estes são os valores válidos:</span><span class="sxs-lookup"><span data-stu-id="15c02-121">Valid values are as follows:</span></span>  
  
 <span data-ttu-id="15c02-122">Zero (**0**) desabilita a paginação.</span><span class="sxs-lookup"><span data-stu-id="15c02-122">Zero (**0**) disables paging.</span></span> <span data-ttu-id="15c02-123">Se a memória for insuficiente, o processamento falhará com um erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="15c02-123">If memory is insufficient, processing fails with an out-of-memory error.</span></span> <span data-ttu-id="15c02-124">Se você desabilitar a paginação, será preciso conceder privilégios do Windows à conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="15c02-124">If you disable paging, you must grant Windows privileges to the service account.</span></span> <span data-ttu-id="15c02-125">Consulte [Configurar contas de serviço &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="15c02-125">See [Configure Service Accounts &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md) for instructions.</span></span>  
  
 <span data-ttu-id="15c02-126">**1** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="15c02-126">**1** is the default.</span></span> <span data-ttu-id="15c02-127">Esta propriedade habilita a paginação no disco usando o arquivo de paginação do sistema operacional (pagefile.sys).</span><span class="sxs-lookup"><span data-stu-id="15c02-127">This property enables paging to disk using the operating system page file (pagefile.sys).</span></span>  
  
 <span data-ttu-id="15c02-128">Quando `VertiPaqPagingPolicy` é definida como 1, o processamento apresenta menor probabilidade de falhar devido às restrições de memória, pois o servidor tentará paginar para o disco usando o método especificado por você.</span><span class="sxs-lookup"><span data-stu-id="15c02-128">When `VertiPaqPagingPolicy` is set to 1, processing is less likely to fail due to memory constraints because the server will try to page to disk using the method that you specified.</span></span> <span data-ttu-id="15c02-129">A definição da propriedade `VertiPaqPagingPolicy` não garante que erros de memória nunca ocorrerão.</span><span class="sxs-lookup"><span data-stu-id="15c02-129">Setting the `VertiPaqPagingPolicy` property does not guarantee that memory errors will never happen.</span></span> <span data-ttu-id="15c02-130">Erros de falta de memória ainda podem ocorrer sob as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="15c02-130">Out of memory errors can still occur under the following conditions:</span></span>  
  
-   <span data-ttu-id="15c02-131">Não há bastante memória para todos os dicionários.</span><span class="sxs-lookup"><span data-stu-id="15c02-131">There is not enough memory for all dictionaries.</span></span> <span data-ttu-id="15c02-132">Durante o processamento, o Analysis Services bloqueia os dicionários para cada coluna na memória e todos eles juntos não podem ter mais do que o valor especificado para `VertiPaqMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="15c02-132">During processing, Analysis Services locks the dictionaries for each column in memory, and all of these together cannot be more than the value specified for `VertiPaqMemoryLimit`.</span></span>  
  
-   <span data-ttu-id="15c02-133">Não há espaço de endereço virtual insuficiente para acomodar o processo.</span><span class="sxs-lookup"><span data-stu-id="15c02-133">There is insufficient virtual address space to accommodate the process.</span></span>  
  
 <span data-ttu-id="15c02-134">Para resolver erros de falta de memória persistentes, você pode tentar reprojetar o modelo para reduzir a quantidade de dados que precisa de processamento ou pode adicionar mais memória física ao computador.</span><span class="sxs-lookup"><span data-stu-id="15c02-134">To resolve persistent out of memory errors, you can either try to redesign the model to reduce the amount of data that needs processing, or you can add more physical memory to the computer.</span></span>  
  
 <span data-ttu-id="15c02-135">Isso se aplica apenas ao modo de servidor tabular.</span><span class="sxs-lookup"><span data-stu-id="15c02-135">Applies to tabular server mode only.</span></span>  
  
 `VertiPaqMemoryLimit`  
 <span data-ttu-id="15c02-136">Se é permitido chamar o disco, esta propriedade especificará o nível de consumo de memória (como um percentual de memória total) no qual a paginação começará.</span><span class="sxs-lookup"><span data-stu-id="15c02-136">If paging to disk is allowed, this property specifies the level of memory consumption (as a percentage of total memory) at which paging starts.</span></span> <span data-ttu-id="15c02-137">O padrão é 60.</span><span class="sxs-lookup"><span data-stu-id="15c02-137">The default is 60.</span></span> <span data-ttu-id="15c02-138">Se o consumo de memória for menos que 60 por cento, o servidor não paginará para o disco.</span><span class="sxs-lookup"><span data-stu-id="15c02-138">If memory consumption is less than 60 percent, the server will not page to disk.</span></span>  
  
 <span data-ttu-id="15c02-139">Esta propriedade depende do `VertiPaqPagingPolicyProperty`, que deve ser definido como 1 para que a paginação ocorra.</span><span class="sxs-lookup"><span data-stu-id="15c02-139">This property depends on the `VertiPaqPagingPolicyProperty`, which must be set to 1 in order for paging to occur.</span></span>  
  
 <span data-ttu-id="15c02-140">Isso se aplica apenas ao modo de servidor tabular.</span><span class="sxs-lookup"><span data-stu-id="15c02-140">Applies to tabular server mode only.</span></span>  
  
 `HighMemoryPrice`  
 <span data-ttu-id="15c02-141">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryHeapType`  
 <span data-ttu-id="15c02-142">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="15c02-143">Aplica-se a somente o modo de servidor multidimensional.</span><span class="sxs-lookup"><span data-stu-id="15c02-143">Applies to multidimensional server mode only.</span></span>  
  
 `HeapTypeForObjects`  
 <span data-ttu-id="15c02-144">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="15c02-145">Aplica-se a somente o modo de servidor multidimensional.</span><span class="sxs-lookup"><span data-stu-id="15c02-145">Applies to multidimensional server mode only.</span></span>  
  
 `DefaultPagesCountToReuse`  
 <span data-ttu-id="15c02-146">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `HandleIA64AlignmentFaults`  
 <span data-ttu-id="15c02-147">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MidMemoryPrice`  
 <span data-ttu-id="15c02-148">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinimumAllocatedMemory`  
 <span data-ttu-id="15c02-149">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PreAllocate`  
 <span data-ttu-id="15c02-150">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SessionMemoryLimit`  
 <span data-ttu-id="15c02-151">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `WaitCountIfHighMemory`  
 <span data-ttu-id="15c02-152">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15c02-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c02-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15c02-153">See Also</span></span>  
 <span data-ttu-id="15c02-154">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="15c02-154">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="15c02-155">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="15c02-155">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
