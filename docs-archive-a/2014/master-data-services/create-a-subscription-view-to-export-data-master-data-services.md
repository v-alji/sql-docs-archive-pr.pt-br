---
title: Criar uma exibição de assinatura (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- subscription views [Master Data Services], creating
- creating subscription views [Master Data Services]
ms.assetid: a5e28961-af16-414a-9845-d2e06aac5214
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e5e2b901e56d75e97a444fd2858ef95872f3b766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575895"
---
# <a name="create-a-subscription-view-master-data-services"></a><span data-ttu-id="c059d-102">Criar uma exibição de assinatura (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c059d-102">Create a Subscription View (Master Data Services)</span></span>
  <span data-ttu-id="c059d-103">Crie uma exibição de assinatura quando desejar criar uma exibição dos dados no [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] banco de dado para uso por sistemas de assinatura.</span><span class="sxs-lookup"><span data-stu-id="c059d-103">Create a subscription view when you want to create a view of your data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database for use by subscribing systems.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c059d-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c059d-104">Prerequisites</span></span>  
 <span data-ttu-id="c059d-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="c059d-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c059d-106">Você deve ter permissão para acessar a área funcional **Gerenciamento de Integração** .</span><span class="sxs-lookup"><span data-stu-id="c059d-106">You must have permission to access the **Integration Management** functional area.</span></span>  
  
-   <span data-ttu-id="c059d-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="c059d-107">You must be a model administrator.</span></span> <span data-ttu-id="c059d-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c059d-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-subscription-view"></a><span data-ttu-id="c059d-109">Para criar uma exibição de assinatura</span><span class="sxs-lookup"><span data-stu-id="c059d-109">To create a subscription view</span></span>  
  
1.  <span data-ttu-id="c059d-110">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Gerenciamento de Integração**.</span><span class="sxs-lookup"><span data-stu-id="c059d-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Integration Management**.</span></span>  
  
2.  <span data-ttu-id="c059d-111">Da barra de menus, clique em **Criar Exibições**.</span><span class="sxs-lookup"><span data-stu-id="c059d-111">From the menu bar, click **Create Views**.</span></span>  
  
3.  <span data-ttu-id="c059d-112">Na página **exibições de assinatura** , clique em **Adicionar exibição de assinatura**.</span><span class="sxs-lookup"><span data-stu-id="c059d-112">On the **Subscription Views** page, click **Add subscription view**.</span></span>  
  
4.  <span data-ttu-id="c059d-113">No painel **criar exibição de assinatura** , na caixa **nome da exibição de assinatura** , digite um nome para a exibição.</span><span class="sxs-lookup"><span data-stu-id="c059d-113">In the **Create Subscription View** pane, in the **Subscription view name** box, type a name for the view.</span></span>  
  
5.  <span data-ttu-id="c059d-114">Na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="c059d-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="c059d-115">Selecione a opção **versão** ou **sinalizador** de versão e, em seguida, selecione na lista correspondente.</span><span class="sxs-lookup"><span data-stu-id="c059d-115">Select either the **Version** or **Version Flag** option, and then select from the corresponding list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="c059d-116">Crie uma exibição de assinatura com base em um sinalizador de versão.</span><span class="sxs-lookup"><span data-stu-id="c059d-116">Create a subscription view based on a version flag.</span></span> <span data-ttu-id="c059d-117">Quando você bloqueia uma versão, pode reatribuir o sinalizador a uma versão aberta sem atualizar a exibição de assinatura.</span><span class="sxs-lookup"><span data-stu-id="c059d-117">When you lock a version, you can reassign the flag to an open version without updating the subscription view.</span></span>  
  
7.  <span data-ttu-id="c059d-118">Selecione a opção **entidade** ou **hierarquia derivada** e, em seguida, selecione na lista correspondente.</span><span class="sxs-lookup"><span data-stu-id="c059d-118">Select either the **Entity** or **Derived hierarchy** option, and then select from the corresponding list.</span></span>  
  
8.  <span data-ttu-id="c059d-119">Selecione um formato de exibição de assinatura na lista **Formato** .</span><span class="sxs-lookup"><span data-stu-id="c059d-119">From the **Format** list, select a subscription view format.</span></span>  
  
9. <span data-ttu-id="c059d-120">Se você escolheu **Níveis Explícitos** ou **Níveis Derivados** da lista **Formato** , digite o número de níveis na hierarquia para incluir na exibição.</span><span class="sxs-lookup"><span data-stu-id="c059d-120">If you chose **Explicit levels** or **Derived levels** from the **Format** list, type the number of levels in the hierarchy to include in the view.</span></span>  
  
10. <span data-ttu-id="c059d-121">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c059d-121">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c059d-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c059d-122">See Also</span></span>  
 <span data-ttu-id="c059d-123">[Exportando dados &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c059d-123">[Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span></span>  
 <span data-ttu-id="c059d-124">[Excluir uma exibição de assinatura &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c059d-124">[Delete a Subscription View &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span></span>  
 [<span data-ttu-id="c059d-125">Criar um sinalizador de versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c059d-125">Create a Version Flag &#40;Master Data Services&#41;</span></span>](create-a-version-flag-master-data-services.md)  
  
  
