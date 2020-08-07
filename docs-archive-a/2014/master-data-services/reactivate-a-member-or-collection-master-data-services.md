---
title: Reativar um membro ou coleção (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], reactivating
- consolidated members [Master Data Services], reactivating
- reactivating members [Master Data Services]
- members [Master Data Services], reactivating
- reactivating collections [Master Data Services]
- leaf members [Master Data Services], reactivating
ms.assetid: bb4884c0-3658-4763-92d1-636804278b1c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c449a5a277128bbca6ae24e848bcf12cb0881968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581440"
---
# <a name="reactivate-a-member-or-collection-master-data-services"></a><span data-ttu-id="c8962-102">Reativar um membro ou coleção (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c8962-102">Reactivate a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="c8962-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], você pode reativar um membro que estava:</span><span class="sxs-lookup"><span data-stu-id="c8962-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can reactivate a member that was either:</span></span>  
  
-   <span data-ttu-id="c8962-104">Desativado pelo processo de preparo.</span><span class="sxs-lookup"><span data-stu-id="c8962-104">Deactivated by the staging process.</span></span>  
  
-   <span data-ttu-id="c8962-105">Excluído do MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8962-105">Deleted in the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span></span>  
  
-   <span data-ttu-id="c8962-106">Excluído do aplicativo Web do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8962-106">Deleted in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="c8962-107">Quando você reativa um membro, seus atributos e sua associação em hierarquias e coleções são restaurados.</span><span class="sxs-lookup"><span data-stu-id="c8962-107">When you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span>  
  
 <span data-ttu-id="c8962-108">Você também pode reativar coleções.</span><span class="sxs-lookup"><span data-stu-id="c8962-108">You can also reactivate collections.</span></span> <span data-ttu-id="c8962-109">Quando você fizer isso, são restaurados os atributos da coleção e os membros que pertencem à coleção.</span><span class="sxs-lookup"><span data-stu-id="c8962-109">When you do, the collection's attributes and the members that belong to the collection are restored.</span></span>  
  
 <span data-ttu-id="c8962-110">Quando uma coleção ou membro é reativado, todas as transações anteriores são restauradas.</span><span class="sxs-lookup"><span data-stu-id="c8962-110">When either a collection or member is reactivated, all previous transactions are restored.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c8962-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c8962-111">Prerequisites</span></span>  
 <span data-ttu-id="c8962-112">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="c8962-112">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c8962-113">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** .</span><span class="sxs-lookup"><span data-stu-id="c8962-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you must have permission to the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="c8962-114">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="c8962-114">You must be a model administrator.</span></span> <span data-ttu-id="c8962-115">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c8962-115">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reactivate-a-member-or-collection"></a><span data-ttu-id="c8962-116">Para reativar um membro ou coleção</span><span class="sxs-lookup"><span data-stu-id="c8962-116">To reactivate a member or collection</span></span>  
  
1.  <span data-ttu-id="c8962-117">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , clique em **Gerenciamento de Versões**.</span><span class="sxs-lookup"><span data-stu-id="c8962-117">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="c8962-118">Na barra de menus, clique em **Transações**.</span><span class="sxs-lookup"><span data-stu-id="c8962-118">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="c8962-119">Na página **Transações** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="c8962-119">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c8962-120">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="c8962-120">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="c8962-121">No painel **Transações** , clique na linha do membro ou da coleção que você deseja reativar.</span><span class="sxs-lookup"><span data-stu-id="c8962-121">In the **Transactions** pane, click the row for the member or collection you want to reactivate.</span></span> <span data-ttu-id="c8962-122">Essa linha deve ter **Ativo** exibido na coluna **Valor Anterior** e **Desativado** na coluna **Novo Valor** .</span><span class="sxs-lookup"><span data-stu-id="c8962-122">This row should have **Active** displayed in the **Prior Value** column and **De-Activated** in the **New Value** column.</span></span>  
  
6.  <span data-ttu-id="c8962-123">Clique em **Inverter Transação**.</span><span class="sxs-lookup"><span data-stu-id="c8962-123">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="c8962-124">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8962-124">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="c8962-125">Uma nova transação é adicionada, mostrando **Ativo** na coluna **Novo Valor** .</span><span class="sxs-lookup"><span data-stu-id="c8962-125">A new transaction is added, showing **Active** in the **New Value** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8962-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8962-126">See Also</span></span>  
 <span data-ttu-id="c8962-127">[Desativar ou excluir membros usando o processo de preparo &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c8962-127">[Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="c8962-128">[Excluir um membro ou uma coleção &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c8962-128">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="c8962-129">[Membros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c8962-129">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="c8962-130">Coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c8962-130">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
