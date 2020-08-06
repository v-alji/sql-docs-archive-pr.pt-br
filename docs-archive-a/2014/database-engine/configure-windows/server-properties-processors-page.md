---
title: Propriedades do servidor (página Processadores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.processor.f1
ms.assetid: cc1581a2-492b-41f0-bda5-17909b65c4f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4d241f01de7ac961832e77bb09483cff275deb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574890"
---
# <a name="server-properties-processors-page"></a><span data-ttu-id="9948e-102">Propriedades do Servidor (página Processadores)</span><span class="sxs-lookup"><span data-stu-id="9948e-102">Server Properties (Processors Page)</span></span>
  <span data-ttu-id="9948e-103">Use esta página para exibir ou modificar suas opções de processador.</span><span class="sxs-lookup"><span data-stu-id="9948e-103">Use this page to view or modify your processor options.</span></span> <span data-ttu-id="9948e-104">As configurações de afinidade do processador só são habilitadas quando há mais de um processador instalado.</span><span class="sxs-lookup"><span data-stu-id="9948e-104">Processor affinity settings are only enabled when more than one processor is installed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9948e-105">Opções</span><span class="sxs-lookup"><span data-stu-id="9948e-105">Options</span></span>  
 <span data-ttu-id="9948e-106">**Afinidade do Processador**</span><span class="sxs-lookup"><span data-stu-id="9948e-106">**Processor Affinity**</span></span>  
 <span data-ttu-id="9948e-107">Atribui processadores a threads específicos para eliminar recargas do processador e reduzir a migração de thread pelos processadores.</span><span class="sxs-lookup"><span data-stu-id="9948e-107">Assigns processors to specific threads to eliminating processor reloads and reduce thread migration across processors.</span></span> <span data-ttu-id="9948e-108">Para obter mais informações, veja [Opção affinity mask de configuração de servidor](affinity-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="9948e-108">For more information, see [affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="9948e-109">**Afinidade de E/S**</span><span class="sxs-lookup"><span data-stu-id="9948e-109">**I/O Affinity**</span></span>  
 <span data-ttu-id="9948e-110">Associa as E/Ss de disco do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a um subconjunto especificado de CPUs.</span><span class="sxs-lookup"><span data-stu-id="9948e-110">Binds [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/Os to a specified subset of CPUs.</span></span> <span data-ttu-id="9948e-111">Para obter mais informações, veja [Opção affinity Input-Output mask de configuração de servidor](affinity-input-output-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="9948e-111">For more information, see [affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="9948e-112">**Definir automaticamente a máscara de afinidade de todos os processadores**</span><span class="sxs-lookup"><span data-stu-id="9948e-112">**Automatically set processor affinity mask for all processors**</span></span>  
 <span data-ttu-id="9948e-113">Permite que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defina a afinidade do processador.</span><span class="sxs-lookup"><span data-stu-id="9948e-113">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the processor affinity.</span></span>  
  
 <span data-ttu-id="9948e-114">**Definir automaticamente a máscara de afinidade de E/S de todos os processadores**</span><span class="sxs-lookup"><span data-stu-id="9948e-114">**Automatically set I/O affinity mask for all processors**</span></span>  
 <span data-ttu-id="9948e-115">Permite que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defina a afinidade de E/S.</span><span class="sxs-lookup"><span data-stu-id="9948e-115">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the I/O affinity.</span></span>  
  
 <span data-ttu-id="9948e-116">**Máximo de threads de trabalho**</span><span class="sxs-lookup"><span data-stu-id="9948e-116">**Maximum worker threads**</span></span>  
 <span data-ttu-id="9948e-117">0 permite que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defina dinamicamente o número de threads de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9948e-117">0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to dynamically set the number of worker threads.</span></span> <span data-ttu-id="9948e-118">Essa configuração é melhor para a maioria dos sistemas.</span><span class="sxs-lookup"><span data-stu-id="9948e-118">This setting is best for most systems.</span></span> <span data-ttu-id="9948e-119">Porém, dependendo de sua configuração de sistema, definir essa opção com um valor específico às vezes melhora o desempenho.</span><span class="sxs-lookup"><span data-stu-id="9948e-119">However, depending on your system configuration, setting this option to a specific value sometimes improves performance.</span></span> <span data-ttu-id="9948e-120">Para obter mais informações, consulte [configurar a opção de configuração de servidor max worker threads](configure-the-max-worker-threads-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="9948e-120">For more information, see [Configure the max worker threads Server Configuration Option](configure-the-max-worker-threads-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="9948e-121">**Aumentar a prioridade do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9948e-121">**Boost SQL Server priority**</span></span>  
 <span data-ttu-id="9948e-122">Especifica se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser executado em uma prioridade de agendamento do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows mais alta que outros processos no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="9948e-122">Specifies whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="9948e-123">Para obter mais informações, consulte [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="9948e-123">For more information, see [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="9948e-124">**Usar fibras do Windows (lightweight pooling)**</span><span class="sxs-lookup"><span data-stu-id="9948e-124">**Use Windows fibers (lightweight pooling)**</span></span>  
 <span data-ttu-id="9948e-125">Use fibras do Windows em vez de threads no serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9948e-125">Use Windows fibers instead of threads for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="9948e-126">Observe que isso só está disponível no Windows 2003 Server Edition.</span><span class="sxs-lookup"><span data-stu-id="9948e-126">Note that this is only available in Windows 2003 Server Edition.</span></span> <span data-ttu-id="9948e-127">Para saber mais, veja [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="9948e-127">For more information, see [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="9948e-128">**Valores Configurados**</span><span class="sxs-lookup"><span data-stu-id="9948e-128">**Configured Values**</span></span>  
 <span data-ttu-id="9948e-129">Exibe os valores configurados para as opções nesse painel.</span><span class="sxs-lookup"><span data-stu-id="9948e-129">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="9948e-130">Se você alterar esses valores, clique em **Executando Valores** para verificar se as alterações entraram em vigor.</span><span class="sxs-lookup"><span data-stu-id="9948e-130">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="9948e-131">Se não houver nenhum, a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deverá ser reiniciada.</span><span class="sxs-lookup"><span data-stu-id="9948e-131">If they have not, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted first.</span></span>  
  
 <span data-ttu-id="9948e-132">**Executando Valores**</span><span class="sxs-lookup"><span data-stu-id="9948e-132">**Running Values**</span></span>  
 <span data-ttu-id="9948e-133">Exiba os valores que estão sendo executados para as opções neste painel.</span><span class="sxs-lookup"><span data-stu-id="9948e-133">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="9948e-134">Esses valores são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9948e-134">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9948e-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9948e-135">See Also</span></span>  
 [<span data-ttu-id="9948e-136">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9948e-136">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
