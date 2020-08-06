---
title: 'Tarefa 6: verificar se o atributo baseado em domínio é criado usando Master Data Manager | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6e90517a-910c-4c33-8f11-92ac3cff4fdc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ea26202ca9e607058b1e385957be3ea3d04038b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568937"
---
# <a name="task-6-verify-that-the-domain-based-attribute-is-created-using-master-data-manager"></a><span data-ttu-id="e621f-102">Tarefa 6: Verificar se o atributo baseado em domínio foi criado usando o Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="e621f-102">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>
  <span data-ttu-id="e621f-103">Nesta tarefa, verifique se a entidade **State** foi criada no **MDS** e o atributo **State** da entidade **Supplier** é um atributo baseado em domínio que depende da entidade **State** usando o **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="e621f-103">In this task, you verify that the **State** entity is created in **MDS** and the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on the **State** entity by using **Master Data Manager**.</span></span>

1.  <span data-ttu-id="e621f-104">Alterne para o aplicativo Web **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="e621f-104">Switch to the **Master Data Manger** web application.</span></span>

2.  <span data-ttu-id="e621f-105">Clique em **SQL Server 2012 Master Data Services** na parte superior para acessar a home page.</span><span class="sxs-lookup"><span data-stu-id="e621f-105">Click **SQL Server 2012 Master Data Services** at the top to get to the home page.</span></span>

3.  <span data-ttu-id="e621f-106">Verifique se o modelo **Fornecedores** está selecionado e clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="e621f-106">Ensure that **Suppliers** model is selected and click **Explorer**.</span></span> <span data-ttu-id="e621f-107">Você poderia atualizar a página se o **Gerenciador** já estivesse aberto.</span><span class="sxs-lookup"><span data-stu-id="e621f-107">You could refresh the page if you already had **Explorer** open.</span></span>

4.  <span data-ttu-id="e621f-108">Passe o mouse sobre **Entidades** na barra de menus e observe que agora há duas entidades: **Supplier** e **State**.</span><span class="sxs-lookup"><span data-stu-id="e621f-108">Hover your mouse over **Entities** on the menu bar and notice that now there are two entities: **Supplier** and **State**.</span></span>

     <span data-ttu-id="e621f-109">![Menu Entidades com Estado e Fornecedor](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Menu Entidades com Estado e Fornecedor")</span><span class="sxs-lookup"><span data-stu-id="e621f-109">![Entities Menu with State and Supplier](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Entities Menu with State and Supplier")</span></span>

5.  <span data-ttu-id="e621f-110">Clique em **State** se a entidade ainda não estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="e621f-110">Click **State** if the entity is not open already.</span></span>

6.  <span data-ttu-id="e621f-111">Selecione **GA** na lista.</span><span class="sxs-lookup"><span data-stu-id="e621f-111">Select **GA** from the list.</span></span>

7.  <span data-ttu-id="e621f-112">No painel **Detalhes** à direita, altere o **Nome** para **Geórgia** no **painel à direita** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e621f-112">In the **Details** pane to the right, change the **Name** to **Georgia** in the **right pane**, and click **OK**.</span></span>

8.  <span data-ttu-id="e621f-113">Repita as etapas anteriores para outros estados.</span><span class="sxs-lookup"><span data-stu-id="e621f-113">Repeat the previous steps for other states.</span></span>

    |<span data-ttu-id="e621f-114">Código</span><span class="sxs-lookup"><span data-stu-id="e621f-114">Code</span></span>|<span data-ttu-id="e621f-115">Nome</span><span class="sxs-lookup"><span data-stu-id="e621f-115">Name</span></span>|
    |----------|----------|
    |<span data-ttu-id="e621f-116">AC</span><span class="sxs-lookup"><span data-stu-id="e621f-116">CA</span></span>|<span data-ttu-id="e621f-117">Califórnia</span><span class="sxs-lookup"><span data-stu-id="e621f-117">California</span></span>|
    |<span data-ttu-id="e621f-118">CO</span><span class="sxs-lookup"><span data-stu-id="e621f-118">CO</span></span>|<span data-ttu-id="e621f-119">Colorado</span><span class="sxs-lookup"><span data-stu-id="e621f-119">Colorado</span></span>|
    |<span data-ttu-id="e621f-120">IL</span><span class="sxs-lookup"><span data-stu-id="e621f-120">IL</span></span>|<span data-ttu-id="e621f-121">Illinois</span><span class="sxs-lookup"><span data-stu-id="e621f-121">Illinois</span></span>|
    |<span data-ttu-id="e621f-122">DC</span><span class="sxs-lookup"><span data-stu-id="e621f-122">DC</span></span>|<span data-ttu-id="e621f-123">District of Columbia</span><span class="sxs-lookup"><span data-stu-id="e621f-123">District of Columbia</span></span>|
    |<span data-ttu-id="e621f-124">FL</span><span class="sxs-lookup"><span data-stu-id="e621f-124">FL</span></span>|<span data-ttu-id="e621f-125">Florida</span><span class="sxs-lookup"><span data-stu-id="e621f-125">Florida</span></span>|
    |<span data-ttu-id="e621f-126">AL</span><span class="sxs-lookup"><span data-stu-id="e621f-126">AL</span></span>|<span data-ttu-id="e621f-127">Alabama</span><span class="sxs-lookup"><span data-stu-id="e621f-127">Alabama</span></span>|
    |<span data-ttu-id="e621f-128">KY</span><span class="sxs-lookup"><span data-stu-id="e621f-128">KY</span></span>|<span data-ttu-id="e621f-129">Kentucky</span><span class="sxs-lookup"><span data-stu-id="e621f-129">Kentucky</span></span>|
    |<span data-ttu-id="e621f-130">MA</span><span class="sxs-lookup"><span data-stu-id="e621f-130">MA</span></span>|<span data-ttu-id="e621f-131">Massachusetts</span><span class="sxs-lookup"><span data-stu-id="e621f-131">Massachusetts</span></span>|
    |<span data-ttu-id="e621f-132">AZ</span><span class="sxs-lookup"><span data-stu-id="e621f-132">AZ</span></span>|<span data-ttu-id="e621f-133">Arizona</span><span class="sxs-lookup"><span data-stu-id="e621f-133">Arizona</span></span>|
    |<span data-ttu-id="e621f-134">MI</span><span class="sxs-lookup"><span data-stu-id="e621f-134">MI</span></span>|<span data-ttu-id="e621f-135">Michigan</span><span class="sxs-lookup"><span data-stu-id="e621f-135">Michigan</span></span>|
    |<span data-ttu-id="e621f-136">MN</span><span class="sxs-lookup"><span data-stu-id="e621f-136">MN</span></span>|<span data-ttu-id="e621f-137">Minnesota</span><span class="sxs-lookup"><span data-stu-id="e621f-137">Minnesota</span></span>|
    |<span data-ttu-id="e621f-138">NJ</span><span class="sxs-lookup"><span data-stu-id="e621f-138">NJ</span></span>|<span data-ttu-id="e621f-139">New Jersey</span><span class="sxs-lookup"><span data-stu-id="e621f-139">New Jersey</span></span>|
    |<span data-ttu-id="e621f-140">NV</span><span class="sxs-lookup"><span data-stu-id="e621f-140">NV</span></span>|<span data-ttu-id="e621f-141">Nevada</span><span class="sxs-lookup"><span data-stu-id="e621f-141">Nevada</span></span>|
    |<span data-ttu-id="e621f-142">NOVA IORQUE</span><span class="sxs-lookup"><span data-stu-id="e621f-142">NY</span></span>|<span data-ttu-id="e621f-143">Nova York</span><span class="sxs-lookup"><span data-stu-id="e621f-143">New York</span></span>|
    |<span data-ttu-id="e621f-144">OH</span><span class="sxs-lookup"><span data-stu-id="e621f-144">OH</span></span>|<span data-ttu-id="e621f-145">Ohio</span><span class="sxs-lookup"><span data-stu-id="e621f-145">Ohio</span></span>|
    |<span data-ttu-id="e621f-146">OK</span><span class="sxs-lookup"><span data-stu-id="e621f-146">OK</span></span>|<span data-ttu-id="e621f-147">Oklahoma</span><span class="sxs-lookup"><span data-stu-id="e621f-147">Oklahoma</span></span>|
    |<span data-ttu-id="e621f-148">OU</span><span class="sxs-lookup"><span data-stu-id="e621f-148">OR</span></span>|<span data-ttu-id="e621f-149">Oregon</span><span class="sxs-lookup"><span data-stu-id="e621f-149">Oregon</span></span>|
    |<span data-ttu-id="e621f-150">PA</span><span class="sxs-lookup"><span data-stu-id="e621f-150">PA</span></span>|<span data-ttu-id="e621f-151">Pensilvânia</span><span class="sxs-lookup"><span data-stu-id="e621f-151">Pennsylvania</span></span>|
    |<span data-ttu-id="e621f-152">SC</span><span class="sxs-lookup"><span data-stu-id="e621f-152">SC</span></span>|<span data-ttu-id="e621f-153">South Carolina</span><span class="sxs-lookup"><span data-stu-id="e621f-153">South Carolina</span></span>|
    |<span data-ttu-id="e621f-154">KS</span><span class="sxs-lookup"><span data-stu-id="e621f-154">KS</span></span>|<span data-ttu-id="e621f-155">Kansas</span><span class="sxs-lookup"><span data-stu-id="e621f-155">Kansas</span></span>|
    |<span data-ttu-id="e621f-156">TN</span><span class="sxs-lookup"><span data-stu-id="e621f-156">TN</span></span>|<span data-ttu-id="e621f-157">Tennessee</span><span class="sxs-lookup"><span data-stu-id="e621f-157">Tennessee</span></span>|
    |<span data-ttu-id="e621f-158">TX</span><span class="sxs-lookup"><span data-stu-id="e621f-158">TX</span></span>|<span data-ttu-id="e621f-159">Texas</span><span class="sxs-lookup"><span data-stu-id="e621f-159">Texas</span></span>|
    |<span data-ttu-id="e621f-160">UT</span><span class="sxs-lookup"><span data-stu-id="e621f-160">UT</span></span>|<span data-ttu-id="e621f-161">Utah</span><span class="sxs-lookup"><span data-stu-id="e621f-161">Utah</span></span>|
    |<span data-ttu-id="e621f-162">VA</span><span class="sxs-lookup"><span data-stu-id="e621f-162">VA</span></span>|<span data-ttu-id="e621f-163">Virgínia</span><span class="sxs-lookup"><span data-stu-id="e621f-163">Virginia</span></span>|
    |<span data-ttu-id="e621f-164">WA</span><span class="sxs-lookup"><span data-stu-id="e621f-164">WA</span></span>|<span data-ttu-id="e621f-165">Washington</span><span class="sxs-lookup"><span data-stu-id="e621f-165">Washington</span></span>|
    |<span data-ttu-id="e621f-166">WI</span><span class="sxs-lookup"><span data-stu-id="e621f-166">WI</span></span>|<span data-ttu-id="e621f-167">Wisconsin</span><span class="sxs-lookup"><span data-stu-id="e621f-167">Wisconsin</span></span>|
    |<span data-ttu-id="e621f-168">HI</span><span class="sxs-lookup"><span data-stu-id="e621f-168">HI</span></span>|<span data-ttu-id="e621f-169">Hawaii</span><span class="sxs-lookup"><span data-stu-id="e621f-169">Hawaii</span></span>|
    |<span data-ttu-id="e621f-170">MD</span><span class="sxs-lookup"><span data-stu-id="e621f-170">MD</span></span>|<span data-ttu-id="e621f-171">Maryland</span><span class="sxs-lookup"><span data-stu-id="e621f-171">Maryland</span></span>|
    |<span data-ttu-id="e621f-172">CT</span><span class="sxs-lookup"><span data-stu-id="e621f-172">CT</span></span>|<span data-ttu-id="e621f-173">Connecticut</span><span class="sxs-lookup"><span data-stu-id="e621f-173">Connecticut</span></span>|

9. <span data-ttu-id="e621f-174">Selecione qualquer uma das entradas de estado e clique em **Exibir Transações** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e621f-174">Select any of the state entries and click **View Transactions** from the Toolbar.</span></span> <span data-ttu-id="e621f-175">Você deverá visualizar a transação da atualização que acabou de fazer na lista de transações.</span><span class="sxs-lookup"><span data-stu-id="e621f-175">You should see the transaction for the update you just made is in the list of transactions.</span></span>

10. <span data-ttu-id="e621f-176">Passe o mouse sobre o menu **Entidades** e clique em **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="e621f-176">Hover the mouse over **Entities** menu and click **Supplier**.</span></span>

11. <span data-ttu-id="e621f-177">Agora, observe que um valor para o campo **Estado** pode ser alterado no painel **Detalhes** usando a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e621f-177">Now, notice that a value for the **State** field can be changed in the **Details** pane by using the drop-down list.</span></span> <span data-ttu-id="e621f-178">Você também pode observar que, na lista à esquerda e na lista suspensa no painel **Detalhes**, o código será exibido primeiro e depois o nome entre chaves.</span><span class="sxs-lookup"><span data-stu-id="e621f-178">You can also see that, in the list to the left and in the drop-down list in the **Details** pane, code is displayed first and then the name in curly braces.</span></span> <span data-ttu-id="e621f-179">Também é possível alterar qualquer outro valor no painel **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e621f-179">You can also change any other value in the **Details** pane.</span></span>

     <span data-ttu-id="e621f-180">![Atributo Estado com Código e Nomes atualizados](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "Atributo Estado com Código e Nomes atualizados")</span><span class="sxs-lookup"><span data-stu-id="e621f-180">![State Attribute with Updated Code and Names](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "State Attribute with Updated Code and Names")</span></span>

## <a name="next-step"></a><span data-ttu-id="e621f-181">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e621f-181">Next Step</span></span>
 [<span data-ttu-id="e621f-182">Tarefa 7: Exibindo as atualizações feitas usando o Master Data Manager no Excel</span><span class="sxs-lookup"><span data-stu-id="e621f-182">Task 7: Viewing Updates Made using Master Data Manager in Excel</span></span>](../../2014/tutorials/task-7-viewing-updates-made-using-master-data-manager-in-excel.md)


