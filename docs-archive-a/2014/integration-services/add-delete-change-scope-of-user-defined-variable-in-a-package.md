---
title: Adicionar, excluir, alterar o escopo da variável definida pelo usuário em um pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], adding
ms.assetid: cbf40c7f-3c8a-48cd-aefa-8b37faf8b40e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7e5980fc7f730c69ef886e4e80760cfbdc9e4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573256"
---
# <a name="add-delete-change-scope-of-user-defined-variable-in-a-package"></a><span data-ttu-id="abf67-102">Adicionar, excluir, alterar o escopo de uma variável definida pelo usuário em um pacote</span><span class="sxs-lookup"><span data-stu-id="abf67-102">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>
  <span data-ttu-id="abf67-103">Estes procedimentos descrevem como adicionar, excluir e alterar o escopo de uma variável definida pelo usuário em um pacote usando a janela **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="abf67-103">These procedures describe how to add, delete, and change the scope of a user-defined variable in a package by using the **Variables** window.</span></span>  
  
 <span data-ttu-id="abf67-104">Para obter mais informações sobre escopo variável, consulte [Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="abf67-104">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="abf67-105">O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] também fornece variáveis do sistema que disponibilizam informações sobre o sistema em tempo de execução e podem ser usadas em contêineres como pacotes e manipuladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="abf67-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] also provides system variables that make system information available at run time and can be used in containers such as packages and event handlers.</span></span> <span data-ttu-id="abf67-106">Você não pode excluir as variáveis de sistema.</span><span class="sxs-lookup"><span data-stu-id="abf67-106">You cannot delete system variables.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="abf67-107">Para adicionar uma variável</span><span class="sxs-lookup"><span data-stu-id="abf67-107">To add a variable</span></span>  
  
1.  <span data-ttu-id="abf67-108">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] com o qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="abf67-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="abf67-109">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="abf67-109">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="abf67-110">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , defina o escopo da variável, seguindo uma das ações:</span><span class="sxs-lookup"><span data-stu-id="abf67-110">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="abf67-111">Para definir o escopo para o pacote, clique na superfície de design da guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="abf67-111">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="abf67-112">Para definir o escopo a um manipulador de eventos, selecione um executável e um manipulador de eventos na superfície de design da guia **Manipulador de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="abf67-112">To set the scope to an event handler, select an executable and an event handler on the design surface of the **Event Handler** tab.</span></span>  
  
    -   <span data-ttu-id="abf67-113">Para definir o escopo para uma tarefa ou contêiner, na superfície de design da guia **Fluxo de Controle** ou **Manipulador de Eventos** , clique na tarefa ou no contêiner.</span><span class="sxs-lookup"><span data-stu-id="abf67-113">To set the scope to a task or container, on the design surface of the **Control Flow** tab or the **Event Handler** tab, click a task or container.</span></span>  
  
4.  <span data-ttu-id="abf67-114">No menu **SSIS** , clique em **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="abf67-114">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="abf67-115">Além disso, você pode exibir a janela **Variáveis** mapeando o comando View.Variables para uma combinação de teclas de sua escolha na página **Teclado** da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="abf67-115">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
5.  <span data-ttu-id="abf67-116">Na janela **variáveis** , clique no ícone **Adicionar variável** .</span><span class="sxs-lookup"><span data-stu-id="abf67-116">In the **Variables** window, click the **Add Variable** icon.</span></span> <span data-ttu-id="abf67-117">A nova variável é adicionada à lista.</span><span class="sxs-lookup"><span data-stu-id="abf67-117">The new variable is added to the list.</span></span>  
  
6.  <span data-ttu-id="abf67-118">Se desejar, clique no ícone **Opções de Grade** , selecione as colunas adicionais a serem exibidas na caixa de diálogo **Opções de Grade Variáveis** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abf67-118">Optionally, click the **Grid Options** icon, select additional columns to show in the **Variables Grid Options** dialog box, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="abf67-119">Como opção, define as propriedades de variáveis.</span><span class="sxs-lookup"><span data-stu-id="abf67-119">Optionally, set the variable properties.</span></span> <span data-ttu-id="abf67-120">Para obter mais informações, consulte [Definir as propriedades de uma variável definida pelo usuário](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span><span class="sxs-lookup"><span data-stu-id="abf67-120">For more information, see [Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span></span>  
  
8.  <span data-ttu-id="abf67-121">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="abf67-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-variable"></a><span data-ttu-id="abf67-122">Para excluir uma variável</span><span class="sxs-lookup"><span data-stu-id="abf67-122">To delete a variable</span></span>  
  
1.  <span data-ttu-id="abf67-123">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="abf67-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="abf67-124">No Gerenciador de Soluções, clique com o botão direito do mouse no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="abf67-124">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="abf67-125">No menu **SSIS** , clique em **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="abf67-125">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="abf67-126">Além disso, você pode exibir a janela **Variáveis** mapeando o comando View.Variables para uma combinação de teclas de sua escolha na página **Teclado** da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="abf67-126">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="abf67-127">Selecione a variável a ser excluída e clique em **Excluir Variável**.</span><span class="sxs-lookup"><span data-stu-id="abf67-127">Select the variable to delete, and then click **Delete Variable**.</span></span>  
  
     <span data-ttu-id="abf67-128">Se você não vir a variável na janela variáveis, clique em **Opções de grade** e selecione **Mostrar variáveis de todos os escopos**.</span><span class="sxs-lookup"><span data-stu-id="abf67-128">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="abf67-129">Se a caixa de diálogo **Confirmar Exclusão de Variáveis** abrir, clique em **Sim** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="abf67-129">If the **Confirm Deletion of Variables** dialog box opens, click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="abf67-130">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="abf67-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-change-the-scope-of-a-variable"></a><span data-ttu-id="abf67-131">Para alterar o escopo de uma variável</span><span class="sxs-lookup"><span data-stu-id="abf67-131">To change the scope of a variable</span></span>  
  
1.  <span data-ttu-id="abf67-132">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="abf67-132">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="abf67-133">No Gerenciador de Soluções, clique com o botão direito do mouse no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="abf67-133">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="abf67-134">No menu **SSIS** , clique em **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="abf67-134">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="abf67-135">Além disso, você pode exibir a janela **Variáveis** mapeando o comando View.Variables para uma combinação de teclas de sua escolha na página **Teclado** da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="abf67-135">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="abf67-136">Selecione a variável e clique em **Mover Variável**.</span><span class="sxs-lookup"><span data-stu-id="abf67-136">Select the variable and then click **Move Variable**.</span></span>  
  
     <span data-ttu-id="abf67-137">Se você não vir a variável na janela variáveis, clique em **Opções de grade** e selecione **Mostrar variáveis de todos os escopos**.</span><span class="sxs-lookup"><span data-stu-id="abf67-137">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="abf67-138">Na caixa de diálogo **Selecionar Novo Escopo** , selecione o pacote ou um contêiner, tarefa ou manipulador de eventos no pacote, para alterar o escopo variável.</span><span class="sxs-lookup"><span data-stu-id="abf67-138">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
6.  <span data-ttu-id="abf67-139">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="abf67-139">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf67-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="abf67-140">See Also</span></span>  
 <span data-ttu-id="abf67-141">[Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="abf67-141">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="abf67-142">[Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="abf67-142">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="abf67-143">[Definir as propriedades de uma variável definida pelo usuário](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span><span class="sxs-lookup"><span data-stu-id="abf67-143">[Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span></span>  
 [<span data-ttu-id="abf67-144">Usar os valores de variáveis e parâmetros em um pacote filho</span><span class="sxs-lookup"><span data-stu-id="abf67-144">Use the Values of Variables and Parameters in a Child Package</span></span>](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md)  
  
  
