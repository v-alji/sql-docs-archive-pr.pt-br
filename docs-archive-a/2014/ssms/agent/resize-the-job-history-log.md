---
title: Redimensionar o log do histórico do trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- resizing job history log
- size [SQL Server], job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: ddee1ce8-9d1b-4017-9894-bf7256aed95d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c25cc43295d47b2bc19d48b5b257dbbe6bcfe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572329"
---
# <a name="resize-the-job-history-log"></a><span data-ttu-id="7875f-102">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="7875f-102">Resize the Job History Log</span></span>
  <span data-ttu-id="7875f-103">Este tópico descreve como definir limites de tamanho para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logs de histórico de trabalhos do Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7875f-103">This topic describes how to set size limits for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history logs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="7875f-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7875f-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7875f-105">Segurança</span><span class="sxs-lookup"><span data-stu-id="7875f-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7875f-106">**Para definir limites de tamanho para logs de histórico de trabalho, usando:**</span><span class="sxs-lookup"><span data-stu-id="7875f-106">**To set size limits for job history logs, using:**</span></span>  
  
     [<span data-ttu-id="7875f-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7875f-107">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7875f-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7875f-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7875f-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="7875f-109">Security</span></span>  
 <span data-ttu-id="7875f-110">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="7875f-110">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="7875f-111">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7875f-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-raw-size"></a><span data-ttu-id="7875f-112">Para redimensionar o log do histórico do trabalho segundo um tamanho bruto</span><span class="sxs-lookup"><span data-stu-id="7875f-112">To resize the job history log based on raw size</span></span>  
  
1.  <span data-ttu-id="7875f-113">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="7875f-113">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7875f-114">Clique com o botão direito do mouse em **SQL Server Agent**e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7875f-114">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7875f-115">Selecione a página **Histórico** e confirme se a opção **Limitar tamanho do log do histórico de trabalhos**está marcada.</span><span class="sxs-lookup"><span data-stu-id="7875f-115">Select the **History** page, and then confirm that **Limit size of job history log**is checked.</span></span>  
  
4.  <span data-ttu-id="7875f-116">Na caixa **Tamanho máximo do log do histórico de trabalho** , insira o número máximo de linhas que o log de histórico do trabalho deve permitir.</span><span class="sxs-lookup"><span data-stu-id="7875f-116">In the **Maximum job history log size** box, enter the maximum number of rows the job history log should allow.</span></span>  
  
5.  <span data-ttu-id="7875f-117">Na caixa **Máximo de linhas do log do histórico de trabalho por trabalho** , insira o número máximo de linhas que o log de histórico do trabalho deve permitir para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="7875f-117">In the **Maximum job history rows per job** box, enter the maximum number of job history rows to allow for a job.</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-time"></a><span data-ttu-id="7875f-118">Para redimensionar o log de histórico de trabalho segundo o tempo</span><span class="sxs-lookup"><span data-stu-id="7875f-118">To resize the job history log based on time</span></span>  
  
1.  <span data-ttu-id="7875f-119">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="7875f-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7875f-120">Clique com o botão direito do mouse em **SQL Server Agent**e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7875f-120">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7875f-121">Selecione a página **Histórico** e clique em **Remover automaticamente o histórico do agente**.</span><span class="sxs-lookup"><span data-stu-id="7875f-121">Select the **History** page, and then click **Automatically remove agent history**.</span></span>  
  
4.  <span data-ttu-id="7875f-122">Selecione o número apropriado de **Dia(s)**, **Semana(s)** ou **Mês (meses)**.</span><span class="sxs-lookup"><span data-stu-id="7875f-122">Select the appropriate number of **Days(s)**, **Week(s)**, or **Month(s)**.</span></span>  
  
  
