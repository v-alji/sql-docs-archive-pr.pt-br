---
title: Proteger pastas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- high-security folders [Reporting Services]
- low-security folders
- folders [Reporting Services], security
- security [Reporting Services], folders
ms.assetid: 0fd91f77-0143-476b-9af0-87293be78e44
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 483b3108713032b3aaf566208f39f6c2f705da1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571265"
---
# <a name="secure-folders"></a><span data-ttu-id="9f696-102">Proteger pastas</span><span class="sxs-lookup"><span data-stu-id="9f696-102">Secure Folders</span></span>
  <span data-ttu-id="9f696-103">A segurança de pasta é a base para proteger todo o conteúdo em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="9f696-103">Folder security is the foundation for securing all content in a report server.</span></span> <span data-ttu-id="9f696-104">Como a segurança é herdada em toda a estrutura de pastas, é possível designar seções grandes ou pequenas da hierarquia de pasta para permitir determinados tipos de acesso.</span><span class="sxs-lookup"><span data-stu-id="9f696-104">Because security is inherited throughout the folder structure, you can designate large or small sections of the folder hierarchy to allow for certain kinds of access.</span></span>  
  
 <span data-ttu-id="9f696-105">As pastas de alta segurança podem ser usadas para armazenar relatórios confidenciais ou como áreas de preparação; por exemplo, você pode ter uma pasta usada para testar os relatórios antes de movê-los para um local final.</span><span class="sxs-lookup"><span data-stu-id="9f696-105">High-security folders can be used to store confidential reports or as staging areas; for example, you can have a folder that you use to test reports before moving them to a final location.</span></span> <span data-ttu-id="9f696-106">Para controlar o acesso a essa área, você pode definir uma atribuição de função que permite somente aos autores de relatório adicionar e excluir itens e uma segunda atribuição de função que permite aos testadores executar relatórios, mas não adicionar ou remover itens.</span><span class="sxs-lookup"><span data-stu-id="9f696-106">To control access to this area, you can define one role assignment that allows only report authors to add and delete items, and a second role assignment that allows testers to run reports but not to add or remove items.</span></span> <span data-ttu-id="9f696-107">Como as atribuições de função são definidas explicitamente para testadores e autores de relatório, nenhum outro usuário (exceto os administradores do sistema local) pode acessar a pasta.</span><span class="sxs-lookup"><span data-stu-id="9f696-107">Because the role assignments are defined explicitly for testers and report authors, no other users (except for local system administrators) can access the folder.</span></span>  
  
 <span data-ttu-id="9f696-108">As pastas de baixa segurança podem ser usadas para armazenar relatórios que você deseja acessar com facilidade.</span><span class="sxs-lookup"><span data-stu-id="9f696-108">Low-security folders can be used to store reports that you want to be easily accessible.</span></span>  
  
 <span data-ttu-id="9f696-109">A segurança de pasta é a base da segurança no nível do item, começando com o nó raiz da hierarquia de pastas do servidor de relatório, a pasta Base.</span><span class="sxs-lookup"><span data-stu-id="9f696-109">Folder security forms the basis of item-level security, starting with the root node of the report server folder hierarchy, the Home folder.</span></span> <span data-ttu-id="9f696-110">Como segurança é herdada, é aconselhável definir uma política de segurança bastante restritiva na pasta Base.</span><span class="sxs-lookup"><span data-stu-id="9f696-110">Because security is inherited, it is advisable to set a fairly restrictive security policy on the Home folder.</span></span> <span data-ttu-id="9f696-111">Usar a função **Navegador** nas atribuições de função da pasta Base é exatamente o mesmo que fornecer o acesso somente exibição.</span><span class="sxs-lookup"><span data-stu-id="9f696-111">Using the **Browser** role in Home folder role assignments does exactly that by providing view-only access.</span></span>  
  
## <a name="tasks-and-folder-access"></a><span data-ttu-id="9f696-112">Tarefas e acesso à pasta</span><span class="sxs-lookup"><span data-stu-id="9f696-112">Tasks and Folder Access</span></span>  
 <span data-ttu-id="9f696-113">Ao criar atribuições de função para pastas, considere as tarefas listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9f696-113">When creating role assignments for folders, consider the tasks listed in the following table.</span></span>  
  
|<span data-ttu-id="9f696-114">Selecione esta tarefa</span><span class="sxs-lookup"><span data-stu-id="9f696-114">Select this task</span></span>|<span data-ttu-id="9f696-115">Para dar permissão para</span><span class="sxs-lookup"><span data-stu-id="9f696-115">To give permission to</span></span>|  
|----------------------|---------------------------|  
|<span data-ttu-id="9f696-116">Exibir pastas</span><span class="sxs-lookup"><span data-stu-id="9f696-116">View folders</span></span>|<span data-ttu-id="9f696-117">Exibir a hierarquia de pastas e as propriedades somente leitura que indicam quando a pasta foi criada e modificada.</span><span class="sxs-lookup"><span data-stu-id="9f696-117">View the folder hierarchy and read-only properties that indicate when the folder was created and modified.</span></span><br /><br /> <span data-ttu-id="9f696-118">Os usuários não podem exibir itens na pasta, a não ser que obtenham funções que também incluem as seguintes tarefas: “Exibir relatórios”, “Exibir modelos”, “Exibir recursos” e “Exibir fontes de dados”.</span><span class="sxs-lookup"><span data-stu-id="9f696-118">Users cannot view items in the folder unless they are assigned to roles that also include the following tasks: "View reports," "View models", "View resources," and "View data sources."</span></span>|  
|<span data-ttu-id="9f696-119">Gerenciar pastas</span><span class="sxs-lookup"><span data-stu-id="9f696-119">Manage folders</span></span>|<span data-ttu-id="9f696-120">Exibir propriedades de pasta, alterar o nome ou a descrição ou mover a pasta para outro local.</span><span class="sxs-lookup"><span data-stu-id="9f696-120">View folder properties, change the name or description, or move the folder to another location.</span></span> <span data-ttu-id="9f696-121">Essa tarefa permite que os usuários criem pastas.</span><span class="sxs-lookup"><span data-stu-id="9f696-121">This task allows users to create folders.</span></span>|  
|<span data-ttu-id="9f696-122">Gerenciar relatórios</span><span class="sxs-lookup"><span data-stu-id="9f696-122">Manage reports</span></span>|<span data-ttu-id="9f696-123">Adicionar relatórios do sistema de arquivos a uma pasta e publicar relatórios do Designer de Relatórios no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="9f696-123">Add reports from the file system to a folder and publish reports from Report Designer to the report server.</span></span>|  
|<span data-ttu-id="9f696-124">Gerenciar as fontes de dados</span><span class="sxs-lookup"><span data-stu-id="9f696-124">Manage data sources</span></span>|<span data-ttu-id="9f696-125">Adicionar novos itens de fontes de dados compartilhadas a uma pasta e alterar as fontes de dados compartilhadas existentes.</span><span class="sxs-lookup"><span data-stu-id="9f696-125">Add new shared data source items to a folder and change existing shared data sources.</span></span>|  
|<span data-ttu-id="9f696-126">Definir segurança em itens</span><span class="sxs-lookup"><span data-stu-id="9f696-126">Set security on items</span></span>|<span data-ttu-id="9f696-127">Criar e modificar atribuições de função que controlam o acesso à pasta.</span><span class="sxs-lookup"><span data-stu-id="9f696-127">Create and modify role assignments that control access to the folder.</span></span> <span data-ttu-id="9f696-128">Essa tarefa deve ser usada com “Exibir pastas” ou “Gerenciar pastas”.</span><span class="sxs-lookup"><span data-stu-id="9f696-128">This task must be used with either "View folders" or "Manage folders."</span></span> <span data-ttu-id="9f696-129">Se não for, não terá nenhum efeito porque o usuário não poderá selecionar o item.</span><span class="sxs-lookup"><span data-stu-id="9f696-129">If it is not, it will have no effect because the user will not be able to select the item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f696-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f696-130">See Also</span></span>  
 <span data-ttu-id="9f696-131">[Proteger relatórios e recursos](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="9f696-131">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="9f696-132">[Proteger itens de fontes de dados compartilhadas](secure-shared-data-source-items.md) </span><span class="sxs-lookup"><span data-stu-id="9f696-132">[Secure Shared Data Source Items](secure-shared-data-source-items.md) </span></span>  
 [<span data-ttu-id="9f696-133">Conceder permissões em um servidor de relatório no Modo Nativo</span><span class="sxs-lookup"><span data-stu-id="9f696-133">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
