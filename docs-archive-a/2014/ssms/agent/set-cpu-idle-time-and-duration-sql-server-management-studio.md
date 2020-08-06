---
title: Definir o momento e a duração de ociosidade da CPU (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CPU [SQL Server], idle conditions
- time [SQL Server], CPU idle and duration
- duration of CPU idle [SQL Server]
- SQL Server Agent, CPU idle conditions
- idle time [SQL Server]
ms.assetid: 8647b465-d899-4cc7-9640-134a506d0a2e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1660f6d70977b8f590a18adf952a6a19f32a26cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686014"
---
# <a name="set-cpu-idle-time-and-duration-sql-server-management-studio"></a><span data-ttu-id="f2261-102">Definir o momento e a duração de ociosidade da CPU (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f2261-102">Set CPU Idle Time and Duration (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f2261-103">Este tópico explica como definir a condição de ociosidade de CPU para seu servidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2261-103">This topic explains how to define the CPU idle condition for your server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f2261-104">A definição de ociosidade de CPU influencia como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent responde a eventos.</span><span class="sxs-lookup"><span data-stu-id="f2261-104">The CPU idle definition influences how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent responds to events.</span></span> <span data-ttu-id="f2261-105">Por exemplo, suponhamos que você defina a condição de ociosidade de CPU como o uso médio de CPU abaixo de 10 por cento, com permanência de 10 minutos nesse nível.</span><span class="sxs-lookup"><span data-stu-id="f2261-105">For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes.</span></span> <span data-ttu-id="f2261-106">Assim, se você tiver definido trabalhos para execução sempre que a CPU do servidor estiver em condição de ociosidade, o trabalho será iniciado quando o uso de CPU cair abaixo de 10 por cento e permanecer por 10 minutos nesse nível.</span><span class="sxs-lookup"><span data-stu-id="f2261-106">Then if you have defined jobs to execute whenever the server CPU reaches an idle condition, the job will start when the CPU usage falls below 10 percent and remains at that level for 10 minutes.</span></span> <span data-ttu-id="f2261-107">Caso se trate de um trabalho com impacto significativo sobre o desempenho do servidor, é muito importante a definição da condição de ociosidade de CPU.</span><span class="sxs-lookup"><span data-stu-id="f2261-107">If this is a job that significantly impacts the performance of your server, how you define the CPU idle condition is important.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f2261-108">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2261-108">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-cpu-idle-time-and-duration"></a><span data-ttu-id="f2261-109">Para definir o momento e a duração da ociosidade de CPU</span><span class="sxs-lookup"><span data-stu-id="f2261-109">To set CPU idle time and duration</span></span>  
  
1.  <span data-ttu-id="f2261-110">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="f2261-110">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f2261-111">Clique com o botão direito do mouse em **SQL Server Agent**, clique em **Propriedades**e selecione a página **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="f2261-111">Right-click **SQL Server Agent**, click **Properties**, and select the **Advanced** page.</span></span>  
  
3.  <span data-ttu-id="f2261-112">Em **Condição de CPU ociosa**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f2261-112">Under **Idle CPU condition**, do the following:</span></span>  
  
    -   <span data-ttu-id="f2261-113">Marque **Definir condição de CPU ociosa**.</span><span class="sxs-lookup"><span data-stu-id="f2261-113">Check **Define idle CPU condition.**</span></span>  
  
    -   <span data-ttu-id="f2261-114">Especifique um percentual na caixa **O uso médio de CPU cai abaixo de** (em todas as CPUs).</span><span class="sxs-lookup"><span data-stu-id="f2261-114">Specify a percentage for the **Average CPU usage falls below** (across all CPUs) box.</span></span> <span data-ttu-id="f2261-115">Isso define o nível de uso abaixo do qual a CPU deve cair para ser considerada ociosa.</span><span class="sxs-lookup"><span data-stu-id="f2261-115">This sets the usage level that the CPU must fall below before it is considered idle.</span></span>  
  
    -   <span data-ttu-id="f2261-116">Especifique um número de segundos na caixa **E permanece abaixo desse nível por** .</span><span class="sxs-lookup"><span data-stu-id="f2261-116">Specify a number of seconds for the **And remains below this level for** box.</span></span> <span data-ttu-id="f2261-117">Isto define a duração da permanência sob o uso mínimo de CPU para que ela seja considerada ociosa.</span><span class="sxs-lookup"><span data-stu-id="f2261-117">This sets the duration that the minimum CPU usage must remain at before it is considered idle.</span></span>  
  
  
