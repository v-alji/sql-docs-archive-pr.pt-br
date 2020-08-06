---
title: rsAccessedDenied – erro do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsAccessDenied error
ms.assetid: 2f76b1bf-96a2-4755-b76b-84e933220efc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 194006c2ef6f22b9bc27e9e8cbe1eebd027ed6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574462"
---
# <a name="rsaccesseddenied---reporting-services-error"></a><span data-ttu-id="5311a-102">rsAccessedDenied - Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5311a-102">rsAccessedDenied - Reporting Services Error</span></span>
  <span data-ttu-id="5311a-103">O erro do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]**rsAccessedDenied** ocorre quando um usuário não tem permissão para realizar uma ação.</span><span class="sxs-lookup"><span data-stu-id="5311a-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] error **rsAccessedDenied** occurs when a user does not have permission to perform an action.</span></span> <span data-ttu-id="5311a-104">Por exemplo, o usuário não tem uma atribuição de função que o permita abrir um relatório ou ele não abriu seu navegador com as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="5311a-104">For, example, they do not have a role assignment that allows them to open a report or they did not open their browser with the required permissions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="5311a-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; Modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="5311a-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; SharePoint mode</span></span>|  
  
-   <span data-ttu-id="5311a-106">Se o erro tiver ocorrido ao acessar o servidor de relatório diretamente através de uma URL, a exceção será mapeada para um erro HTTP 401.</span><span class="sxs-lookup"><span data-stu-id="5311a-106">If the error occurred while accessing the report server directly through a URL, the exception is mapped to an HTTP 401 error.</span></span>  
  
-   <span data-ttu-id="5311a-107">Se ele tiver ocorrido ao usar o Gerenciador de Relatórios ou outra ferramenta, o erro será exibido em uma página de erro.</span><span class="sxs-lookup"><span data-stu-id="5311a-107">If the error occurred while using Report Manager or another tool, the error appears in an error page.</span></span>  
  
-   <span data-ttu-id="5311a-108">Se ele tiver ocorrido durante uma operação, uma assinatura ou uma entrega agendada, o erro será exibido somente no arquivo de log do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5311a-108">If the error occurred during a scheduled operation, subscription, or delivery, the error will appear in the report server log file only.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5311a-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5311a-109">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5311a-110">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="5311a-110">**Product Name**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="5311a-111">**ID do evento**</span><span class="sxs-lookup"><span data-stu-id="5311a-111">**Event ID**</span></span>|<span data-ttu-id="5311a-112">rsAccessedDenied</span><span class="sxs-lookup"><span data-stu-id="5311a-112">rsAccessedDenied</span></span>|  
|<span data-ttu-id="5311a-113">**Origem do evento**</span><span class="sxs-lookup"><span data-stu-id="5311a-113">**Event Source**</span></span>|<span data-ttu-id="5311a-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="5311a-114">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="5311a-115">**Componente**</span><span class="sxs-lookup"><span data-stu-id="5311a-115">**Component**</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="5311a-116">**Texto da mensagem**</span><span class="sxs-lookup"><span data-stu-id="5311a-116">**Message Text**</span></span>|<span data-ttu-id="5311a-117">As permissões concedidas ao usuário 'meudomínio\minhaConta' são insuficientes para a execução dessa operação.</span><span class="sxs-lookup"><span data-stu-id="5311a-117">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="5311a-118">(rsAccessDenied) (ReportingServicesLibrary)</span><span class="sxs-lookup"><span data-stu-id="5311a-118">(rsAccessDenied) (ReportingServicesLibrary)</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="5311a-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5311a-119">User Action</span></span>  
 <span data-ttu-id="5311a-120">A permissão para acessar as operações e o conteúdo do servidor de relatório é concedida através de atribuições de função.</span><span class="sxs-lookup"><span data-stu-id="5311a-120">Permission to access report server content and operations are granted through role assignments.</span></span> <span data-ttu-id="5311a-121">Em uma nova instalação, somente administradores locais têm acesso a um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5311a-121">On a new installation, only local administrators have access to a report server.</span></span> <span data-ttu-id="5311a-122">Para conceder acesso a outros usuários, é necessário que um administrador local crie uma atribuição de função que especifique um usuário de domínio ou uma conta de grupo, uma ou mais funções que definem as tarefas que o usuário pode executar e um escopo (geralmente, a pasta Base ou o nó raiz da hierarquia de pastas do servidor de relatório).</span><span class="sxs-lookup"><span data-stu-id="5311a-122">To grant access to other users, a local administrator must create a role assignment that specifies a domain user or group account, one or more roles that define the tasks the user can perform, and a scope (usually the Home folder or root node of the report server folder hierarchy).</span></span> <span data-ttu-id="5311a-123">É possível usar o Gerenciador de Relatórios para criar as atribuições de função.</span><span class="sxs-lookup"><span data-stu-id="5311a-123">You can use Report Manager to create the role assignments.</span></span> <span data-ttu-id="5311a-124">Para obter mais informações, consulte "Atribuições de função" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5311a-124">For more information, search for "Role Assignments" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="5311a-125">Esse erro também é causado pela administração local do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5311a-125">This error is also caused by local administration of the report server.</span></span> <span data-ttu-id="5311a-126">Para obter mais informações, consulte [Configurar um servidor de relatório no modo nativo para a Administração Local &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5311a-126">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](../report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5311a-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5311a-127">See Also</span></span>  
 <span data-ttu-id="5311a-128">[Atribuições de função](../security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="5311a-128">[Role Assignments](../security/role-assignments.md) </span></span>  
 <span data-ttu-id="5311a-129">[Concedendo permissões em um servidor de relatório no modo nativo](../security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="5311a-129">[Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="5311a-130">Funções e permissões &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5311a-130">Roles and Permissions &#40;Reporting Services&#41;</span></span>](../security/roles-and-permissions-reporting-services.md)  
  
  
