---
title: Somente usuários sysadmin podem gravar arquivos de log de etapa de trabalho no sistema de arquivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- job step log files [SQL Server Agent]
- log files [SQL Server Agent]
- writing job step log files
ms.assetid: d26a7cef-1a60-4c95-b9df-f8b4fec59f9b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e2bf5095ac1e6b67f6c6f3f87444879913916e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574452"
---
# <a name="only-sysadmin-users-can-write-job-step-log-files-to-the-file-system"></a><span data-ttu-id="c2ba2-102">Somente usuários sysadmin podem gravar arquivos de log da etapa de trabalho no sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="c2ba2-102">Only sysadmin users can write job step log files to the file system</span></span>
  <span data-ttu-id="c2ba2-103">O [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] grava, opcionalmente, um log para cada etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-103">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] optionally writes a log for each job step.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c2ba2-104">Componente</span><span class="sxs-lookup"><span data-stu-id="c2ba2-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c2ba2-105">Agent</span><span class="sxs-lookup"><span data-stu-id="c2ba2-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="c2ba2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c2ba2-106">Description</span></span>  
 <span data-ttu-id="c2ba2-107">No [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] , o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pode gravar logs no sistema de arquivos para trabalhos que pertencem a membros da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c2ba2-107">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system for jobs that are owned by members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="c2ba2-108">Se o proprietário do trabalho não for um membro da função **sysadmin** e se a conta proxy estiver habilitada, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent poderá gravar logs no sistema de arquivos usando as credenciais da conta proxy.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-108">If the job owner is not a member of the **sysadmin** role and if the proxy account is enabled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system by using the credentials of the proxy account.</span></span>  
  
 <span data-ttu-id="c2ba2-109">Após a atualização, os trabalhos que pertencem a usuários que não são membros da função de servidor fixa **sysadmin** não podem mais gravar logs no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-109">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** fixed server role can no longer write logs to the file system.</span></span> <span data-ttu-id="c2ba2-110">Em vez disso, esses usuários podem selecionar a opção para gravar seus logs em uma tabela no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c2ba2-110">Instead, these users can select the option to write their logs to a table in the **msdb** database.</span></span> <span data-ttu-id="c2ba2-111">Os membros da função **sysadmin** ainda podem gravar arquivos de log no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-111">Members of the **sysadmin** role can still write log files to the file system.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c2ba2-112">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="c2ba2-112">Corrective Action</span></span>  
 <span data-ttu-id="c2ba2-113">Após a atualização, os trabalhos que são de propriedade de usuários que não são membros da função **sysadmin** continuarão a ser executados, mas os logs não serão criados.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-113">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** role will continue to run, but logs will not be created.</span></span> <span data-ttu-id="c2ba2-114">Para registrar etapas de trabalho em uma tabela, os usuários que não são membros da função **sysadmin** devem atualizar manualmente seus trabalhos.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-114">To log job steps to a table, users who are not members of the **sysadmin** role must manually update their jobs.</span></span>  
  
 <span data-ttu-id="c2ba2-115">Para obter mais informações, consulte os tópicos ‘Criando trabalhos, ‘Criando etapas de trabalhos' e ‘Manuseando várias etapas de trabalho’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2ba2-115">For more information, see the topics "Creating Jobs," "Creating Job Steps," and "Handling Multiple Job Steps" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ba2-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2ba2-116">See Also</span></span>  
 [<span data-ttu-id="c2ba2-117">Problemas de atualização do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c2ba2-117">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
