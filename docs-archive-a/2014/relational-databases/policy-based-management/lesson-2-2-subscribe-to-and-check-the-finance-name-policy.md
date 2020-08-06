---
title: Assinar e verificar a política Nome Financeiro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 126b4c4c-2a1c-4701-a0ad-8de23fbd7306
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2bfe6f463d03fe8b95f000dc6f34dc0718a7729f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569395"
---
# <a name="subscribe-to-and-check-the-finance-name-policy"></a><span data-ttu-id="ebecd-102">Assinar e verificar a política Nome Financeiro</span><span class="sxs-lookup"><span data-stu-id="ebecd-102">Subscribe to and Check the Finance Name Policy</span></span>
  <span data-ttu-id="ebecd-103">Nesta tarefa, você configurará o banco de dados Finanças para assinar a categoria de políticas Finanças.</span><span class="sxs-lookup"><span data-stu-id="ebecd-103">In this task, you will configure the Finance database to subscribe to the Finance policy category.</span></span> <span data-ttu-id="ebecd-104">Então, você testará a política Nome de Finanças.</span><span class="sxs-lookup"><span data-stu-id="ebecd-104">Then, you will test the Finance Name policy.</span></span>  
  
### <a name="to-subscribe-to-the-finance-policy-category"></a><span data-ttu-id="ebecd-105">Para assinar a categoria de políticas Finanças</span><span class="sxs-lookup"><span data-stu-id="ebecd-105">To subscribe to the Finance policy category</span></span>  
  
1.  <span data-ttu-id="ebecd-106">No Pesquisador de objetos, expanda **bancos de dados**, clique com o botão direito do mouse `Finance` , aponte para **políticas**e clique em **categorias**.</span><span class="sxs-lookup"><span data-stu-id="ebecd-106">In Object Explorer, expand **Databases**, right-click `Finance`, point to **Policies**, and then click **Categories**.</span></span>  
  
2.  <span data-ttu-id="ebecd-107">Marque a caixa de seleção **assinada** da `Finance` categoria.</span><span class="sxs-lookup"><span data-stu-id="ebecd-107">Select the **Subscribed** checkbox for the `Finance` category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-enforcement-of-the-finance-name-policy"></a><span data-ttu-id="ebecd-108">Para testar a execução da política Nome de Finanças</span><span class="sxs-lookup"><span data-stu-id="ebecd-108">To test the enforcement of the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="ebecd-109">Em [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], abra uma janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="ebecd-109">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window.</span></span> <span data-ttu-id="ebecd-110">Execute as instruções a seguir que tentam criar uma tabela que viola a política **Nome de Finanças** .</span><span class="sxs-lookup"><span data-stu-id="ebecd-110">Execute the following statements that try to create a table that violates the **Finance Name** policy.</span></span> <span data-ttu-id="ebecd-111">A tabela viola a política porque o nome de tabela não começa com as letras **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="ebecd-111">The table violates the policy because the table name does not begin with the letters **fintbl**.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE NewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="ebecd-112">Observe que a política impede que a tabela seja criada e retorne uma mensagem informativa que forneça o nome da política.</span><span class="sxs-lookup"><span data-stu-id="ebecd-112">Notice that the policy prevents the table from being created and returns an informational message that provides the policy name.</span></span>  
  
2.  <span data-ttu-id="ebecd-113">Para fornecer um nome válido, modifique o código como se segue e execute a instrução novamente.</span><span class="sxs-lookup"><span data-stu-id="ebecd-113">To provide a valid name, modify the code as follows and run the statement again.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE fintblNewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="ebecd-114">Neste momento, a tabela é criada.</span><span class="sxs-lookup"><span data-stu-id="ebecd-114">This time, the table is created.</span></span>  
  
### <a name="to-apply-the-policy-to-the-whole-server"></a><span data-ttu-id="ebecd-115">Para aplicar a política ao servidor inteiro</span><span class="sxs-lookup"><span data-stu-id="ebecd-115">To apply the policy to the whole server</span></span>  
  
1.  <span data-ttu-id="ebecd-116">Atualmente, o banco de dados Finanças se inscreve na categoria de política Finanças.</span><span class="sxs-lookup"><span data-stu-id="ebecd-116">Currently, only the Finance database subscribes to the Finance policy category.</span></span> <span data-ttu-id="ebecd-117">Em muitos casos, é mais fácil aplicar a categoria de política ao servidor inteiro.</span><span class="sxs-lookup"><span data-stu-id="ebecd-117">In many cases, it is easier to apply the policy category to the whole server.</span></span> <span data-ttu-id="ebecd-118">Em Pesquisador de Objetos, expanda **Gerenciamento**, clique com o botão direito do mouse em **Gerenciamento de Política**e clique em **Gerenciar Categorias**.</span><span class="sxs-lookup"><span data-stu-id="ebecd-118">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="ebecd-119">Na caixa de diálogo **Gerenciar Categorias de Política** , localize a categoria Finanças e marque a caixa de seleção **Autorizar Assinaturas de Bancos de Dados** para a categoria Finanças.</span><span class="sxs-lookup"><span data-stu-id="ebecd-119">In the **Manage Policy Categories** dialog box, locate the Finance category, and select the **Mandate Database Subscriptions** checkbox for the Finance category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)] <span data-ttu-id="ebecd-120">Agora a categoria Finanças se aplica a todos os bancos de dados, mas a condição que você criou restringe a política Nome de Finanças ao banco de dados Finanças.</span><span class="sxs-lookup"><span data-stu-id="ebecd-120">Now the Finance category applies to all databases, but the condition that you have created restricts the Finance Name policy to the Finance database.</span></span> <span data-ttu-id="ebecd-121">Isso mostra como você pode usar combinações complexas de políticas de destino de forma a aplicá-las corretamente em muitos servidores.</span><span class="sxs-lookup"><span data-stu-id="ebecd-121">This shows how you can use complex combinations of conditions to target policies in ways that will apply correctly on many servers.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="ebecd-122">Resumo</span><span class="sxs-lookup"><span data-stu-id="ebecd-122">Summary</span></span>  
 <span data-ttu-id="ebecd-123">Este tutorial mostrou como criar condições do Gerenciamento Baseado em Políticas, políticas e grupos de políticas e como aplicar filtros e verificar a compatibilidade de destinos de Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="ebecd-123">This tutorial has shown you how to create Policy-Based Management conditions, policies and policy groups, and how to apply filters and check the compliance of Policy-Based Management targets.</span></span>  
  
## <a name="next"></a><span data-ttu-id="ebecd-124">Avançar</span><span class="sxs-lookup"><span data-stu-id="ebecd-124">Next</span></span>  
 <span data-ttu-id="ebecd-125">Este tutorial está concluído.</span><span class="sxs-lookup"><span data-stu-id="ebecd-125">This tutorial is finished.</span></span> <span data-ttu-id="ebecd-126">Para retornar ao início, clique em [Tutorial: Administrando servidores com o Gerenciamento Baseado em Políticas](tutorial-administering-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="ebecd-126">To return to the start, click [Tutorial: Administering Servers by Using Policy-Based Management](tutorial-administering-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="ebecd-127">Para obter uma lista de tutoriais, consulte os [tutoriais para SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="ebecd-127">For a list of tutorials, see [Tutorials for SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebecd-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ebecd-128">See Also</span></span>  
 [<span data-ttu-id="ebecd-129">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="ebecd-129">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
