---
title: Reservar uma transação (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], reversing
ms.assetid: 6f7c3f07-0f64-4283-8c9c-93facd00a046
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fb5b1b0932b65b1d6f8fe7b1bc842836e21aaca6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680001"
---
# <a name="reverse-a-transaction-master-data-services"></a><span data-ttu-id="6643a-102">Inverter uma transação (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6643a-102">Reverse a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="6643a-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], os administradores podem inverter uma transação quando uma ação precisar ser desfeita.</span><span class="sxs-lookup"><span data-stu-id="6643a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], administrators can reverse a transaction when an action needs to be undone.</span></span> <span data-ttu-id="6643a-104">Exemplos de transações são alterações de valor de atributo, movimentos de hierarquia ou exclusões de membro.</span><span class="sxs-lookup"><span data-stu-id="6643a-104">Examples of transactions are attribute value changes, hierarchy moves, or member deletions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6643a-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6643a-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="6643a-106">Você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** .</span><span class="sxs-lookup"><span data-stu-id="6643a-106">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="6643a-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="6643a-107">You must be a model administrator.</span></span> <span data-ttu-id="6643a-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6643a-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reverse-a-transaction"></a><span data-ttu-id="6643a-109">Para inverter uma transação</span><span class="sxs-lookup"><span data-stu-id="6643a-109">To reverse a transaction</span></span>  
  
1.  <span data-ttu-id="6643a-110">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , clique em **Gerenciamento de Versões**.</span><span class="sxs-lookup"><span data-stu-id="6643a-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="6643a-111">Na barra de menus, clique em **Transações**.</span><span class="sxs-lookup"><span data-stu-id="6643a-111">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="6643a-112">Na página **Transações** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="6643a-112">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="6643a-113">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="6643a-113">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="6643a-114">Clique na linha da grade da transação que você deseja inverter.</span><span class="sxs-lookup"><span data-stu-id="6643a-114">Click the row in the grid for the transaction you want to reverse.</span></span>  
  
6.  <span data-ttu-id="6643a-115">Clique em **Inverter Transação**.</span><span class="sxs-lookup"><span data-stu-id="6643a-115">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="6643a-116">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6643a-116">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="6643a-117">Outra transação é adicionada à grade para registrar a transação invertida.</span><span class="sxs-lookup"><span data-stu-id="6643a-117">Another transaction is added to the grid to record the reversed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6643a-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6643a-118">See Also</span></span>  
 <span data-ttu-id="6643a-119">[Transações &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6643a-119">[Transactions &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span></span>  
 [<span data-ttu-id="6643a-120">Reativar um membro ou uma coleção &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6643a-120">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)  
  
  
