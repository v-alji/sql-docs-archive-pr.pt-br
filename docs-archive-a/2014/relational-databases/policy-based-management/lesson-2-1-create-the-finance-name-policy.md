---
title: Criar a política Nome Financeiro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 56b2c852-fd69-4cd2-9b5d-977467b94fd9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 44ffff45f126d2ad9b73c5b8410b8f89ad2b0604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569965"
---
# <a name="create-the-finance-name-policy"></a><span data-ttu-id="c3b4d-102">Criar a política Nome Financeiro</span><span class="sxs-lookup"><span data-stu-id="c3b4d-102">Create the Finance Name Policy</span></span>
  <span data-ttu-id="c3b4d-103">Nessa tarefa, você criará um banco de dados chamado Finance e uma condição que exige que todas as tabelas comecem com as letras **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-103">In this task, you will create a database named Finance, and then create a condition that requires all tables to start with the letters **fintbl**.</span></span> <span data-ttu-id="c3b4d-104">Em seguida, você criará uma política e uma categoria de políticas para impor um padrão de nomenclatura para as tabelas no banco de dados Finanças.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-104">Then, you will create a policy and policy category to enforce a naming standard for tables in the Finance database.</span></span>  
  
### <a name="to-create-the-finance-database"></a><span data-ttu-id="c3b4d-105">Para criar o banco de dados Finanças</span><span class="sxs-lookup"><span data-stu-id="c3b4d-105">To create the Finance database</span></span>  
  
1.  <span data-ttu-id="c3b4d-106">Em [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], abra uma janela de consulta e execute a instrução a seguir:</span><span class="sxs-lookup"><span data-stu-id="c3b4d-106">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window and execute the following statement:</span></span>  
  
    ```  
    CREATE DATABASE Finance ;  
    GO  
    ```  
  
2.  <span data-ttu-id="c3b4d-107">No Pesquisador de Objetos, clique em **Bancos de Dados**e, em seguida, pressione F5 para atualizar a lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-107">In Object Explorer, click **Databases**, and then press F5 to refresh the list of databases.</span></span>  
  
### <a name="to-create-the-finance-tables-condition"></a><span data-ttu-id="c3b4d-108">Para criar a condição Tabelas de Finanças</span><span class="sxs-lookup"><span data-stu-id="c3b4d-108">To create the Finance Tables condition</span></span>  
  
1.  <span data-ttu-id="c3b4d-109">No Pesquisador de Objetos, expanda **Gerenciamento**, **Gerenciamento de Política**, clique com o botão direito do mouse em **Condições**e clique em **Nova Condição**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-109">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Conditions**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="c3b4d-110">Na caixa de diálogo **Criar Nova Condição** , na caixa **Nome** , digite **Tabelas de Finanças**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-110">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Tables**.</span></span>  
  
3.  <span data-ttu-id="c3b4d-111">Na lista **Faceta** , selecione **Nome com Diversas Partes**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-111">In the **Facet** list, select **Multipart Name**.</span></span>  
  
4.  <span data-ttu-id="c3b4d-112">Na área **expressão** , na caixa **campo** , selecione \*\* \@ nome\*\*; na caixa **operador** , selecione **like**; e na caixa **valor** , digite **' fintbl% '** para forçar todos os nomes de tabela a começar com as letras **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-112">In the **Expression** area, in the **Field** box, select **\@Name**; in the **Operator** box, select **Like**; and in the **Value** box, type **'fintbl%'** to force all table names to start with the letters **fintbl**.</span></span>  
  
5.  <span data-ttu-id="c3b4d-113">Na página **Descrição** , digite **Os nomes da tabela de Finanças deve começar com fintbl**e, em seguida, clique em **OK** para criar a condição.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-113">On the **Description** page, type **Finance table names must begin with fintbl**, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-finance-name-policy"></a><span data-ttu-id="c3b4d-114">Para criar a política Nome Financeiro</span><span class="sxs-lookup"><span data-stu-id="c3b4d-114">To create the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="c3b4d-115">No Pesquisador de Objetos, clique com o botão direito do mouse em **Políticas**e clique em **Nova Política**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-115">In Object Explorer, right-click **Policies**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="c3b4d-116">Na caixa de diálogo **Criar Nova Política** , na caixa **Nome** , digite **Nome de Finanças**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-116">In the **Create New Policy** dialog box, in the **Name** box, type **Finance Name**.</span></span>  
  
3.  <span data-ttu-id="c3b4d-117">Na lista **Verificar condição** , selecione **Tabelas de Finanças**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-117">In the **Check condition** list, select **Finance Tables**.</span></span> <span data-ttu-id="c3b4d-118">Isso está na área **Nome com Diversas Partes** .</span><span class="sxs-lookup"><span data-stu-id="c3b4d-118">This is in the **Multipart Name** area.</span></span>  
  
4.  <span data-ttu-id="c3b4d-119">Na área **Contra** você verá uma lista dos objetos de banco de dados que poderiam aplicar essa política.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-119">In the **Against** area you will see a list of the database objects that could apply this policy.</span></span> <span data-ttu-id="c3b4d-120">Selecione a caixa de seleção para **Cada Tabela**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-120">Select the check box for **Every Table**.</span></span>  
  
5.  <span data-ttu-id="c3b4d-121">Na área **Cada Banco de Dados** , expanda **Tudo**e clique em **Nova condição**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-121">In the **Every Database** area, expand **Every**, and then click **New condition**.</span></span>  
  
6.  <span data-ttu-id="c3b4d-122">Na caixa de diálogo **Criar Nova Condição** , na caixa **Nome** , digite **Banco de Dados de Finanças**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-122">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Database**.</span></span>  
  
7.  <span data-ttu-id="c3b4d-123">Na caixa **expressão** , conclua a expressão para incluir \*\* \@ name = ' Finance '\*\* e clique em **OK** para fechar a página condição.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-123">In the **Expression** box, complete the expression to include **\@Name = 'Finance'**, and then click **OK** to close the condition page.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3b4d-124">Você poderia ter a guia fora da caixa **Valor** para habilitar o botão **OK** .</span><span class="sxs-lookup"><span data-stu-id="c3b4d-124">You might have to tab out of the **Value** box to enable the **OK** button.</span></span>  
  
8.  <span data-ttu-id="c3b4d-125">Na lista **Modo de Avaliação** , selecione **Ao alterar: impedir**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-125">In the **Evaluation Mode** list, select **On change: prevent**.</span></span> <span data-ttu-id="c3b4d-126">Isso aplicará a política criando um gatilho de banco de dados no banco de dados Finanças.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-126">This will enforce the policy by creating a database trigger on the Finance database.</span></span>  
  
9. <span data-ttu-id="c3b4d-127">Selecione a lista **Habilitado** .</span><span class="sxs-lookup"><span data-stu-id="c3b4d-127">Select the **Enabled** list.</span></span> <span data-ttu-id="c3b4d-128">(A caixa **Habilitado** não se aplica a políticas **Sob Demanda** .)</span><span class="sxs-lookup"><span data-stu-id="c3b4d-128">(The **Enabled** box does not apply to **On demand** policies.)</span></span>  
  
10. <span data-ttu-id="c3b4d-129">Na lista **Restrição de servidor** , selecione **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-129">In the **Server restriction** list, select **None**.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-create-the-finance-policy-category"></a><span data-ttu-id="c3b4d-130">Para criar a categoria da política Finanças</span><span class="sxs-lookup"><span data-stu-id="c3b4d-130">To create the Finance policy category</span></span>  
  
1.  <span data-ttu-id="c3b4d-131">Em Pesquisador de Objetos, expanda **Gerenciamento**, clique com o botão direito do mouse em **Gerenciamento de Política**e clique em **Gerenciar Categorias**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-131">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="c3b4d-132">Na caixa de diálogo **gerenciar categorias de política** , em **nome**, digite `Finance` na caixa em branco e desmarque autorizar assinaturas de banco de **dados**.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-132">In the **Manage Policy Categories** dialog box, under **Name**, type `Finance` in the blank box, and then clear **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="c3b4d-133">A opção**Autorizar Assinaturas de Banco de Dados** forçará todos os bancos de dados na instância a assinarem as políticas que pertencem a esta categoria de política.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-133">**Mandate Database Subscriptions** will force every database in the instance to subscribe to the policies that belong to this policy category.</span></span> <span data-ttu-id="c3b4d-134">Para esta lição, somente o banco de dados Finanças deve assinar a política Nome Financeiro.</span><span class="sxs-lookup"><span data-stu-id="c3b4d-134">For this lesson, only the Finance database should subscribe to the Finance Name policy.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c3b4d-135">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="c3b4d-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c3b4d-136">Assinar e verificar a política Nome Financeiro</span><span class="sxs-lookup"><span data-stu-id="c3b4d-136">Subscribe to and Check the Finance Name Policy</span></span>](lesson-2-2-subscribe-to-and-check-the-finance-name-policy.md)  
  
  
