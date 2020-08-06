---
title: Excluir trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
author: stevestein
ms.author: sstein
ms.openlocfilehash: f66387a1334f91c29b8edddad293d76064430b39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683906"
---
# <a name="delete-jobs"></a><span data-ttu-id="d0496-102">excluir trabalhos</span><span class="sxs-lookup"><span data-stu-id="d0496-102">Delete Jobs</span></span>
  <span data-ttu-id="d0496-103">Um trabalho é uma série especificada de operações executadas sequencialmente pelo SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="d0496-103">A job is a specified series of operations performed sequentially by SQL Server Agent.</span></span> <span data-ttu-id="d0496-104">Por padrão, os trabalhos não são excluídos quando a execução termina.</span><span class="sxs-lookup"><span data-stu-id="d0496-104">By default, jobs are not deleted when execution finishes.</span></span> <span data-ttu-id="d0496-105">Você pode excluir um ou mais trabalhos do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent independentemente do êxito ou da falha do trabalho.</span><span class="sxs-lookup"><span data-stu-id="d0496-105">You can delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs regardless of success or failure of the job.</span></span> <span data-ttu-id="d0496-106">Também é possível configurar o [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para excluir trabalhos automaticamente quando eles obtiverem êxito, falharem ou forem concluídos.</span><span class="sxs-lookup"><span data-stu-id="d0496-106">You can also configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>  
  
 <span data-ttu-id="d0496-107">Por padrão, os membros da função de servidor fixa **sysadmin** podem executar o sp_delete_job &#40;procedimento armazenado do sistema [&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) para excluir um trabalho.</span><span class="sxs-lookup"><span data-stu-id="d0496-107">By default, members of the **sysadmin** fixed server role can execute the [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) system stored procedure to delete a job.</span></span> <span data-ttu-id="d0496-108">Deve ser concedida a outros usuários uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados **msdb** :</span><span class="sxs-lookup"><span data-stu-id="d0496-108">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="d0496-109">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="d0496-109">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="d0496-110">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="d0496-110">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="d0496-111">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="d0496-111">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="d0496-112">Para obter detalhes sobre as permissões dessas funções, consulte [Funções de banco de dados fixas do SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d0496-112">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="d0496-113">Membros da função de servidor fixa **sysadmin** podem executar **sp_delete_job** para excluir qualquer trabalho.</span><span class="sxs-lookup"><span data-stu-id="d0496-113">Members of the **sysadmin** fixed server role can execute **sp_delete_job** to delete any job.</span></span> <span data-ttu-id="d0496-114">Um usuário que não for membro da função de servidor fixa **sysadmin** poderá excluir somente os trabalhos que forem de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="d0496-114">A user that is not a member of the **sysadmin** fixed server role can only delete jobs owned by that user.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d0496-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d0496-115">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0496-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d0496-116">**Description**</span></span>|<span data-ttu-id="d0496-117">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="d0496-117">**Topic**</span></span>|  
|<span data-ttu-id="d0496-118">Descreve como excluir um ou mais trabalhos do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="d0496-118">Describes how to delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="d0496-119">Excluir um ou mais trabalhos</span><span class="sxs-lookup"><span data-stu-id="d0496-119">Delete One or More Jobs</span></span>](delete-one-or-more-jobs.md)|  
|<span data-ttu-id="d0496-120">Descreve como configurar o [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para excluir trabalhos automaticamente quando eles obtiverem êxito, falharem ou forem concluídos.</span><span class="sxs-lookup"><span data-stu-id="d0496-120">Describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>|[<span data-ttu-id="d0496-121">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="d0496-121">Automatically Delete a Job</span></span>](automatically-delete-a-job.md)|  
  
  
