---
title: Definir opções de rastreamento global (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- global trace options [SQL Server]
ms.assetid: 2854608a-c3c7-4eb8-b567-034bfec4b1a9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f0809ae11776e1bddf42c189b86f48689ff4859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569783"
---
# <a name="set-global-trace-options-sql-server-profiler"></a><span data-ttu-id="9cfa1-102">Definir opções de rastreamento globais (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="9cfa1-102">Set Global Trace Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="9cfa1-103">Este tópico descreve como definir opções que se aplicam a todos os rastreamentos criados com uma instância específica do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cfa1-103">This topic describes how to set options that apply to all traces that are created with a specific instance of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-global-trace-options"></a><span data-ttu-id="9cfa1-104">Para definir opções de rastreamento globais</span><span class="sxs-lookup"><span data-stu-id="9cfa1-104">To set global trace options</span></span>  
  
1.  <span data-ttu-id="9cfa1-105">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-105">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="9cfa1-106">Na caixa de diálogo **Opções Gerais**, clique em **Escolher Fonte**para modificar as opções de exibição e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-106">In the **General Options**dialog box, click **Choose Font**to modify the display options, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9cfa1-107">Opcionalmente, selecione **Iniciar rastreamento imediatamente após estabelecer a conexão**.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-107">Optionally, select **Start tracing immediately after making connection**.</span></span>  
  
4.  <span data-ttu-id="9cfa1-108">Opcionalmente, selecione **Atualizar definição de rastreamento quando a versão do provedor for alterada**.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-108">Optionally, select **Update trace definition when provider version changes**.</span></span> <span data-ttu-id="9cfa1-109">Essa opção é recomendada e encontra-se selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-109">This option is recommended and is selected by default.</span></span> <span data-ttu-id="9cfa1-110">Quando essa opção está selecionada, a definição do rastreamento é atualizada automaticamente para a versão atual do servidor em que o rastreamento é executado.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-110">When this option is selected, the trace definition is automatically updated to the current version of the server where tracing is performed.</span></span>  
  
5.  <span data-ttu-id="9cfa1-111">Opcionalmente, especifique como o servidor deve gerenciar arquivos de substituição:</span><span class="sxs-lookup"><span data-stu-id="9cfa1-111">Optionally, specify how the server should manage rollover files:</span></span>  
  
    -   <span data-ttu-id="9cfa1-112">Selecione **Carregar todos os arquivos de substituição em sequência, sem perguntar** , para carregar arquivos de substituição automaticamente durante a reprodução.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-112">Select **Load all rollover files in sequence without prompting** to automatically load rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="9cfa1-113">Selecione **Perguntar antes de carregar arquivos de substituição** para controlar arquivos de substituição durante a repetição.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-113">Select **Prompt before loading rollover files** to control rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="9cfa1-114">Selecione **Nunca carregar arquivos de substituição subsequentes** para reproduzir apenas um arquivo por vez.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-114">Select **Never load subsequent rollover files** to replay only one file at a time.</span></span>  
  
6.  <span data-ttu-id="9cfa1-115">Opcionalmente, defina as opções de repetição:</span><span class="sxs-lookup"><span data-stu-id="9cfa1-115">Optionally, set replay options:</span></span>  
  
    -   <span data-ttu-id="9cfa1-116">**Número padrão de threads de reprodução** controla o número de threads de processador a ser usado durante a reprodução.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-116">**Default number of replay threads** controls the number of processor threads to use during replay.</span></span> <span data-ttu-id="9cfa1-117">Um número maior de threads faz com que a repetição se conclua mais rápido, mas degrada o desempenho do servidor durante a repetição.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-117">A higher number of threads causes replay to complete faster, but causes server performance to degrade during replay.</span></span> <span data-ttu-id="9cfa1-118">A configuração recomendada é **4**.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-118">The recommended setting is **4**.</span></span> <span data-ttu-id="9cfa1-119">A tabela a seguir lista as opções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="9cfa1-119">The following table lists the available options:</span></span>  
  
        |<span data-ttu-id="9cfa1-120">Valor</span><span class="sxs-lookup"><span data-stu-id="9cfa1-120">Value</span></span>|<span data-ttu-id="9cfa1-121">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9cfa1-121">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="9cfa1-122">**2**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-122">**2**</span></span>|<span data-ttu-id="9cfa1-123">Valor mínimo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-123">Minimum value.</span></span> <span data-ttu-id="9cfa1-124">Usar dois threads na repetição.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-124">Use two threads to replay.</span></span>|  
        |<span data-ttu-id="9cfa1-125">**4**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-125">**4**</span></span>|<span data-ttu-id="9cfa1-126">Valor padrão.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-126">Default value.</span></span>|  
        |<span data-ttu-id="9cfa1-127">**255**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-127">**255**</span></span>|<span data-ttu-id="9cfa1-128">Valor máximo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-128">Maximum value.</span></span> <span data-ttu-id="9cfa1-129">Definir um valor máximo prejudicará o desempenho de outros processos.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-129">Setting a maximum value will impede performance for other processes.</span></span>|  
  
    -   <span data-ttu-id="9cfa1-130">**Intervalo de espera padrão do monitor de integridade (s)** define o período máximo, em segundos, durante o qual um thread de repetição pode bloquear outro processo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-130">**Default health monitor wait interval (sec)** sets the maximum amount of time that a replay thread can block another process in seconds.</span></span> <span data-ttu-id="9cfa1-131">A tabela a seguir explica os valores.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-131">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="9cfa1-132">Valor</span><span class="sxs-lookup"><span data-stu-id="9cfa1-132">Value</span></span>|<span data-ttu-id="9cfa1-133">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9cfa1-133">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="9cfa1-134">**0**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-134">**0**</span></span>|<span data-ttu-id="9cfa1-135">Valor mínimo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-135">Minimum value.</span></span> <span data-ttu-id="9cfa1-136">Uma configuração **0** significa que o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] nunca interromperá um processo de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-136">A setting of **0** means that [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will never stop a blocking process.</span></span>|  
        |<span data-ttu-id="9cfa1-137">**3600**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-137">**3600**</span></span>|<span data-ttu-id="9cfa1-138">Valor padrão.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-138">Default value.</span></span> <span data-ttu-id="9cfa1-139">Permite processos de bloqueio que não excedam **3600** segundos, ou uma hora.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-139">Allow blocking processes that do not exceed **3600** seconds, or one hour.</span></span>|  
        |<span data-ttu-id="9cfa1-140">**86400**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-140">**86400**</span></span>|<span data-ttu-id="9cfa1-141">Valor máximo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-141">Maximum value.</span></span> <span data-ttu-id="9cfa1-142">Permite processos de bloqueio que não excedam **86400** segundos, ou um dia.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-142">Allow blocking processes that do not exceed **86400** seconds, or one day.</span></span>|  
  
    -   <span data-ttu-id="9cfa1-143">**Intervalo de sondagem padrão do monitor de integridade (s)** define a frequência de sondagem dos threads de reprodução para processos de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-143">**Default health monitor poll interval (sec)** sets the frequency to poll replay threads for blocking processes.</span></span> <span data-ttu-id="9cfa1-144">A tabela a seguir explica os valores.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-144">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="9cfa1-145">Valor</span><span class="sxs-lookup"><span data-stu-id="9cfa1-145">Value</span></span>|<span data-ttu-id="9cfa1-146">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9cfa1-146">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="9cfa1-147">**1**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-147">**1**</span></span>|<span data-ttu-id="9cfa1-148">Valor mínimo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-148">Minimum value.</span></span> <span data-ttu-id="9cfa1-149">Uma configuração **1** significa que o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] sondará processos de bloqueio uma vez a cada segundo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-149">A setting of **1** means [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will poll for blocking processes once per second.</span></span>|  
        |<span data-ttu-id="9cfa1-150">**60**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-150">**60**</span></span>|<span data-ttu-id="9cfa1-151">Valor padrão.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-151">Default value.</span></span> <span data-ttu-id="9cfa1-152">Sondar processos de bloqueio uma vez por minuto.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-152">Poll for blocking processes once per minute.</span></span>|  
        |<span data-ttu-id="9cfa1-153">**86400**</span><span class="sxs-lookup"><span data-stu-id="9cfa1-153">**86400**</span></span>|<span data-ttu-id="9cfa1-154">Valor máximo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-154">Maximum value.</span></span> <span data-ttu-id="9cfa1-155">Sondar processos de bloqueio uma vez a cada **86.400** segundos, ou um dia.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-155">Poll for blocking processes once per **86400** seconds, or one day.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cfa1-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9cfa1-156">See Also</span></span>  
 <span data-ttu-id="9cfa1-157">[Definir padrões de exibição de rastreamento &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="9cfa1-157">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="9cfa1-158">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9cfa1-158">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
