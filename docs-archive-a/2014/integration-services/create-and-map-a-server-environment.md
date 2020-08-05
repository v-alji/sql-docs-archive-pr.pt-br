---
title: Criar e mapear um ambiente de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isenvprop.variables.f1
- sql12.ssis.ssms.iscreateenv.f1
- sql12.ssis.ssms.isenvprop.permissions.f1
- sql12.ssis.ssms.isenvprop.general.f1
ms.assetid: b1cbb697-713f-48e4-b234-b23724d87451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9331b5078effb562931f45c48bd8ff975c1d1998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572615"
---
# <a name="create-and-map-a-server-environment"></a><span data-ttu-id="fd47c-102">Criar e mapear um ambiente de servidor</span><span class="sxs-lookup"><span data-stu-id="fd47c-102">Create and Map a Server Environment</span></span>
  <span data-ttu-id="fd47c-103">Você cria um ambiente de servidor para especificar valores de runtime para pacotes contidos em um projeto que você implantou no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd47c-103">You create a server environment to specify runtime values for packages contained in a project you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="fd47c-104">Você pode mapear as variáveis de ambiente para parâmetros, para um pacote específico, para pacotes de ponto de entrada ou para todos os pacotes em um projeto específico.</span><span class="sxs-lookup"><span data-stu-id="fd47c-104">You can then map the environment variables to parameters, for a specific package, for entry-point packages, or for all the packages in a given project.</span></span> <span data-ttu-id="fd47c-105">Um pacote de ponto de entrada é geralmente um pacote pai que executa um pacote filho.</span><span class="sxs-lookup"><span data-stu-id="fd47c-105">An entry-point package is typically a parent package that executes a child package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fd47c-106">Para uma execução específica, um pacote pode ser executado somente com os valores contidos em um único ambiente de servidor.</span><span class="sxs-lookup"><span data-stu-id="fd47c-106">For a given execution, a package can execute only with the values contained in a single server environment.</span></span>  
  
 <span data-ttu-id="fd47c-107">Você pode consultar as exibições para uma lista de ambientes de servidor, referências de ambiente e variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="fd47c-107">You can query views for a list of server environments, environment references, and environment variables.</span></span> <span data-ttu-id="fd47c-108">Você também pode chamar procedimentos armazenados para adicionar, excluir, alterar e modificar ambientes, referências de ambiente e variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="fd47c-108">You can also call stored to add, delete, and modify environments, environment references, and environment variables.</span></span> <span data-ttu-id="fd47c-109">Para obter mais informações, consulte a seção **Ambientes de servidor, variáveis de servidor e referências de ambiente de servidor** em [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="fd47c-109">For more information, see the **Server Environments, Server Variables and Server Environment References** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
### <a name="to-create-and-use-a-server-environment"></a><span data-ttu-id="fd47c-110">Para criar e usar um ambiente de servidor</span><span class="sxs-lookup"><span data-stu-id="fd47c-110">To create and use a server environment</span></span>  
  
1.  <span data-ttu-id="fd47c-111">No [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , expanda o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nó catálogos> **SSISDB** no Pesquisador de objetos e localize a pasta **ambientes** do projeto para o qual você deseja criar um ambiente.</span><span class="sxs-lookup"><span data-stu-id="fd47c-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], expand the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Catalogs> **SSISDB** node in Object Explorer, and locate the **Environments** folder of the project for which you want to create an environment.</span></span>  
  
2.  <span data-ttu-id="fd47c-112">Clique com o botão direito do mouse na pasta **Ambientes** e clique em **Criar Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="fd47c-112">Right-click the **Environments** folder, and then click **Create Environment**.</span></span>  
  
3.  <span data-ttu-id="fd47c-113">Digite um nome para o ambiente e uma descrição (opcional) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd47c-113">Type a name for the environment and optionally a description, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="fd47c-114">Clique com o botão direito do mouse no novo ambiente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="fd47c-114">Right-click the new environment and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="fd47c-115">Na página **Variáveis** , faça o seguinte para adicionar uma variável.</span><span class="sxs-lookup"><span data-stu-id="fd47c-115">On the **Variables** page, do the following to add a variable.</span></span>  
  
    1.  <span data-ttu-id="fd47c-116">Selecione o **Tipo** da variável.</span><span class="sxs-lookup"><span data-stu-id="fd47c-116">Select the **Type** for the variable.</span></span> <span data-ttu-id="fd47c-117">O nome da variável **não** precisa corresponder ao nome do parâmetro de projeto que você mapeia para a variável.</span><span class="sxs-lookup"><span data-stu-id="fd47c-117">The name of the variable **does not** need to match the name of the project parameter that you map to the variable.</span></span>  
  
    2.  <span data-ttu-id="fd47c-118">Digite uma **Descrição** opcional para a variável.</span><span class="sxs-lookup"><span data-stu-id="fd47c-118">Enter an optional **Description** for the variable.</span></span>  
  
    3.  <span data-ttu-id="fd47c-119">Digite o **Valor** para a variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="fd47c-119">Enter the **Value** for the environment variable.</span></span>  
  
         <span data-ttu-id="fd47c-120">Para obter informações sobre as regras para nomes de variável de ambiente, consulte a seção **Variável do ambiente** em [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="fd47c-120">For information about the rules for environment variable names, see the **Environment Variable** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
    4.  <span data-ttu-id="fd47c-121">Indica se a variável contém o valor confidencial, marcando ou desmarcando a caixa de seleção **Confidencial** .</span><span class="sxs-lookup"><span data-stu-id="fd47c-121">Indicate whether the variable contains sensitive value, by selecting or clearing the **Sensitive** checkbox.</span></span>  
  
         <span data-ttu-id="fd47c-122">Se você selecionar **Confidencial**, o valor da variável não será exibido no campo **Valor** .</span><span class="sxs-lookup"><span data-stu-id="fd47c-122">If you select **Sensitive**, the variable value does not display in the **Value** field.</span></span>  
  
         <span data-ttu-id="fd47c-123">Os valores confidenciais são criptografados no catálogo do SSISDB.</span><span class="sxs-lookup"><span data-stu-id="fd47c-123">Sensitive values are encrypted in the SSISDB catalog.</span></span> <span data-ttu-id="fd47c-124">Para obter mais informações sobre a criptografia SSL, consulte [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="fd47c-124">For more information about the encryption, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
6.  <span data-ttu-id="fd47c-125">Na página **Permissões** , conceda ou negue permissões para usuários e funções selecionados fazendo o seguinte.</span><span class="sxs-lookup"><span data-stu-id="fd47c-125">On the **Permissions** page, grant or deny permissions for selected users and roles by doing the following.</span></span>  
  
    1.  <span data-ttu-id="fd47c-126">Clique em **Procurar**e selecione um ou mais usuários e funções na caixa de diálogo **Procurar Todas as Entidades de Segurança** .</span><span class="sxs-lookup"><span data-stu-id="fd47c-126">Click **Browse**, and then select one or more users and roles in the **Browse All Principals** dialog box.</span></span>  
  
    2.  <span data-ttu-id="fd47c-127">Na área **Logons ou funções** , selecione o usuário ou função ao qual você quer conceder ou negar permissões.</span><span class="sxs-lookup"><span data-stu-id="fd47c-127">In the **Logins or roles** area, select the user or role that you want to grant or deny permissions for.</span></span>  
  
    3.  <span data-ttu-id="fd47c-128">Na área **Explícita** , clique em **Conceder** ou **Negar** ao lado de cada permissão.</span><span class="sxs-lookup"><span data-stu-id="fd47c-128">In the **Explicit** area, click **Grant** or **Deny** next to each permission.</span></span>  
  
7.  <span data-ttu-id="fd47c-129">Para criar o script do ambiente, clique em **Script**.</span><span class="sxs-lookup"><span data-stu-id="fd47c-129">To script the environment, click **Script**.</span></span> <span data-ttu-id="fd47c-130">Por padrão, o script é exibido em uma nova janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="fd47c-130">By default, the script displays in a new Query Editor window.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="fd47c-131">Você precisará clicar em **Script** depois de ter feito uma ou mais alterações às propriedades do ambiente, como adicionar uma variável e antes de clicar em **OK** na caixa de diálogo **Propriedades do Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="fd47c-131">You need to click **Script** after you've made one or changes to the environment properties, such as adding a variable, and before you click **OK** in the **Environment Properties** dialog box.</span></span> <span data-ttu-id="fd47c-132">Caso contrário, um script não será gerado.</span><span class="sxs-lookup"><span data-stu-id="fd47c-132">Otherwise, a script is not generated.</span></span>  
  
8.  <span data-ttu-id="fd47c-133">Clique em **OK** para salvar suas alterações nas propriedades de ambiente.</span><span class="sxs-lookup"><span data-stu-id="fd47c-133">Click **OK** to save your changes to the environment properties.</span></span>  
  
9. <span data-ttu-id="fd47c-134">No nó **SSISDB** no Pesquisador de Objetos, expanda a pasta **Projetos** , clique com o botão direito do mouse no projeto e, depois, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="fd47c-134">Under the **SSISDB** node in Object Explorer, expand the **Projects** folder, right-click the project, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="fd47c-135">Na página **Referências** , clique em **Adicionar** para adicionar um ambiente e, depois, em **OK** para salvar a referência para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="fd47c-135">On the **References** page, click **Add** to add an environment, and then click **OK** to save the reference to the environment.</span></span>  
  
11. <span data-ttu-id="fd47c-136">Clique novamente com o botão direito do mouse no projeto e clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="fd47c-136">Right-click the project again, and then click **Configure**.</span></span>  
  
12. <span data-ttu-id="fd47c-137">Para mapear a variável de ambiente para um parâmetro adicionado ao pacote em tempo de criação ou para um parâmetro gerado quando você converteu o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no modelo de implantação de projeto, siga os procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd47c-137">To map the environment variable to a parameter that you added to the package at design-time or to a parameter that was generated when you converted the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the project deployment model, do the following.,</span></span>  
  
    1.  <span data-ttu-id="fd47c-138">Na guia **Parâmetros** na página **Parâmetros** , clique no botão Procurar ao lado do campo **Valor** .</span><span class="sxs-lookup"><span data-stu-id="fd47c-138">In the **Parameters** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="fd47c-139">Clique em **Usar variável de ambiente**e selecione a variável de ambiente que você criou.</span><span class="sxs-lookup"><span data-stu-id="fd47c-139">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
13. <span data-ttu-id="fd47c-140">Para mapear a variável de ambiente para uma propriedade de gerenciador de conexões, siga os procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd47c-140">To map the environment variable to a connection manager property, do the following.</span></span> <span data-ttu-id="fd47c-141">Os parâmetros são gerados automaticamente no servidor do SSIS para as propriedades do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="fd47c-141">Parameters are automatically generated on the SSIS server for the connection manager properties.</span></span>  
  
    1.  <span data-ttu-id="fd47c-142">Na guia **Gerenciadores de Conexões** na página **Parâmetros**, clique no botão Procurar ao lado do campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="fd47c-142">In the **Connection Managers** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="fd47c-143">Clique em **Usar variável de ambiente**e selecione a variável de ambiente que você criou.</span><span class="sxs-lookup"><span data-stu-id="fd47c-143">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
14. <span data-ttu-id="fd47c-144">Clique em **OK** duas vezes para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="fd47c-144">Click **OK** twice to save your changes.</span></span>  
  
  
