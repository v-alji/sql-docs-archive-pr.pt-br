---
title: Solucionar problemas de trabalhos com multisservidor que usam proxies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], multiserver jobs
- jobs [SQL Server Agent], multiserver jobs using proxies
ms.assetid: fc579bd3-010c-4f72-8b5c-d0cc18a1f280
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19de975ef5e1f22c93cec72a5014a01da5b03dd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680269"
---
# <a name="troubleshoot-multiserver-jobs-that-use-proxies"></a><span data-ttu-id="7b779-102">Solucionar problemas de trabalhos multisservidor que usam proxies</span><span class="sxs-lookup"><span data-stu-id="7b779-102">Troubleshoot Multiserver Jobs That Use Proxies</span></span>
  <span data-ttu-id="7b779-103">Trabalhos distribuídos cujas etapas estejam associadas a um proxy são executados no contexto da conta proxy no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7b779-103">Distributed jobs whose steps are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="7b779-104">Se as etapas de trabalho que usam contas proxy falharem ao serem baixadas do servidor mestre, verifique a coluna **error_message** da tabela **sysdownloadlist** no banco de dados **msdb** quanto às seguintes mensagens de erro:</span><span class="sxs-lookup"><span data-stu-id="7b779-104">If job steps that use proxy accounts fail when downloaded from the master server, check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="7b779-105">"A etapa do trabalho requer uma conta proxy. Entretanto, a verificação de proxy está desabilitada no servidor de destino."</span><span class="sxs-lookup"><span data-stu-id="7b779-105">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="7b779-106">Para resolver esse erro, defina o **\ HKEY_LOCAL_MACHINE \SOFTWARE\MICROSOFT\MICROSOFT SQL Server\MSSQL.** _ \<n_> **\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** subchave do registro como **1 (true)**.</span><span class="sxs-lookup"><span data-stu-id="7b779-106">To resolve this error, set the **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL.**_\<n_>**\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** registry subkey to **1 (true)**.</span></span> <span data-ttu-id="7b779-107">Por padrão, essa subchave é definida como **0** ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="7b779-107">By default, this subkey is set to **0** (`false`).</span></span> <span data-ttu-id="7b779-108">O valor de **MSSQL.**\<*n*></span><span class="sxs-lookup"><span data-stu-id="7b779-108">The value of **MSSQL.**\<*n*></span></span> <span data-ttu-id="7b779-109">é o nome da instância; por exemplo, **MSSQL. 1** ou **MSSQL. 3**.</span><span class="sxs-lookup"><span data-stu-id="7b779-109">is the instance name; for example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
-   <span data-ttu-id="7b779-110">"Proxy não localizado."</span><span class="sxs-lookup"><span data-stu-id="7b779-110">"Proxy not found."</span></span>  
  
     <span data-ttu-id="7b779-111">Para resolver este erro, verifique se existe uma conta proxy no servidor de destino com o mesmo nome da conta proxy do servidor mestre sob a qual a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="7b779-111">To resolve this error, make sure a proxy account exists on the target server with the same name as the master server proxy account under which the job step runs.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b779-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b779-112">See Also</span></span>  
 [<span data-ttu-id="7b779-113">Criar um ambiente multisservidor</span><span class="sxs-lookup"><span data-stu-id="7b779-113">Create a Multiserver Environment</span></span>](create-a-multiserver-environment.md)  
  
  
