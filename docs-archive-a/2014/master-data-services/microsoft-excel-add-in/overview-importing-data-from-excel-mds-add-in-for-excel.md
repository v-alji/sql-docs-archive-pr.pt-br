---
title: Publicando dados (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ea84a9aa-aeec-411b-ab8d-bc1b14f864a3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ab37a353469d1902394a3e2cd8060d9be82abb40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682342"
---
# <a name="publishing-data-mds-add-in-for-excel"></a><span data-ttu-id="c6e39-102">Publicando dados (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="c6e39-102">Publishing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="c6e39-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publique dados no repositório do MDS quando quiser compartilhá-lo com outros usuários.</span><span class="sxs-lookup"><span data-stu-id="c6e39-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you want to share it with other users.</span></span> <span data-ttu-id="c6e39-104">Assim que os dados são publicados, eles ficam disponíveis para outros usuários do suplemento para download.</span><span class="sxs-lookup"><span data-stu-id="c6e39-104">As soon as data is published, it is available for other users of the Add-in to download.</span></span>  
  
 <span data-ttu-id="c6e39-105">Ao publicar dados, qualquer dado que você adicionou ou atualizou será publicado no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="c6e39-105">When you publish data, any data you've added or updated is published to the MDS repository.</span></span> <span data-ttu-id="c6e39-106">Os dados que você excluiu não são publicados – é necessário excluir os dados separadamente.</span><span class="sxs-lookup"><span data-stu-id="c6e39-106">Data you've deleted is not published-you must delete data separately.</span></span> <span data-ttu-id="c6e39-107">Para obter mais informações, consulte [Excluir uma linha &#40;Suplemento MDS para Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="c6e39-107">For more information, see [Delete a Row &#40;MDS Add-in for Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6e39-108">A publicação não pode ser usada para criar uma nova entidade.</span><span class="sxs-lookup"><span data-stu-id="c6e39-108">Publishing cannot be used to create a new entity.</span></span> <span data-ttu-id="c6e39-109">Para obter mais informações sobre como criar entidades, consulte [Criar uma entidade &#40;Suplemento MDS para Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="c6e39-109">For more information about creating entities, see [Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span></span>  
  
## <a name="when-multiple-users-publish-at-the-same-time"></a><span data-ttu-id="c6e39-110">Quando vários usuários publicam ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="c6e39-110">When Multiple Users Publish at the Same Time</span></span>  
 <span data-ttu-id="c6e39-111">Vários usuários podem publicar atualizações dos mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="c6e39-111">Multiple users can publish updates to the same data.</span></span> <span data-ttu-id="c6e39-112">Conforme cada usuário publica, a atualização é salva no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6e39-112">As each user publishes, the update is saved to the database.</span></span> <span data-ttu-id="c6e39-113">Isso significa que um usuário que não estava trabalhando com os dados atualizados mais recentemente ainda pode alterar o valor quando ele publicá-los.</span><span class="sxs-lookup"><span data-stu-id="c6e39-113">This means that a user who was not working with the most recently-updated data can still change the value when he or she publishes.</span></span>  
  
 <span data-ttu-id="c6e39-114">Somente as atualizações que você faz são publicadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6e39-114">Only the updates you make are published to the database.</span></span> <span data-ttu-id="c6e39-115">Os dados desatualizados na planilha não são publicados.</span><span class="sxs-lookup"><span data-stu-id="c6e39-115">Any out-of-date data in the worksheet is not published.</span></span>  
  
## <a name="transactions-and-annotations"></a><span data-ttu-id="c6e39-116">Transações e anotações</span><span class="sxs-lookup"><span data-stu-id="c6e39-116">Transactions and Annotations</span></span>  
 <span data-ttu-id="c6e39-117">Cada alteração publicada é salva como transação.</span><span class="sxs-lookup"><span data-stu-id="c6e39-117">Each published change is saved as a transaction.</span></span> <span data-ttu-id="c6e39-118">Se quiser, você pode adicionar anotações (comentários) a uma transação, para explicar por que fez a alteração.</span><span class="sxs-lookup"><span data-stu-id="c6e39-118">If you choose, you can add annotations (comments) to a transaction, to explain why you made the change.</span></span>  
  
-   <span data-ttu-id="c6e39-119">Você não pode anotar exclusões, embora as exclusões sejam salvas como transações que podem ser revertidas por um administrador.</span><span class="sxs-lookup"><span data-stu-id="c6e39-119">You cannot annotate deletions, although deletions are saved as transactions that can be reversed by an administrator.</span></span>  
  
-   <span data-ttu-id="c6e39-120">Se você alterar o valor de **código** de um membro, ele não será registrado como uma transação e todas as transações anteriores para o membro não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c6e39-120">If you change the **Code** value for a member, it is not recorded as a transaction, and all previous transactions for the member are unavailable.</span></span>  
  
-   <span data-ttu-id="c6e39-121">Você pode ver as transações feitas em um membro por outros usuários.</span><span class="sxs-lookup"><span data-stu-id="c6e39-121">You can view transactions made to a member by other users.</span></span> <span data-ttu-id="c6e39-122">Também será possível exibir todas as transações que você fez em um membro, mesmo se não tiver mais permissão para atributos específicos.</span><span class="sxs-lookup"><span data-stu-id="c6e39-122">You can also view all transactions you've made to a member, even if you no longer have permission to specific attributes.</span></span>  
  
 <span data-ttu-id="c6e39-123">Você pode ver todas as transações feitas em um membro.</span><span class="sxs-lookup"><span data-stu-id="c6e39-123">You can view all transactions made to a member.</span></span> <span data-ttu-id="c6e39-124">Para obter mais informações, consulte [Exibir todas as anotações ou transações de um membro &#40;Suplemento MDS para Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="c6e39-124">For more information, see [View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c6e39-125">Se você inserir uma anotação de mais de 500 caracteres, a anotação será truncada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c6e39-125">If you enter an annotation of more than 500 characters, the annotation is automatically truncated.</span></span>  
  
## <a name="business-rule-and-other-validation"></a><span data-ttu-id="c6e39-126">Regra de negócio e outra validação</span><span class="sxs-lookup"><span data-stu-id="c6e39-126">Business Rule and Other Validation</span></span>  
 <span data-ttu-id="c6e39-127">Ao publicar dados, a validação é executada para garantir que dados estejam precisos antes de serem adicionados ao repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="c6e39-127">When you publish data, validation is performed to ensure data is accurate before it's added to the MDS repository.</span></span> <span data-ttu-id="c6e39-128">Se os dados não estiverem de acordo com os critérios especificados, eles não serão publicados no repositório.</span><span class="sxs-lookup"><span data-stu-id="c6e39-128">If the data does not meet specified criteria, it will not be published to the repository.</span></span> <span data-ttu-id="c6e39-129">Para obter mais informações, consulte [Validando dados &#40;Suplemento MDS para Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="c6e39-129">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c6e39-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c6e39-130">Related Tasks</span></span>  
  
|<span data-ttu-id="c6e39-131">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="c6e39-131">Task Description</span></span>|<span data-ttu-id="c6e39-132">Tópico</span><span class="sxs-lookup"><span data-stu-id="c6e39-132">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="c6e39-133">Publique dados da planilha ativa novamente no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="c6e39-133">Publish data from the active worksheet back to the MDS repository.</span></span>|[<span data-ttu-id="c6e39-134">Publicar dados do Excel para o MDS &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c6e39-134">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)|  
|<span data-ttu-id="c6e39-135">Exclua uma linha do repositório do MDS e da planilha ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c6e39-135">Delete a row from the MDS repository and from the worksheet at the same time.</span></span>|[<span data-ttu-id="c6e39-136">Excluir uma linha &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c6e39-136">Delete a Row &#40;MDS Add-in for Excel&#41;</span></span>](delete-a-row-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="c6e39-137">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="c6e39-137">Related Content</span></span>  
  
-   [<span data-ttu-id="c6e39-138">Atualizando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c6e39-138">Refreshing Data &#40;MDS Add-in for Excel&#41;</span></span>](refreshing-data-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="c6e39-139">Suplemento do Master Data Services para Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="c6e39-139">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
