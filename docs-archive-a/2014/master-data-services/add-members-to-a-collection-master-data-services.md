---
title: Adicionar membros a uma coleção (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], adding members
ms.assetid: 1a7155e6-2d4a-4ed1-a72c-edb37fa1a46b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce2038f3bc90a2f17506b0aadaaf9707fa911896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583141"
---
# <a name="add-members-to-a-collection-master-data-services"></a><span data-ttu-id="d167f-102">Adicionar membros a uma coleção (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d167f-102">Add Members to a Collection (Master Data Services)</span></span>
  <span data-ttu-id="d167f-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], você pode adicionar membros folha e consolidados a uma coleção.</span><span class="sxs-lookup"><span data-stu-id="d167f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can add leaf and consolidated members to a collection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d167f-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d167f-104">Prerequisites</span></span>  
 <span data-ttu-id="d167f-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="d167f-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d167f-106">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="d167f-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="d167f-107">Você deve ter, no mínimo, a permissão **Atualizar** para o objeto de modelo de coleção ao qual está adicionando membros.</span><span class="sxs-lookup"><span data-stu-id="d167f-107">You must have a minimum of **Update** permission to the collection model object that you are adding members to.</span></span>  
  
-   <span data-ttu-id="d167f-108">Uma coleção deve existir.</span><span class="sxs-lookup"><span data-stu-id="d167f-108">A collection must exist.</span></span> <span data-ttu-id="d167f-109">Para obter mais informações, consulte [Criar uma coleção &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d167f-109">For more information, see [Create a Collection &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span></span>  
  
### <a name="to-add-members-to-a-collection"></a><span data-ttu-id="d167f-110">Para adicionar membros a uma coleção</span><span class="sxs-lookup"><span data-stu-id="d167f-110">To add members to a collection</span></span>  
  
1.  <span data-ttu-id="d167f-111">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="d167f-111">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="d167f-112">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="d167f-112">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="d167f-113">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="d167f-113">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="d167f-114">Na barra de menus, aponte para **Coleções** e clique em *entity_name*.</span><span class="sxs-lookup"><span data-stu-id="d167f-114">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="d167f-115">Na grade, clique na linha da coleção à qual você deseja adicionar membros.</span><span class="sxs-lookup"><span data-stu-id="d167f-115">In the grid, click the row for the collection you want to add members to.</span></span>  
  
6.  <span data-ttu-id="d167f-116">Clique na guia **Membros da Coleção** .</span><span class="sxs-lookup"><span data-stu-id="d167f-116">Click the **Collection Members** tab.</span></span>  
  
7.  <span data-ttu-id="d167f-117">Clique em **Editar Membros**.</span><span class="sxs-lookup"><span data-stu-id="d167f-117">Click **Edit Members**.</span></span>  
  
8.  <span data-ttu-id="d167f-118">Para filtrar a lista de membros disponíveis, selecione na lista à esquerda.</span><span class="sxs-lookup"><span data-stu-id="d167f-118">To filter the list of available members, select from the list on the left.</span></span>  
  
9. <span data-ttu-id="d167f-119">Clique na linha com o membro a ser adicionado e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d167f-119">Click the row with the member you want to add and click **Add**.</span></span>  
  
10. <span data-ttu-id="d167f-120">Opcionalmente, reorganize os membros da coleção clicando em **Acima** ou **Abaixo**.</span><span class="sxs-lookup"><span data-stu-id="d167f-120">Optionally, rearrange collection members by clicking **Up** or **Down**.</span></span>  
  
11. <span data-ttu-id="d167f-121">Opcionalmente, defina valores de peso clicando no valor na coluna **Peso** .</span><span class="sxs-lookup"><span data-stu-id="d167f-121">Optionally, set weight values by clicking the value in the **Weight** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d167f-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d167f-122">See Also</span></span>  
 [<span data-ttu-id="d167f-123">Coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d167f-123">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
