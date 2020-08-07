---
title: Definir o desligamento da execução de trabalhos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
- SQL Server Agent jobs, execution shutdowns
ms.assetid: ac23e88f-53fc-41de-bb16-0c27c002d5a5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e60807676c3c54faf1d44de318ff0a31c2e20b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582262"
---
# <a name="set-job-execution-shutdown-sql-server-management-studio"></a><span data-ttu-id="c04c6-102">Set Job Execution Shutdown (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c04c6-102">Set Job Execution Shutdown (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c04c6-103">Este tópico descreve como definir o tempo que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent aguardará até que os trabalhos em execução sejam concluídos antes que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] próprio agente seja concluído no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c04c6-103">This topic describes how to set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c04c6-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c04c6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c04c6-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c04c6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c04c6-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="c04c6-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c04c6-107">**Para definir um tempo de desligamento para um trabalho do SQL Server Agent, usando:**</span><span class="sxs-lookup"><span data-stu-id="c04c6-107">**To set a shutdown time for a SQL Server Agent job, using:**</span></span>  
  
     [<span data-ttu-id="c04c6-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c04c6-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c04c6-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c04c6-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c04c6-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="c04c6-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c04c6-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="c04c6-111">Permissions</span></span>  
 <span data-ttu-id="c04c6-112">Por padrão, os membros da função de servidor fixa **sysadmin** podem marcar a hora que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent esperará pela conclusão de trabalhos em execução antes que o próprio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent finalize-os.</span><span class="sxs-lookup"><span data-stu-id="c04c6-112">By default, members of the **sysadmin** fixed server role can set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span> <span data-ttu-id="c04c6-113">Deve ser concedida a outros usuários uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados **msdb** :</span><span class="sxs-lookup"><span data-stu-id="c04c6-113">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="c04c6-114">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="c04c6-114">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="c04c6-115">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="c04c6-115">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="c04c6-116">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="c04c6-116">**SQLAgentOperatorRole**</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c04c6-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c04c6-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-execution-shutdown"></a><span data-ttu-id="c04c6-118">Para definir desligamento de execução de trabalho</span><span class="sxs-lookup"><span data-stu-id="c04c6-118">To set job execution shutdown</span></span>  
  
1.  <span data-ttu-id="c04c6-119">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor no qual você deseja definir um intervalo de desligamento de execução de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c04c6-119">In **Object Explorer,** , click the plus sign to expand the server where you want to set a job execution shutdown interval.</span></span>  
  
2.  <span data-ttu-id="c04c6-120">Clique com o botão direito do mouse em **SQL Server Agent** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c04c6-120">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="c04c6-121">Em **Selecione uma página**, selecione **Sistema de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c04c6-121">Under **Select a page**, select **Job System**.</span></span>  
  
4.  <span data-ttu-id="c04c6-122">Defina o **Intervalo de tempo limite de desligamento** em segundos para aumentar ou diminuir o intervalo do tempo limite para o desligamento.</span><span class="sxs-lookup"><span data-stu-id="c04c6-122">Set the **Shutdown time-out interval** in seconds to increase or decrease the shutdown time-out interval.</span></span> <span data-ttu-id="c04c6-123">Isso determina quanto tempo o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent aguardará pelo término dos trabalhos em execução antes de o próprio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent terminar.</span><span class="sxs-lookup"><span data-stu-id="c04c6-123">This determines how long [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span>  
  
  
