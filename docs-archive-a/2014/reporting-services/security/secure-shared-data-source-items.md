---
title: Proteger itens de fonte de dados compartilhada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
- security [Reporting Services], data sources
ms.assetid: 7299e498-0a1a-4821-a22a-5199bb773ce0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4177834a90e2852f4079e3b2bf5a1dd85b9cd51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574476"
---
# <a name="secure-shared-data-source-items"></a><span data-ttu-id="6da21-102">Proteger itens de fontes de dados compartilhadas</span><span class="sxs-lookup"><span data-stu-id="6da21-102">Secure Shared Data Source Items</span></span>
  <span data-ttu-id="6da21-103">Você pode definir a segurança em um item fonte de dados compartilhada para habilitar ou desabilitar o acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="6da21-103">You can set security on a shared data source item to enable or disable access to it.</span></span>  
  
 <span data-ttu-id="6da21-104">Um usuário que tem acesso mínimo a uma fonte de dados compartilhada (por exemplo, o acesso concedido através da função **Navegador** ) pode exibir a lista de relatórios que usam o item, contanto que o usuário também tenha autorização para exibir os relatórios propriamente ditos.</span><span class="sxs-lookup"><span data-stu-id="6da21-104">A user who has minimal access to a shared data source (for example, the access granted through the **Browser** role) can view the list of reports that use the item, provided the user is also authorized to view the reports themselves.</span></span>  
  
 <span data-ttu-id="6da21-105">Um usuário que tem acesso adicional (como o acesso concedido pela função **Gerenciador de Conteúdo** ) pode exibir e definir propriedades para a fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="6da21-105">A user who has additional access (such as that granted through the **Content Manager** role) can view and set properties for the shared data source.</span></span>  
  
 <span data-ttu-id="6da21-106">Para definir a segurança, crie uma atribuição de função que especifique a conta de usuário ou grupo que tem acesso à fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="6da21-106">To set security, you create a role assignment that specifies which user or group account has access to the shared data source.</span></span> <span data-ttu-id="6da21-107">Os usuários que têm acesso a um item fonte de dados compartilhada podem alterar seu nome, descrição, cadeia de conexão ou informações de credenciais.</span><span class="sxs-lookup"><span data-stu-id="6da21-107">Users who have access to a shared data source item can change its name, description, connection string, or credential information.</span></span>  
  
## <a name="tasks-and-access-to-items"></a><span data-ttu-id="6da21-108">Tarefas e acesso a itens</span><span class="sxs-lookup"><span data-stu-id="6da21-108">Tasks and Access to Items</span></span>  
 <span data-ttu-id="6da21-109">Ao criar atribuições de função, use uma função que tem estas tarefas para atribuir permissões apropriadas aos usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="6da21-109">When creating role assignments, use a role that has these tasks to assign appropriate permissions to users and groups.</span></span>  
  
|<span data-ttu-id="6da21-110">Selecione esta tarefa</span><span class="sxs-lookup"><span data-stu-id="6da21-110">Select this task</span></span>|<span data-ttu-id="6da21-111">Para conceder permissão aos usuários para</span><span class="sxs-lookup"><span data-stu-id="6da21-111">To give users permission to</span></span>|  
|----------------------|---------------------------------|  
|<span data-ttu-id="6da21-112">Exibir fontes de dados</span><span class="sxs-lookup"><span data-stu-id="6da21-112">View data sources</span></span>|<span data-ttu-id="6da21-113">Exibir o item fonte de dados compartilhada na hierarquia de pastas.</span><span class="sxs-lookup"><span data-stu-id="6da21-113">View the shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="6da21-114">Sem essa tarefa, o item não pode ser visto pelos usuários e eles talvez não saibam que a fonte de dados está disponível.</span><span class="sxs-lookup"><span data-stu-id="6da21-114">Without this task, the item is not visible to users and they may not be aware that the data source is available.</span></span>|  
|<span data-ttu-id="6da21-115">Gerenciar as fontes de dados</span><span class="sxs-lookup"><span data-stu-id="6da21-115">Manage data sources</span></span>|<span data-ttu-id="6da21-116">Exibir as propriedades que especificam o nome, a descrição e as informações de conexão.</span><span class="sxs-lookup"><span data-stu-id="6da21-116">View properties that specify the name, description, and connection information.</span></span> <span data-ttu-id="6da21-117">Essa tarefa também é usada para exibir um item fonte de dados compartilhada na hierarquia de pastas.</span><span class="sxs-lookup"><span data-stu-id="6da21-117">This task is also used to display a shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="6da21-118">Se você escolher essa tarefa, poderá omitir a tarefa “Exibir fontes de dados”.</span><span class="sxs-lookup"><span data-stu-id="6da21-118">If you choose this task, you can omit the "View data sources" task.</span></span>|  
|<span data-ttu-id="6da21-119">Definir segurança em itens</span><span class="sxs-lookup"><span data-stu-id="6da21-119">Set security on items</span></span>|<span data-ttu-id="6da21-120">Criar e modificar atribuições de função que controlam o acesso à fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="6da21-120">Create and modify role assignments that control access to the shared data source.</span></span> <span data-ttu-id="6da21-121">Essa tarefa deve ser usada com as tarefas “Exibir fonte de dados” ou “Gerenciar fontes de dados”.</span><span class="sxs-lookup"><span data-stu-id="6da21-121">This task must be used with either "View data source" or "Manage data sources" tasks.</span></span> <span data-ttu-id="6da21-122">Se não for, não terá nenhum efeito porque o usuário não pode selecionar o item.</span><span class="sxs-lookup"><span data-stu-id="6da21-122">If it is not, it has no effect because the user cannot select the item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6da21-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6da21-123">See Also</span></span>  
 <span data-ttu-id="6da21-124">[Gerenciar fontes de dados de relatório](../report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="6da21-124">[Manage Report Data Sources](../report-data/manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="6da21-125">[Proteger pastas](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="6da21-125">[Secure Folders](secure-folders.md) </span></span>  
 <span data-ttu-id="6da21-126">[Proteger relatórios e recursos](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="6da21-126">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="6da21-127">[Concedendo permissões em um servidor de relatório no modo nativo](granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="6da21-127">[Granting Permissions on a Native Mode Report Server](granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="6da21-128">Armazenar credenciais em uma fonte de dados do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6da21-128">Store Credentials in a Reporting Services Data Source</span></span>](../report-data/store-credentials-in-a-reporting-services-data-source.md)  
  
  
