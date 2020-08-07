---
title: Anotar uma transação (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c384f4241d0ddcd78fd8942fe28da8c0b5b1e77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681733"
---
# <a name="annotate-a-transaction-master-data-services"></a><span data-ttu-id="286c8-102">Anotar uma transação (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="286c8-102">Annotate a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="286c8-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], anote uma transação quando desejar fornecer detalhes de suporte sobre a transação para objetivos históricos.</span><span class="sxs-lookup"><span data-stu-id="286c8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], annotate a transaction when you want to provide supporting details about the transaction for historical purposes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="286c8-104">Não é possível excluir anotações.</span><span class="sxs-lookup"><span data-stu-id="286c8-104">You cannot delete annotations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="286c8-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="286c8-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="286c8-106">Para anotar as transações criadas, você deve ter permissões para acessar a área funcional **Explorer** e ter, no mínimo, a permissão **Atualizar** no objeto do modelo que você deseja anotar.</span><span class="sxs-lookup"><span data-stu-id="286c8-106">To annotate transactions that you created, you must have permission to access the **Explorer** functional area, and have a minimum of **Update** permission to the model object you want to annotate.</span></span>  
  
-   <span data-ttu-id="286c8-107">Para anotar transações para todos os usuários, você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** e ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="286c8-107">To annotate transactions for all users, you must have permission to access the **Version Management** functional area and be a model administrator.</span></span> <span data-ttu-id="286c8-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="286c8-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-annotate-a-transaction-in-explorer"></a><span data-ttu-id="286c8-109">Para anotar uma transação no Explorer</span><span class="sxs-lookup"><span data-stu-id="286c8-109">To annotate a transaction in Explorer</span></span>  
  
1.  <span data-ttu-id="286c8-110">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="286c8-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="286c8-111">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="286c8-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="286c8-112">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="286c8-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="286c8-113">Na barra de menus, aponte para **Entidades** e clique na entidade que contém o membro com a transação que você deseja anotar.</span><span class="sxs-lookup"><span data-stu-id="286c8-113">From the menu bar, point to **Entities** and click the entity that contains the member with a transaction you want to annotate.</span></span>  
  
5.  <span data-ttu-id="286c8-114">Na grade, clique na linha do membro.</span><span class="sxs-lookup"><span data-stu-id="286c8-114">In the grid, click the row of the member.</span></span>  
  
6.  <span data-ttu-id="286c8-115">Clique em **Exibir Transações**.</span><span class="sxs-lookup"><span data-stu-id="286c8-115">Click **View Transactions**.</span></span>  
  
7.  <span data-ttu-id="286c8-116">Na caixa de diálogo **Exibir Transações** , clique na transação que você deseja anotar.</span><span class="sxs-lookup"><span data-stu-id="286c8-116">In the **View Transactions** dialog box, click the transaction you want to annotate.</span></span>  
  
8.  <span data-ttu-id="286c8-117">Na caixa na parte inferior da caixa de diálogo, digite sua anotação.</span><span class="sxs-lookup"><span data-stu-id="286c8-117">In the box at the bottom of the dialog box, type your annotation.</span></span>  
  
9. <span data-ttu-id="286c8-118">Clique em **Adicionar Anotação**.</span><span class="sxs-lookup"><span data-stu-id="286c8-118">Click **Add Annotation**.</span></span> <span data-ttu-id="286c8-119">A anotação é exibida no painel **Anotações** .</span><span class="sxs-lookup"><span data-stu-id="286c8-119">The annotation is displayed in the **Annotations** pane.</span></span>  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a><span data-ttu-id="286c8-120">Para anotar uma transação no Gerenciamento de Versão (somente administradores)</span><span class="sxs-lookup"><span data-stu-id="286c8-120">To annotate a transaction in Version Management (administrators only)</span></span>  
  
1.  <span data-ttu-id="286c8-121">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , clique em **Gerenciamento de Versões**.</span><span class="sxs-lookup"><span data-stu-id="286c8-121">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="286c8-122">Na barra de menus, clique em **Transações**.</span><span class="sxs-lookup"><span data-stu-id="286c8-122">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="286c8-123">No painel **Transações** , clique na linha da grade da transação que você deseja anotar.</span><span class="sxs-lookup"><span data-stu-id="286c8-123">In the **Transactions** pane, click the row in the grid for the transaction you want to annotate.</span></span>  
  
4.  <span data-ttu-id="286c8-124">No painel **Anotações da Transação** , na caixa **Anotação** , digite a anotação.</span><span class="sxs-lookup"><span data-stu-id="286c8-124">In the **Transaction Annotations** pane, in the **Annotation** box, type your annotation.</span></span>  
  
5.  <span data-ttu-id="286c8-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="286c8-125">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="286c8-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="286c8-126">See Also</span></span>  
 <span data-ttu-id="286c8-127">[&#40;de anotações Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="286c8-127">[Annotations &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span></span>  
 [<span data-ttu-id="286c8-128">Transações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="286c8-128">Transactions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/transactions-master-data-services.md)  
  
  
