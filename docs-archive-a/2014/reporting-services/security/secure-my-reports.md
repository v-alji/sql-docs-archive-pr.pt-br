---
title: Proteger Meus Relatórios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- denying My Reports folder access
- private folders [Reporting Services]
- user workspace [Reporting Services]
- security [Reporting Services], My Reports folder
- My Reports folder [Reporting Services]
ms.assetid: 3b23a382-13b8-4196-9a93-7fe62d03a63c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b0a832133852e05c54a80b73fad8a91426840467
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679657"
---
# <a name="secure-my-reports"></a><span data-ttu-id="f32d0-102">Proteger Meus Relatórios</span><span class="sxs-lookup"><span data-stu-id="f32d0-102">Secure My Reports</span></span>
  <span data-ttu-id="f32d0-103">O recurso Meus Relatórios fornece um workspace gerenciado pelo usuário para trabalhar com relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-103">The My Reports feature provides a user-managed workspace for working with reports.</span></span> <span data-ttu-id="f32d0-104">Para funcionar conforme pretendido, a pasta Meus Relatórios requer permissões menos restritivas do que as outras pastas que estão disponíveis para uso geral.</span><span class="sxs-lookup"><span data-stu-id="f32d0-104">In order to serve its intended purpose, the My Reports folder requires less restrictive permissions than other folders that are available for general use.</span></span> <span data-ttu-id="f32d0-105">Os usuários que têm permissões apenas para exibir e executar relatórios em outras pastas podem precisar de um conjunto maior de permissões para gerenciar suas pastas Meus Relatórios e seu próprio conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f32d0-105">Users who have permissions to only view and run reports in other folders might require an expanded set of permissions to manage their My Reports folders and content that they own.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="f32d0-106">fornece uma atribuição de função especializada e uma definição de função para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="f32d0-106">provides a specialized role assignment and role definition for this purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f32d0-107">O recurso Meus Relatórios só está disponível no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-107">My Reports is available only in Report Manager.</span></span> <span data-ttu-id="f32d0-108">Não está disponível no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f32d0-108">It is not available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="role-assignment-for-my-reports"></a><span data-ttu-id="f32d0-109">Atribuição de função para Meus Relatórios</span><span class="sxs-lookup"><span data-stu-id="f32d0-109">Role Assignment for My Reports</span></span>  
 <span data-ttu-id="f32d0-110">A atribuição de função para Meus Relatórios tem elementos predefinidos e é criada automaticamente para cada usuário que ativa uma pasta Meus Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-110">The role assignment for My Reports has preset elements and is automatically created for each user who activates a My Reports folder.</span></span> <span data-ttu-id="f32d0-111">A atribuição automática de segurança feita pelo servidor de relatório é especialmente útil para organizações que usam muito o recurso Meus Relatórios porque os administradores não precisam permitir o acesso para cada usuário dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f32d0-111">Having the report server automatically assign security is especially useful for organizations that use My Reports widely because administrators do not have to enable access for each My Reports user.</span></span>  
  
 <span data-ttu-id="f32d0-112">Uma atribuição de função de **Meus Relatórios** consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="f32d0-112">A **My Reports** role assignment consists of the following elements:</span></span>  
  
-   <span data-ttu-id="f32d0-113">A pasta meus relatórios do usuário, localizada na pasta pastas de usuários \\ *\<username>* \Meus relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-113">The user's My Reports folder, which is located in Users Folders\\*\<username>* \My Reports folder.</span></span>  
  
-   <span data-ttu-id="f32d0-114">A conta de usuário, que é determinada quando a pasta Meus Relatórios é ativada.</span><span class="sxs-lookup"><span data-stu-id="f32d0-114">The user account, which is determined when the My Reports folder is activated.</span></span> <span data-ttu-id="f32d0-115">Uma pasta é ativada quando o usuário clica em uma pasta Meus Relatórios no Gerenciador de Relatórios ou publica um relatório em uma pasta Meus Relatórios a partir do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-115">A folder is activated when a user clicks a My Reports folder in Report Manager or when publishing a report to a My Reports folder from Report Designer.</span></span> <span data-ttu-id="f32d0-116">Essa pasta também é ativada quando o usuário solicita propriedades no link Meus Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-116">This folder is also activated when a user requests properties on the My Reports link.</span></span>  
  
-   <span data-ttu-id="f32d0-117">A definição de função predefinida para Meus Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-117">The predefined role definition for My Reports.</span></span>  
  
## <a name="role-definition-for-my-reports"></a><span data-ttu-id="f32d0-118">Definição de função para Meus Relatórios</span><span class="sxs-lookup"><span data-stu-id="f32d0-118">Role Definition for My Reports</span></span>  
 <span data-ttu-id="f32d0-119">A definição de função de **Meus Relatórios** inclui tarefas que dão suporte ao gerenciamento de conteúdo de uma pasta Meus Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-119">The **My Reports** role definition includes tasks that support content management of a My Reports folder.</span></span> <span data-ttu-id="f32d0-120">A função **Meus Relatórios** tem uma única finalidade.</span><span class="sxs-lookup"><span data-stu-id="f32d0-120">The **My Reports** role is intended to be a single-purpose role.</span></span> <span data-ttu-id="f32d0-121">Embora seja possível definir qualquer política de segurança no nível do item para essa pasta, evite fazer isso para minimizar a chance de modificá-la para satisfazer requisitos de outra pasta.</span><span class="sxs-lookup"><span data-stu-id="f32d0-121">Although you can choose it for any item-level security policy, you should avoid doing so to minimize the chance that you will modify it to accommodate other folder requirements.</span></span> <span data-ttu-id="f32d0-122">A reserva da função **Meus Relatórios** para o recurso Meus Relatórios pode ajudar você a manter uma experiência consistente para os usuários.</span><span class="sxs-lookup"><span data-stu-id="f32d0-122">Reserving the **My Reports** role for the My Reports feature can help you maintain a consistent experience for users.</span></span>  
  
 <span data-ttu-id="f32d0-123">Por padrão, só administradores de servidor de relatório modificam a função **Meus Relatórios** .</span><span class="sxs-lookup"><span data-stu-id="f32d0-123">By default, only report server administrators modify the **My Reports** role.</span></span> <span data-ttu-id="f32d0-124">Você pode personalizar a função **Meus Relatórios** alterando as tarefas que ela contém.</span><span class="sxs-lookup"><span data-stu-id="f32d0-124">You can customize the **My Reports** role by changing the tasks it contains.</span></span> <span data-ttu-id="f32d0-125">Você também pode substituir uma função diferente.</span><span class="sxs-lookup"><span data-stu-id="f32d0-125">You can also substitute a different role.</span></span>  
  
## <a name="denying-access-to-my-reports"></a><span data-ttu-id="f32d0-126">Negando o acesso a Meus Relatórios</span><span class="sxs-lookup"><span data-stu-id="f32d0-126">Denying Access to My Reports</span></span>  
 <span data-ttu-id="f32d0-127">Para impedir que os usuários acessem Meus Relatórios:</span><span class="sxs-lookup"><span data-stu-id="f32d0-127">You can prevent users from accessing My Reports by:</span></span>  
  
-   <span data-ttu-id="f32d0-128">Desabilite Meus Relatórios na página Configurações de Site.</span><span class="sxs-lookup"><span data-stu-id="f32d0-128">Disabling My Reports on the Site Settings page.</span></span> <span data-ttu-id="f32d0-129">Para obter mais informações, consulte [Habilitar e desabilitar Meus Relatórios](../report-server/enable-and-disable-my-reports.md).</span><span class="sxs-lookup"><span data-stu-id="f32d0-129">For more information, see [Enable and Disable My Reports](../report-server/enable-and-disable-my-reports.md).</span></span>  
  
-   <span data-ttu-id="f32d0-130">Remova todas as tarefas da função **Meus Relatórios** .</span><span class="sxs-lookup"><span data-stu-id="f32d0-130">Removing all tasks from the **My Reports** role.</span></span>  
  
 <span data-ttu-id="f32d0-131">Ao desabilitar Meus Relatórios, o link para uma pasta Meus Relatórios é removido do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f32d0-131">When you disable My Reports, the link to a My Reports folder is removed from Report Manager.</span></span> <span data-ttu-id="f32d0-132">A estrutura de pasta subjacente que dá suporte a Meus Relatórios (quer dizer, a pasta Pastas dos Usuários e as subpastas) ainda estará disponível e poderá ser acessada se o usuário souber o caminho da pasta.</span><span class="sxs-lookup"><span data-stu-id="f32d0-132">The underlying folder structure that supports My Reports (that is, the Users Folders folder and subfolders) is still available and can be accessed if a user knows the folder path.</span></span> <span data-ttu-id="f32d0-133">A remoção de tarefas da função **Meus Relatórios** assegura a negação do acesso.</span><span class="sxs-lookup"><span data-stu-id="f32d0-133">Removing tasks from **My Reports** role ensures that access is prevented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f32d0-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f32d0-134">See Also</span></span>  
 <span data-ttu-id="f32d0-135">[Proteger relatórios e recursos](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="f32d0-135">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="f32d0-136">[Proteger pastas](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="f32d0-136">[Secure Folders](secure-folders.md) </span></span>  
 [<span data-ttu-id="f32d0-137">Conceder permissões em um servidor de relatório no Modo Nativo</span><span class="sxs-lookup"><span data-stu-id="f32d0-137">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
