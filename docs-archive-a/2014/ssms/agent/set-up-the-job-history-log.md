---
title: Configurar o log do histórico do trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 018e5c49-d3a0-4504-851a-f70996a34bb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb42e1daaee8a3a9e5ae9cc3c09a8cc42dcbff56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678561"
---
# <a name="set-up-the-job-history-log"></a><span data-ttu-id="17998-102">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="17998-102">Set Up the Job History Log</span></span>
  <span data-ttu-id="17998-103">Este tópico descreve como configurar o log de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] histórico de trabalhos do Agent.</span><span class="sxs-lookup"><span data-stu-id="17998-103">This topic describes how to set up the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>  
  
-   <span data-ttu-id="17998-104">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="17998-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="17998-105">**Para configurar o log do histórico de trabalhos usando:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="17998-105">**To setup the job history log, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="17998-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="17998-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="17998-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="17998-107">Security</span></span>  
 <span data-ttu-id="17998-108">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="17998-108">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="17998-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17998-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="17998-110">**Para configurar o log do histórico do trabalho**</span><span class="sxs-lookup"><span data-stu-id="17998-110">**To set up the job history log**</span></span>  
  
1.  <span data-ttu-id="17998-111">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="17998-111">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="17998-112">Clique com o botão direito do mouse em **SQL Server Agent**e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="17998-112">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="17998-113">Na caixa de diálogo **Propriedades do SQL Server Agent** , selecione a página **Histórico** .</span><span class="sxs-lookup"><span data-stu-id="17998-113">In the **SQL Server Agent Properties** dialog box, select the **History** page.</span></span>  
  
4.  <span data-ttu-id="17998-114">Escolha dentre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="17998-114">Choose from the following options:</span></span>  
  
    1.  <span data-ttu-id="17998-115">Marque **Limitar tamanho do log do histórico de trabalho**e indique o número máximo de linhas para o log de histórico de trabalhos e o número máximo de linhas por trabalho.</span><span class="sxs-lookup"><span data-stu-id="17998-115">Check **Limit size of job history log**, and then type the maximum number of rows for the job history log, and the maximum number of rows per job.</span></span>  
  
    2.  <span data-ttu-id="17998-116">Marque **Remover automaticamente o histórico do agente**e especifique um período de tempo, para que os históricos anteriores a ele sejam excluídos do log.</span><span class="sxs-lookup"><span data-stu-id="17998-116">Check **Automatically remove agent history**, and specify a time period, such that history older than this period will be purged from the log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17998-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="17998-117">See Also</span></span>  
 <span data-ttu-id="17998-118">[Implementar trabalhos](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="17998-118">[Implement Jobs](implement-jobs.md) </span></span>  
 <span data-ttu-id="17998-119">[Monitorar atividade do trabalho](monitor-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="17998-119">[Monitor Job Activity](monitor-job-activity.md) </span></span>  
 [<span data-ttu-id="17998-120">Criar trabalhos</span><span class="sxs-lookup"><span data-stu-id="17998-120">Create Jobs</span></span>](create-jobs.md)  
  
  
