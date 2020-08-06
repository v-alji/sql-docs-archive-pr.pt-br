---
title: Funções e permissões (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], about security
- security [Analysis Services - multidimensional data], about security
ms.assetid: bb885447-868b-4686-853c-8241f63d4370
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6595d931b2c2760e5fd3013ff6bec88f85106d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686417"
---
# <a name="roles-and-permissions-analysis-services"></a><span data-ttu-id="5c75a-102">Funções e permissões (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="5c75a-102">Roles and Permissions (Analysis Services)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="5c75a-103">fornece um modelo de autorização com base em funções que concede acesso a operações, objetos e dados.</span><span class="sxs-lookup"><span data-stu-id="5c75a-103">provides a role-based authorization model that grants access to operations, objects, and data.</span></span> <span data-ttu-id="5c75a-104">Todos os usuários que acessam uma instância ou banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] devem fazer isso dentro do contexto de uma função.</span><span class="sxs-lookup"><span data-stu-id="5c75a-104">All users who access an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance or database must do so within the context of a role.</span></span>  
  
 <span data-ttu-id="5c75a-105">Como um administrador de sistema do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , você é responsável pela concessão de associações à **função de administrador do servidor** que transmite acesso irrestrito às operações no servidor.</span><span class="sxs-lookup"><span data-stu-id="5c75a-105">As an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] system administrator, you are in charge of granting membership to the **server administrator role** that conveys unrestricted access to operations on the server.</span></span> <span data-ttu-id="5c75a-106">Essa função tem permissões fixas e não pode ser personalizada.</span><span class="sxs-lookup"><span data-stu-id="5c75a-106">This role has fixed permissions and cannot be customized.</span></span> <span data-ttu-id="5c75a-107">Por padrão, os membros do grupo Administradores local são automaticamente administradores do sistema do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="5c75a-107">By default, members of the local Administrators group are automatically Analysis Services system administrators.</span></span>  
  
 <span data-ttu-id="5c75a-108">Aos usuários não administrativos que consultam ou processam dados são concedidos acesso por meio das **funções de banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="5c75a-108">Non-administrative users who query or process data are granted access through **database roles**.</span></span> <span data-ttu-id="5c75a-109">Tanto os administradores de sistema quanto os administrador de banco de dados podem criar as funções que descrevem níveis de acesso diferentes em um determinado banco de dados e, depois, atribuir a associação a cada usuário que solicitar acesso.</span><span class="sxs-lookup"><span data-stu-id="5c75a-109">Both system administrators and database administrators can create the roles that describe different levels of access within a given database, and then assign membership to every user who requires access.</span></span> <span data-ttu-id="5c75a-110">Cada função tem um conjunto personalizado de permissões para acessar objetos e operações em um determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5c75a-110">Each role has a customized set of permissions for accessing objects and operations within a particular database.</span></span> <span data-ttu-id="5c75a-111">Você pode atribuir permissões nestes níveis: banco de dados, objetos interiores como cubos e dimensões (mas não perspectivas) e linhas.</span><span class="sxs-lookup"><span data-stu-id="5c75a-111">You can assign permissions at these levels: database, interior objects such as cubes and dimensions (but not perspectives), and rows.</span></span>  
  
 <span data-ttu-id="5c75a-112">É prática comum criar funções e atribuir associação como operações separadas.</span><span class="sxs-lookup"><span data-stu-id="5c75a-112">It is common practice to create roles and assign membership as separate operations.</span></span> <span data-ttu-id="5c75a-113">Frequentemente, o designer de modelos adiciona funções durante a fase de design.</span><span class="sxs-lookup"><span data-stu-id="5c75a-113">Often, the model designer adds roles during the design phase.</span></span> <span data-ttu-id="5c75a-114">Desse modo, todas as definições de função são refletidas nos arquivos de projeto que definem o modelo.</span><span class="sxs-lookup"><span data-stu-id="5c75a-114">This way, all role definitions are reflected in the project files that define the model.</span></span> <span data-ttu-id="5c75a-115">A associação de função geralmente é distribuída depois, à medida que o banco de dados vai para produção, em geral pelos administradores de banco de dados que criam scripts que podem ser desenvolvidos, testados e executados como uma operação independente.</span><span class="sxs-lookup"><span data-stu-id="5c75a-115">Role membership is typically rolled out later as the database moves into production, usually by database administrators who create scripts that can be developed, tested, and run as an independent operation.</span></span>  
  
 <span data-ttu-id="5c75a-116">Toda a autorização é predicada em uma identidade de usuário do Windows válida.</span><span class="sxs-lookup"><span data-stu-id="5c75a-116">All authorization is predicated on a valid Windows user identity.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="5c75a-117">usa a autenticação do Windows exclusivamente para autenticar identidades de usuário.</span><span class="sxs-lookup"><span data-stu-id="5c75a-117">uses Windows authentication exclusively to authenticate user identities.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="5c75a-118">não fornece nenhum método de autenticação proprietário. Consulte [metodologias de autenticação com suporte pelo Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="5c75a-118">provides no proprietary authentication method.See [Authentication methodologies supported by Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5c75a-119">As permissões são aditivas para cada usuário ou grupo do Windows, em todas as funções no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5c75a-119">Permissions are additive for each Windows user or group, across all roles in the database.</span></span> <span data-ttu-id="5c75a-120">Se uma função nega a um usuário ou grupo permissão para executar certas tarefas ou exibir certos dados, mas outra função concede essa permissão a esse usuário ou grupo, o usuário ou o grupo terá permissão para executar a tarefa ou exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="5c75a-120">If one role denies a user or group permission to perform certain tasks or view certain data, but another role grants this permission to that user or group, the user or group will have permission to perform the task or view the data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c75a-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5c75a-121">In this section</span></span>  
  
-   [<span data-ttu-id="5c75a-122">Autorizando o acesso a objetos e operações &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-122">Authorizing access to objects and operations &#40;Analysis Services&#41;</span></span>](authorizing-access-to-objects-and-operations-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-123">Conceder permissões de banco de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-123">Grant database permissions &#40;Analysis Services&#41;</span></span>](grant-database-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-124">Conceder permissões de cubo ou modelo &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-124">Grant cube or model permissions &#40;Analysis Services&#41;</span></span>](grant-cube-or-model-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-125">Conceder permissões de processo &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-125">Grant process permissions &#40;Analysis Services&#41;</span></span>](grant-process-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-126">Conceder permissões para ler definição em metadados de objetos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-126">Grant read definition permissions on object metadata &#40;Analysis Services&#41;</span></span>](grant-read-definition-permissions-on-object-metadata-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-127">Conceder permissões em um objeto de fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-127">Grant permissions on a data source object &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-data-source-object-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-128">Conceder permissões em estruturas e modelos de mineração de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-128">Grant permissions on data mining structures and models &#40;Analysis Services&#41;</span></span>](grant-permissions-on-data-mining-structures-and-models-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-129">Conceder permissões em uma dimensão &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-129">Grant permissions on a dimension &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-dimension-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-130">Conceder acesso personalizado a dados da dimensão &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-130">Grant custom access to dimension data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-dimension-data-analysis-services.md)  
  
-   [<span data-ttu-id="5c75a-131">Conceder acesso personalizado a dados de célula &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-131">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="5c75a-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c75a-132">See Also</span></span>  
 [<span data-ttu-id="5c75a-133">Criar e Gerenciar Funções &#40;SSAS Tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="5c75a-133">Create and Manage Roles &#40;SSAS Tabular&#41;</span></span>](../tabular-models/roles-ssas-tabular.md)  
  
  
