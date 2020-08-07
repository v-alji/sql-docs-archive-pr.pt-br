---
title: Usar os valores de variáveis e parâmetros em um pacote filho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], passing between packages
- configurations [Integration Services]
- packages [Integration Services], configurations
- variables [Integration Services], adding
ms.assetid: 9b939edb-4e17-48e5-8428-855beb10049c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 28561db91e5e924d8b25f9c7be7a4a51c6c315ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575907"
---
# <a name="use-the-values-of-variables-and-parameters-in-a-child-package"></a><span data-ttu-id="ccd10-102">Usar os valores de variáveis e parâmetros em um pacote filho</span><span class="sxs-lookup"><span data-stu-id="ccd10-102">Use the Values of Variables and Parameters in a Child Package</span></span>
  <span data-ttu-id="ccd10-103">Este procedimento descreve como criar uma configuração de pacote que usa o tipo de configuração variável pai.</span><span class="sxs-lookup"><span data-stu-id="ccd10-103">This procedure describes how to create a package configuration that uses the parent variable configuration type.</span></span> <span data-ttu-id="ccd10-104">Este tipo de configuração habilita um pacote filho que é executado de um pacote pai para acessar uma variável no pai.</span><span class="sxs-lookup"><span data-stu-id="ccd10-104">This configuration type enables a child package that is run from a parent package to access a variable in the parent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccd10-105">Você também pode passar valores para um pacote filho configurando a tarefa Executar Pacote para mapear as variáveis de pacote pai ou parâmetros, ou parâmetros de projeto, para parâmetros de pacote filho.</span><span class="sxs-lookup"><span data-stu-id="ccd10-105">You can also pass values to a child package by configuring the Execute Package Task to map parent package variables or parameters, or project parameters, to child package parameters.</span></span> <span data-ttu-id="ccd10-106">Para obter mais informações, consulte [Execute Package Task](control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="ccd10-106">For more information, see [Execute Package Task](control-flow/execute-package-task.md).</span></span>  
  
 <span data-ttu-id="ccd10-107">Não é necessário criar a variável no pacote pai antes de criar a configuração de pacote no pacote filho.</span><span class="sxs-lookup"><span data-stu-id="ccd10-107">It is not necessary to create the variable in the parent package before you create the package configuration in the child package.</span></span> <span data-ttu-id="ccd10-108">É possível adicionar a variável ao pacote pai a qualquer momento, mas será preciso usar o nome exato da variável pai na configuração do pacote.</span><span class="sxs-lookup"><span data-stu-id="ccd10-108">You can add the variable to the parent package at any time, but you must use the exact name of the parent variable in the package configuration.</span></span> <span data-ttu-id="ccd10-109">Entretanto, antes de criar uma configuração da variável pai, é preciso que exista uma variável no pacote filho que possa ser atualizada pela configuração.</span><span class="sxs-lookup"><span data-stu-id="ccd10-109">However, before you can create a parent variable configuration, there must be an existing variable in the child package that the configuration can update.</span></span> <span data-ttu-id="ccd10-110">Para obter mais informações sobre como adicionar e configurar variáveis, consulte [Adicionar, excluir, alterar o escopo de uma variável definida pelo usuário em um pacote](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="ccd10-110">For more information about adding and configuring variables, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
 <span data-ttu-id="ccd10-111">O escopo da variável no pacote pai que é usado na configuração da variável pai pode ser definido como a tarefa Executar Pacote, tanto para o contêiner que tenha a tarefa quanto para o pacote.</span><span class="sxs-lookup"><span data-stu-id="ccd10-111">The scope of the variable in the parent package that is used in a parent variable configuration can be set to the Execute Package task, to the container that has the task, or to the package.</span></span> <span data-ttu-id="ccd10-112">Se várias variáveis tiverem o mesmo nome, será usada a variável que tiver o escopo mais próximo da tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="ccd10-112">If multiple variables with the same name are defined in a package, the variable that is closest in scope to the Execute Package task is used.</span></span> <span data-ttu-id="ccd10-113">O escopo mais próximo da tarefa Executar Pacote é a própria tarefa.</span><span class="sxs-lookup"><span data-stu-id="ccd10-113">The closest scope to the Execute Package task is the task itself.</span></span>  
  
### <a name="to-add-a-variable-to-a-parent-package"></a><span data-ttu-id="ccd10-114">Adicionar uma variável a um pacote pai</span><span class="sxs-lookup"><span data-stu-id="ccd10-114">To add a variable to a parent package</span></span>  
  
1.  <span data-ttu-id="ccd10-115">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote no qual deseja adicionar uma variável para passar a um pacote filho.</span><span class="sxs-lookup"><span data-stu-id="ccd10-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a variable to pass to a child package.</span></span>  
  
2.  <span data-ttu-id="ccd10-116">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="ccd10-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ccd10-117">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , defina o escopo da variável, seguindo uma das ações:</span><span class="sxs-lookup"><span data-stu-id="ccd10-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="ccd10-118">Para definir o escopo para o pacote, clique na superfície de design da guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="ccd10-118">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="ccd10-119">Para definir o escopo para um contêiner pai da tarefa Executar Pacote, clique no contêiner.</span><span class="sxs-lookup"><span data-stu-id="ccd10-119">To set the scope to a parent container of the Execute Package task, click the container.</span></span>  
  
    -   <span data-ttu-id="ccd10-120">Para definir o escopo da tarefa Executar Pacote, clique na tarefa.</span><span class="sxs-lookup"><span data-stu-id="ccd10-120">To set the scope to the Execute Package task, click the task.</span></span>  
  
4.  <span data-ttu-id="ccd10-121">Adicione e configure uma variável.</span><span class="sxs-lookup"><span data-stu-id="ccd10-121">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ccd10-122">Selecione um tipo de dados que seja compatível com os dados que serão armazenados pela variável.</span><span class="sxs-lookup"><span data-stu-id="ccd10-122">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="ccd10-123">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="ccd10-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-variable-to-a-child-package"></a><span data-ttu-id="ccd10-124">Adicionar uma variável a um pacote filho</span><span class="sxs-lookup"><span data-stu-id="ccd10-124">To add a variable to a child package</span></span>  
  
1.  <span data-ttu-id="ccd10-125">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote no qual deseja adicionar uma configuração de variável pai.</span><span class="sxs-lookup"><span data-stu-id="ccd10-125">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a parent variable configuration.</span></span>  
  
2.  <span data-ttu-id="ccd10-126">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="ccd10-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ccd10-127">No Designer de [!INCLUDE[ssIS](../includes/ssis-md.md)] , defina o escopo para o pacote e clique na superfície de design da guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="ccd10-127">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="ccd10-128">Adicione e configure uma variável.</span><span class="sxs-lookup"><span data-stu-id="ccd10-128">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ccd10-129">Selecione um tipo de dados que seja compatível com os dados que serão armazenados pela variável.</span><span class="sxs-lookup"><span data-stu-id="ccd10-129">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="ccd10-130">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="ccd10-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-parent-package-configuration-to-a-child-package"></a><span data-ttu-id="ccd10-131">Adicionar uma configuração de pacote pai a um pacote filho</span><span class="sxs-lookup"><span data-stu-id="ccd10-131">To add a parent package configuration to a child package</span></span>  
  
1.  <span data-ttu-id="ccd10-132">Se ainda não estiver aberto, abra o pacote filho no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccd10-132">If it is not already open, open the child package in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="ccd10-133">Clique na superfície de design da guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="ccd10-133">Click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="ccd10-134">No menu **SSIS** , clique em **Configurações do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="ccd10-134">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="ccd10-135">Na caixa de diálogo **Organizador de Configurações do Pacote** , selecione **Ativar configurações do pacote**e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ccd10-135">In the **Package Configuration Organizer** dialog box, select **Enable package configuration**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="ccd10-136">Na página inicial do Assistente de Configuração de Pacotes, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ccd10-136">On the welcome page of the Package Configuration Wizard, click **Next.**</span></span>  
  
6.  <span data-ttu-id="ccd10-137">Na página Selecionar Tipo de Configuração, na lista **Tipo de configuração** , selecione **Variável do pacote pai** e siga um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ccd10-137">On the Select Configuration Type page, in the **Configuration type** list, select **Parent package variable** and do one of the following:</span></span>  
  
    -   <span data-ttu-id="ccd10-138">Selecione **Especificar as configurações de configuração diretamente**e na caixa **Variável pai** , forneça o nome da variável no pacote pai a ser usado na configuração.</span><span class="sxs-lookup"><span data-stu-id="ccd10-138">Select **Specify configuration settings directly**, and then in the **Parent variable** box, provide the name of the variable in the parent package to use in the configuration.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="ccd10-139">Nomes de variáveis fazem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ccd10-139">Variable names are case sensitive.</span></span>  
  
    -   <span data-ttu-id="ccd10-140">Selecione **O local de configuração está armazenado em uma variável do ambiente** e, na lista **Variável de ambiente**, selecione a variável de ambiente que contém o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="ccd10-140">Select or **Configuration location is stored in an environment variable,** and then in the **Environment variable list**, select the environmentvariable that contains the name of the variable.</span></span>  
  
7.  <span data-ttu-id="ccd10-141">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ccd10-141">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="ccd10-142">Na página Selecionar Propriedade de Destino, expanda o nó **Variável** e o nó **Propriedades** da variável a ser configurada e, em seguida, clique na propriedade que será definida pela configuração.</span><span class="sxs-lookup"><span data-stu-id="ccd10-142">On the Select Target Property page, expand the **Variable** node, and expand the **Properties** node of the variable to configure, and then click the property to be set by the configuration.</span></span>  
  
9. <span data-ttu-id="ccd10-143">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ccd10-143">Click **Next**.</span></span>  
  
10. <span data-ttu-id="ccd10-144">Na página Concluindo o Assistente, você pode modificar o nome padrão da configuração e revisar a informações de configuração (opcional).</span><span class="sxs-lookup"><span data-stu-id="ccd10-144">On the Completing the Wizard page, optionally, modify the default name of the configuration and review the configuration information.</span></span>  
  
11. <span data-ttu-id="ccd10-145">Clique em **Concluir** para concluir o assistente e retornar para a caixa de diálogo **Organizador de Configurações do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="ccd10-145">Click **Finish** to complete the wizard and return to the **Package Configuration Organizer** dialog box.</span></span>  
  
12. <span data-ttu-id="ccd10-146">Na caixa de diálogo **Organizador de Configurações do Pacote** , a caixa **Configuração** lista a nova configuração.</span><span class="sxs-lookup"><span data-stu-id="ccd10-146">In the **Package Configuration Organizer** dialog box, the **Configuration** box lists the new configuration.</span></span>  
  
13. <span data-ttu-id="ccd10-147">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="ccd10-147">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd10-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ccd10-148">See Also</span></span>  
 <span data-ttu-id="ccd10-149">[Configurações do pacote](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="ccd10-149">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="ccd10-150">[Criar configurações de pacote](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="ccd10-150">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 <span data-ttu-id="ccd10-151">[Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="ccd10-151">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="ccd10-152">Usar variáveis em pacotes</span><span class="sxs-lookup"><span data-stu-id="ccd10-152">Use Variables in Packages</span></span>](../../2014/integration-services/use-variables-in-packages.md)  
  
  
