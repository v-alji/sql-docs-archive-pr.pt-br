---
title: Criar uma política de gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policies
ms.assetid: b28bf963-89f9-4941-b6c1-6004fec347f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e76b4dce17e00bae5e8ca4fcf071868c0641c786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574673"
---
# <a name="create-a-policy-based-management-policy"></a><span data-ttu-id="68b55-102">Criar uma política do Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="68b55-102">Create a Policy-Based Management Policy</span></span>
  <span data-ttu-id="68b55-103">Este tópico descreve como criar uma Política de Gerenciamento Baseado em Políticas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68b55-103">This topic describes how to create a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="68b55-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="68b55-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="68b55-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="68b55-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="68b55-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="68b55-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="68b55-107">**Para criar uma política, usando:**</span><span class="sxs-lookup"><span data-stu-id="68b55-107">**To create a policy, using:**</span></span>  
  
     [<span data-ttu-id="68b55-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68b55-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="68b55-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="68b55-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="68b55-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="68b55-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="68b55-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="68b55-111">Permissions</span></span>  
 <span data-ttu-id="68b55-112">Requer a associação à função PolicyAdministratorRole no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="68b55-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="68b55-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68b55-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-policy"></a><span data-ttu-id="68b55-114">Para criar uma política</span><span class="sxs-lookup"><span data-stu-id="68b55-114">To create a policy</span></span>  
  
1.  <span data-ttu-id="68b55-115">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja criar uma nova política de Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="68b55-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a new a Policy-Based Management policy.</span></span>  
  
2.  <span data-ttu-id="68b55-116">Clique no sinal de adição para expandir a pasta **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="68b55-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="68b55-117">Clique no sinal de adição para expandir a pasta **Gerenciamento de Política**.</span><span class="sxs-lookup"><span data-stu-id="68b55-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="68b55-118">Clique com o botão direito do mouse na pasta **Políticas** e selecione **Nova Política**.</span><span class="sxs-lookup"><span data-stu-id="68b55-118">Right-click the **Policies** folder and select **New Policy**.</span></span>  
  
5.  <span data-ttu-id="68b55-119">Na caixa de diálogo **Criar Nova Política** , na caixa **Nome** , digite o nome da nova política.</span><span class="sxs-lookup"><span data-stu-id="68b55-119">In the **Create New Policy** dialog box, in the **Name** box, type the name of the new policy.</span></span>  
  
6.  <span data-ttu-id="68b55-120">Se você quiser habilitar a política assim que seja criado, marque a caixa de seleção **Habilitado** .</span><span class="sxs-lookup"><span data-stu-id="68b55-120">If you want the policy to be enabled as soon as it is created, select the **Enabled** check box.</span></span> <span data-ttu-id="68b55-121">Se o modo de avaliação for **Sob Demanda**, a caixa de seleção **Habilitado** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="68b55-121">If the evaluation mode is **On demand**, the **Enabled** check box is not available.</span></span>  
  
7.  <span data-ttu-id="68b55-122">Na lista **Verificar condição** , selecione um das condições existentes ou selecione **Nova Condição**.</span><span class="sxs-lookup"><span data-stu-id="68b55-122">In the **Check condition** list, select one of the existing conditions, or select **New Condition**.</span></span> <span data-ttu-id="68b55-123">Para editar uma condição, selecione a condição e clique nas reticências ( **...** ). Para obter mais informações, veja [Criar uma nova condição de Gerenciamento Baseado em Políticas](create-a-new-policy-based-management-condition.md) ou [Exibir ou modificar as propriedades de uma condição de Gerenciamento Baseado em Políticas](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span><span class="sxs-lookup"><span data-stu-id="68b55-123">To edit a condition, select the condition and then click the ellipsis (**...**). For more information, see [Create a New Policy-Based Management Condition](create-a-new-policy-based-management-condition.md) or [View or Modify the Properties of a Policy-Based Management Condition](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span></span>  
  
8.  <span data-ttu-id="68b55-124">Na caixa **Em relação aos destinos** , selecione um ou mais tipos de destino para essa política.</span><span class="sxs-lookup"><span data-stu-id="68b55-124">In the **Against targets** box, select one or more target types for this policy.</span></span> <span data-ttu-id="68b55-125">Só podem ser se aplicadas algumas condições e facetas a certos tipos de destinos.</span><span class="sxs-lookup"><span data-stu-id="68b55-125">Some conditions and facets can only be applied to certain types of targets.</span></span> <span data-ttu-id="68b55-126">Os conjuntos de destino disponíveis aparecem na caixa associada.</span><span class="sxs-lookup"><span data-stu-id="68b55-126">The available target sets appear in the associated box.</span></span> <span data-ttu-id="68b55-127">Expanda **Todo** para selecionar uma condição de filtragem para alguns tipos de destinos.</span><span class="sxs-lookup"><span data-stu-id="68b55-127">Expand **Every** to select a filtering condition for some types of the targets.</span></span> <span data-ttu-id="68b55-128">Se nenhum destino for exibido nesta caixa, o escopo da condição de verificação será no nível de servidor.</span><span class="sxs-lookup"><span data-stu-id="68b55-128">If no targets appear in this box, the check condition is scoped at the server level.</span></span>  
  
9. <span data-ttu-id="68b55-129">Na caixa **Modo de Avaliação** , selecione como essa política se comportará.</span><span class="sxs-lookup"><span data-stu-id="68b55-129">In the **Evaluation Mode** box, select how this policy will behave.</span></span> <span data-ttu-id="68b55-130">Condições diferentes podem ter modos de avaliação válidos diferentes.</span><span class="sxs-lookup"><span data-stu-id="68b55-130">Different conditions can have different valid evaluation modes.</span></span> <span data-ttu-id="68b55-131">Para obter mais informações sobre quais modos de avaliação são válidos, veja [Administrar servidores usando o Gerenciamento Baseado em Políticas](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="68b55-131">For more information about which evaluation modes are valid, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
10. <span data-ttu-id="68b55-132">Se a política for avaliada em um agendamento, clique em **Ao Agendar**e em **Escolher** para selecionar um agendamento ou clique em **Novo** para criar um novo agendamento.</span><span class="sxs-lookup"><span data-stu-id="68b55-132">If the policy will be evaluated on a schedule, set the evaluation mode to **On schedule**, and then click **Pick** to select a schedule, or click **New** to create a new schedule.</span></span>  
  
11. <span data-ttu-id="68b55-133">Para limitar a política a um subconjunto dos tipos de destino, na caixa **Restrição de servidor** , selecione a partir das condições de limitação ou crie uma nova condição.</span><span class="sxs-lookup"><span data-stu-id="68b55-133">To limit the policy to subset of the target types, in the **Server restriction** box, select from limiting conditions or create a new condition.</span></span>  
  
     <span data-ttu-id="68b55-134">Para obter mais informações sobre as opções disponíveis contidas na caixa de diálogo **Criar Nova Política** , consulte [Caixas de diálogo Criar Nova Política ou Abrir política, Página geral](../../integration-services/general-page-of-integration-services-designers-options.md) ou [Caixas de diálogo Criar Nova Política ou Abrir Política, página Descrição](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="68b55-134">For more information on the available options in the **Create New Policy** dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) or [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
12. <span data-ttu-id="68b55-135">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="68b55-135">When finished click **OK**.</span></span>  
  
  
