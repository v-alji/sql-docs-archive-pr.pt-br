---
title: Concedendo permissões de banco de dados do processo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 69ba952e-09ae-49a9-9297-00e32e8e89a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6ada30e3fb509bd1ffd210485ce0e34b7bf86fb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568846"
---
# <a name="granting-process-database-permissions"></a><span data-ttu-id="864da-102">Concedendo permissões ao banco de dados do processo</span><span class="sxs-lookup"><span data-stu-id="864da-102">Granting Process Database Permissions</span></span>
  <span data-ttu-id="864da-103">Depois da instalação de uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], todos os membros da função do administrador de servidor do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] nessa instância têm permissões em todo o servidor para executar qualquer tarefa na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="864da-103">After you install an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], all members of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server administrator role in that instance have server-wide permissions to perform any task within the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="864da-104">Por padrão, nenhum outro usuário tem qualquer permissão para administrar ou exibir objetos na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="864da-104">By default, no other users have any permission to administer or view any objects in the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>

 <span data-ttu-id="864da-105">Um membro da função de administrador de servidor pode conceder acesso administrativo aos usuários no servidor tornando-os membros da função.</span><span class="sxs-lookup"><span data-stu-id="864da-105">A member of the server administrator role can grant users administrative access on a server-wide basis by making them members of the role.</span></span> <span data-ttu-id="864da-106">Um membro da função de administrador de servidor também pode conceder acesso mais limitado aos usuários. Para isso, ele deve conceder permissões de acesso ou administrativas totais ou limitadas no nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="864da-106">A member of the server administrator role can also grant users access on a more limited basis by granting them limited or complete administrative or access permissions at the database level.</span></span> <span data-ttu-id="864da-107">Permissões administrativas limitadas incluem permissões para processar ou ler definição no nível de banco de dados, cubo ou dimensão.</span><span class="sxs-lookup"><span data-stu-id="864da-107">Limited administrative permissions include process or read definition permissions at the database, cube, or dimension level.</span></span>

 <span data-ttu-id="864da-108">Nas tarefas deste tópico, você definirá uma função de segurança Processar objetos de banco de dados que concede aos membros dessa função permissão para processar todos os objetos de banco de dados, mas não para exibir dados contidos nesse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="864da-108">In the tasks in this topic, you will define a Process Database Objects security role that grants members of the role permission to process all database objects, but no permission to view data within the database.</span></span>

## <a name="defining-a-process-database-objects-security-role"></a><span data-ttu-id="864da-109">Definindo uma função de segurança Processar objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="864da-109">Defining a Process Database Objects Security Role</span></span>

1.  <span data-ttu-id="864da-110">No Gerenciador de Soluções, clique com o botão direito do mouse em **Funções** e clique em **Nova Função** para abrir o Designer de Função.</span><span class="sxs-lookup"><span data-stu-id="864da-110">In Solution Explorer, right-click **Roles** and then click **New Role** to open the Role Designer.</span></span>

2.  <span data-ttu-id="864da-111">Clique na caixa de seleção **Processar banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="864da-111">Click the **Process database** check box.</span></span>

3.  <span data-ttu-id="864da-112">No janela Propriedades, altere a propriedade **Name** para essa nova função para `Process Database Objects Role` .</span><span class="sxs-lookup"><span data-stu-id="864da-112">In the Properties window, change the **Name** property for this new role to `Process Database Objects Role`.</span></span>

     <span data-ttu-id="864da-113">![Designer de Função](../../2014/tutorials/media/l10-security-1.png "Designer de Função")</span><span class="sxs-lookup"><span data-stu-id="864da-113">![Role Designer](../../2014/tutorials/media/l10-security-1.png "Role Designer")</span></span>

4.  <span data-ttu-id="864da-114">Alterne para a guia **Associação** do Designer de Função e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="864da-114">Switch to the **Membership** tab of Role Designer and click **Add**.</span></span>

5.  <span data-ttu-id="864da-115">Insira as contas dos usuários ou grupos do domínio do Windows que serão membros dessa função.</span><span class="sxs-lookup"><span data-stu-id="864da-115">Enter the accounts of the Windows domain users or groups who will be members of this role.</span></span> <span data-ttu-id="864da-116">Clique em **Verificar Nomes** para verificar as informações das contas e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="864da-116">Click **Check Names** to verify the account information, and then click **OK**.</span></span>

6.  <span data-ttu-id="864da-117">Alterne para a guia **Cubos** do Designer de Função.</span><span class="sxs-lookup"><span data-stu-id="864da-117">Switch to the **Cubes** tab of Role Designer.</span></span>

     <span data-ttu-id="864da-118">Observe que os membros dessa função têm permissão para processar este banco de dados, mas não para acessar os dados no cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e também não têm acesso ao cubo/detalhamento local, conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="864da-118">Notice that members of this role have permissions to process this database, but have no permission to access the data in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube and have no local cube/drillthrough access, as shown in the following image.</span></span>

     <span data-ttu-id="864da-119">![Guia Cubos do Designer de Função](../../2014/tutorials/media/l10-security-2.png "Guia Cubos do Designer de Função")</span><span class="sxs-lookup"><span data-stu-id="864da-119">![Cubes tab of Role Designer](../../2014/tutorials/media/l10-security-2.png "Cubes tab of Role Designer")</span></span>

7.  <span data-ttu-id="864da-120">Alterne para a guia **Dimensões** do Designer de Função.</span><span class="sxs-lookup"><span data-stu-id="864da-120">Switch to the **Dimensions** tab of Role Designer.</span></span>

     <span data-ttu-id="864da-121">Observe que os membros dessa função têm permissões para processar todos os objetos da dimensão neste banco de dados e, por padrão, têm permissão de leitura para acessar cada objeto de dimensão no banco de dados do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="864da-121">Notice that members of this role have permissions to process all dimension objects in this database, and, by default, have read permissions to access each dimension object in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial database.</span></span>

8.  <span data-ttu-id="864da-122">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="864da-122">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

     <span data-ttu-id="864da-123">Você definiu e implantou com êxito a função de segurança Processar objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="864da-123">You have now successfully defined and deployed the Process Database Objects security role.</span></span> <span data-ttu-id="864da-124">Depois que o cubo for implantado no ambiente de produção, os administradores desse cubo poderão adicionar usuários a essa função, conforme necessário para delegar responsabilidades de processamento a determinados usuários.</span><span class="sxs-lookup"><span data-stu-id="864da-124">After a cube is deployed to the production environment, the administrators of the deployed cube can add users to this role as required to delegate processing responsibilities to specific users.</span></span>

> [!NOTE]
>  <span data-ttu-id="864da-125">Um projeto completo para a Lição 10 pode ser obtido por meio do download e instalação dos exemplos.</span><span class="sxs-lookup"><span data-stu-id="864da-125">A completed project for Lesson 10 is available by downloading and installing the samples.</span></span> <span data-ttu-id="864da-126">Para obter mais informações, consulte [instalar dados de exemplo e projetos para o tutorial de modelagem multidimensional Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="864da-126">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="864da-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="864da-127">See Also</span></span>
 [<span data-ttu-id="864da-128">Funções e permissões &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="864da-128">Roles and Permissions &#40;Analysis Services&#41;</span></span>](multidimensional-models/roles-and-permissions-analysis-services.md)


