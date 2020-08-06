---
title: Configurar um alerta de banco de dados do SQL Server (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
ms.assetid: 65d2c5c1-921f-4eff-9ef7-149170ab61e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 090eeda2c134857df18d083ce06d460214aa4dfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583551"
---
# <a name="set-up-a-sql-server-database-alert-windows"></a><span data-ttu-id="ae378-102">Configurar um alerta de banco de dados do SQL Server (Windows)</span><span class="sxs-lookup"><span data-stu-id="ae378-102">Set Up a SQL Server Database Alert (Windows)</span></span>
  <span data-ttu-id="ae378-103">Usando o Monitor do Sistema, é possível criar um alerta a ser emitido quando um valor-limite de um contador do Monitor do Sistema for atingido.</span><span class="sxs-lookup"><span data-stu-id="ae378-103">Using System Monitor, you can create an alert to be raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="ae378-104">Em resposta ao alerta, o Monitor do Sistema pode iniciar um aplicativo, tal como um aplicativo personalizado escrito para lidar com a condição de alerta.</span><span class="sxs-lookup"><span data-stu-id="ae378-104">In response to the alert, System Monitor can launch an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="ae378-105">Por exemplo, você pode criar um alerta a ser emitido quando o número de deadlocks exceder um valor específico.</span><span class="sxs-lookup"><span data-stu-id="ae378-105">For example, you can create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="ae378-106">Os alertas também podem ser definidos usando o Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="ae378-106">Alerts also can be defined using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="ae378-107">Para obter mais informações, consulte [Alertas](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="ae378-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
### <a name="to-set-up-a-sql-server-database-alert"></a><span data-ttu-id="ae378-108">Para configurar um alerta de banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae378-108">To set up a SQL Server database alert</span></span>  
  
1.  <span data-ttu-id="ae378-109">Na árvore de navegação da janela Desempenho, expanda **Logs e Alertas de Desempenho**.</span><span class="sxs-lookup"><span data-stu-id="ae378-109">On the navigation tree of the Performance window, expand **Performance Logs and Alerts**.</span></span>  
  
2.  <span data-ttu-id="ae378-110">Clique com o botão direito do mouse em **Alertas**e clique em **Novas Configurações de Alerta**.</span><span class="sxs-lookup"><span data-stu-id="ae378-110">Right-click **Alerts**, and then click **New Alert Settings**.</span></span>  
  
3.  <span data-ttu-id="ae378-111">Na caixa de diálogo **Novas Configurações de Alerta** , digite um nome para o novo alerta e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae378-111">In the **New Alert Settings** dialog box, type a name for the new alert, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="ae378-112">Na guia **Geral** da caixa de diálogo do novo alerta, adicione um **Comentário**e clique em **Adicionar** para adicionar um contador ao alerta.</span><span class="sxs-lookup"><span data-stu-id="ae378-112">On the **General** tab of the dialog box for the new alert, add a **Comment**, and click **Add** to add a counter to the alert.</span></span>  
  
     <span data-ttu-id="ae378-113">Todos os alertas devem ter pelo menos um contador.</span><span class="sxs-lookup"><span data-stu-id="ae378-113">All alerts must have at least one counter.</span></span>  
  
5.  <span data-ttu-id="ae378-114">Na caixa de diálogo Adicionar Contadores, selecione um objeto do SQL Server na lista **Objeto de Desempenho** e um contador em **Selecionar contadores na lista**.</span><span class="sxs-lookup"><span data-stu-id="ae378-114">In the Add Counters dialog box, select a SQL Server object from the **Performance Object** list, and then select a counter from the **Select counters from list**.</span></span>  
  
6.  <span data-ttu-id="ae378-115">Para adicionar o contador ao alerta, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ae378-115">To add the counter to the alert, click **Add**.</span></span> <span data-ttu-id="ae378-116">Você pode continuar adicionando contadores ou clicar em **Fechar** para retornar à caixa de diálogo do novo alerta.</span><span class="sxs-lookup"><span data-stu-id="ae378-116">You can continue to add counters, or you can click **Close** to return to the dialog box for the new alert.</span></span>  
  
7.  <span data-ttu-id="ae378-117">Na caixa de diálogo do novo alerta, clique em **Acima** ou **Abaixo**na lista **Alertar quando o valor estiver** e insira um valor-limite em **Limite**.</span><span class="sxs-lookup"><span data-stu-id="ae378-117">In the new alert dialog box, click either **Over** or **Under**in the **Alert when the value is** list, and then enter a threshold value in **Limit**.</span></span>  
  
     <span data-ttu-id="ae378-118">O alerta será gerado quando o valor do contador estiver acima ou abaixo do valor-limite (segundo a opção por **Acima** ou **Abaixo**).</span><span class="sxs-lookup"><span data-stu-id="ae378-118">The alert is generated when the value for the counter is more than or less than the threshold value (depending on whether you clicked **Over** or **Under**).</span></span>  
  
8.  <span data-ttu-id="ae378-119">Nas caixas **Amostrar dados a cada** , defina a frequência de amostragem.</span><span class="sxs-lookup"><span data-stu-id="ae378-119">In the **Sample data every** boxes, set the sampling frequency.</span></span>  
  
9. <span data-ttu-id="ae378-120">Na guia **Ação** , defina as ações que devem ocorrer sempre que o alerta for disparado.</span><span class="sxs-lookup"><span data-stu-id="ae378-120">On the **Action** tab, set actions to occur every time the alert is triggered.</span></span>  
  
10. <span data-ttu-id="ae378-121">Na guia **Agendar** , defina o agendamento de início e interrupção da verificação do alerta.</span><span class="sxs-lookup"><span data-stu-id="ae378-121">On the **Schedule** tab, set the start and stop schedule for the alert scan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae378-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae378-122">See Also</span></span>  
 [<span data-ttu-id="ae378-123">Criar um alerta de Banco de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae378-123">Create a SQL Server Database Alert</span></span>](../performance-monitor/create-a-sql-server-database-alert.md)  
  
  
