---
title: Adicionar um log para contadores de desempenho de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- performance counters [Integration Services]
- counters [Integration Services]
- logs [Integration Services], data flow counters
ms.assetid: b500d166-33ba-4b82-a92d-b0a333924e8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 489bde1b0e5769f05d1063eb0af2376b659574de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683646"
---
# <a name="add-a-log-for-data-flow-performance-counters"></a><span data-ttu-id="f8338-102">Adicionar um log para contadores de desempenho de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="f8338-102">Add a Log for Data Flow Performance Counters</span></span>
  <span data-ttu-id="f8338-103">Este procedimento descreve como adicionar um log para os contadores de desempenho fornecidos pelo mecanismo de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="f8338-103">This procedure describes how to add a log for the performance counters that the data flow engine provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8338-104">se você instalar o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] em um computador que está executando o [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)]e atualizar o computador para o [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], o processo de atualização removerá os contadores de desempenho do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="f8338-104">If you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] on a computer that is running [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)], and then upgrade that computer to [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], the upgrade process removes the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters from the computer.</span></span> <span data-ttu-id="f8338-105">Para restaurar os contadores de desempenho do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no computador, execute a Instalação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em modo de reparo.</span><span class="sxs-lookup"><span data-stu-id="f8338-105">To restore the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters on the computer, run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup in repair mode.</span></span>  
  
### <a name="to-add-logging-of-performance-counters"></a><span data-ttu-id="f8338-106">Para adicionar registros de contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="f8338-106">To add logging of performance counters</span></span>  
  
1.  <span data-ttu-id="f8338-107">No **Painel de Controle**, se você estiver usando a exibição Clássica, clique em **Ferramentas Administrativas**.</span><span class="sxs-lookup"><span data-stu-id="f8338-107">In **Control Panel**, if you are using Classic view, click **Administrative Tools**.</span></span> <span data-ttu-id="f8338-108">Se você estiver usando a exibição Categoria, clique em **Desempenho e Manutenção** e clique em **Ferramentas Administrativas**.</span><span class="sxs-lookup"><span data-stu-id="f8338-108">If you are using Category view, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="f8338-109">Clique em **Desempenho**.</span><span class="sxs-lookup"><span data-stu-id="f8338-109">Click **Performance**.</span></span>  
  
3.  <span data-ttu-id="f8338-110">Na caixa de diálogo **Desempenho** , expanda **Logs e Alertas de Desempenho**, clique com o botão direito do mouse em **Logs do Contador**e clique em **Novas Configurações de Log**.</span><span class="sxs-lookup"><span data-stu-id="f8338-110">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span> <span data-ttu-id="f8338-111">Digite o nome do log.</span><span class="sxs-lookup"><span data-stu-id="f8338-111">Type the name of the log.</span></span> <span data-ttu-id="f8338-112">Por exemplo, digite **MyLog**.</span><span class="sxs-lookup"><span data-stu-id="f8338-112">For example, type **MyLog**.</span></span>  
  
4.  <span data-ttu-id="f8338-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8338-113">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="f8338-114">Na caixa de diálogo **MyLog** , clique em **Adicionar Contadores**.</span><span class="sxs-lookup"><span data-stu-id="f8338-114">In the **MyLog** dialog box, click **Add Counters**.</span></span>  
  
6.  <span data-ttu-id="f8338-115">Clique em **Usar contadores locais do computador** para registrar contadores de desempenho no computador local ou clique em **Selecionar contadores do computador** e selecione um computador da lista para registrar os contadores de desempenho no computador especificado.</span><span class="sxs-lookup"><span data-stu-id="f8338-115">Click **Use local computer counters** to log performance counters on the local computer, or click **Select counters from computer** and then select a computer from the list to log performance counters on the specified computer.</span></span>  
  
7.  <span data-ttu-id="f8338-116">Na caixa de diálogo **Adicionar contadores** , selecione **SQL Server:SSIS Pipeline** na lista **Objeto de desempenho** .</span><span class="sxs-lookup"><span data-stu-id="f8338-116">In the **Add Counters** dialog box, select **SQL Server:SSIS Pipeline** in the **Performance object** list.</span></span>  
  
8.  <span data-ttu-id="f8338-117">Para selecionar contadores de desempenho, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f8338-117">To select performance counters, do one of the following:</span></span>  
  
    -   <span data-ttu-id="f8338-118">Selecione **Todos os contadores** para registrar todos os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="f8338-118">Select **All Counters** to log all performance counters.</span></span>  
  
    -   <span data-ttu-id="f8338-119">Selecione **Selecionar contadores na lista** e selecione o contador de desempenho a ser usado.</span><span class="sxs-lookup"><span data-stu-id="f8338-119">Select **Select counters in list** and select the performance counters to use.</span></span>  
  
9. <span data-ttu-id="f8338-120">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f8338-120">Click **Add**.</span></span>  
  
10. <span data-ttu-id="f8338-121">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="f8338-121">Click **Close**.</span></span>  
  
11. <span data-ttu-id="f8338-122">Na caixa de diálogo **MyLog** , examine a lista de registro de contadores de desempenho na lista **Contadores** .</span><span class="sxs-lookup"><span data-stu-id="f8338-122">In the **MyLog** dialog box, review the list of logging performance counters in the **Counters** list.</span></span>  
  
12. <span data-ttu-id="f8338-123">Para adicionar contadores extras, repitas as etapas de 5 a 10.</span><span class="sxs-lookup"><span data-stu-id="f8338-123">To add additional counters, repeat steps 5 through 10.</span></span>  
  
13. <span data-ttu-id="f8338-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8338-124">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8338-125">Você deve iniciar o serviço Logs e Alertas de Desempenho usando uma conta local ou uma conta de domínio que seja um membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="f8338-125">You must start the Performance Logs and Alerts service using a local account or a domain account that is a member of the Administrators group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8338-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f8338-126">See Also</span></span>  
 <span data-ttu-id="f8338-127">[Contadores de desempenho](performance/performance-counters.md) </span><span class="sxs-lookup"><span data-stu-id="f8338-127">[Performance Counters](performance/performance-counters.md) </span></span>  
 [<span data-ttu-id="f8338-128">Exibir entradas de log na janela Eventos de Log</span><span class="sxs-lookup"><span data-stu-id="f8338-128">View Log Entries in the Log Events Window</span></span>](../../2014/integration-services/view-log-entries-in-the-log-events-window.md)  
  
  
