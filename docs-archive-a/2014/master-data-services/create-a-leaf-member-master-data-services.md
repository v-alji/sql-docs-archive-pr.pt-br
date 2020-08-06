---
title: Criar um membro folha (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services], creating
- creating leaf members [Master Data Services]
- members [Master Data Services], creating leaf members
ms.assetid: 0499d3b3-d508-4d43-a740-19cf53ade9f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe0245dd30019e1cb9112754bd8b8eeafed93aa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568682"
---
# <a name="create-a-leaf-member-master-data-services"></a><span data-ttu-id="91e42-102">Criar um membro folha (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="91e42-102">Create a Leaf Member (Master Data Services)</span></span>
  <span data-ttu-id="91e42-103">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , crie um membro folha quando desejar adicionar dados mestres ao seu sistema e não estiver usando tabelas de preparo ou o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] para importar dados.</span><span class="sxs-lookup"><span data-stu-id="91e42-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a leaf member when you want to add master data to your system and are not using staging tables or the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] to import data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="91e42-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="91e42-104">Prerequisites</span></span>  
 <span data-ttu-id="91e42-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="91e42-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="91e42-106">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="91e42-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="91e42-107">Você deve ter, no mínimo, a permissão **Atualizar** para o objeto de modelo folha da entidade à qual você está adicionando um membro.</span><span class="sxs-lookup"><span data-stu-id="91e42-107">You must have a minimum of **Update** permission to the leaf model object for the entity you are adding a member to.</span></span>  
  
### <a name="to-create-a-leaf-member"></a><span data-ttu-id="91e42-108">Para criar um membro folha</span><span class="sxs-lookup"><span data-stu-id="91e42-108">To create a leaf member</span></span>  
  
1.  <span data-ttu-id="91e42-109">Na home page do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="91e42-109">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="91e42-110">Se você for um usuário, selecione uma versão aberta da lista **Versão** .</span><span class="sxs-lookup"><span data-stu-id="91e42-110">If you are a user, select an open version from the **Version** list.</span></span> <span data-ttu-id="91e42-111">Se você for um administrador, selecione uma versão com status aberto ou bloqueado da lista **Versão** .</span><span class="sxs-lookup"><span data-stu-id="91e42-111">If you are an administrator, select a version with open or locked status from the **Version** list.</span></span>  
  
3.  <span data-ttu-id="91e42-112">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="91e42-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="91e42-113">Na barra de menus, aponte para **Entidades** e clique no nome da entidade à qual você deseja adicionar um membro.</span><span class="sxs-lookup"><span data-stu-id="91e42-113">From the menu bar, point to **Entities** and click the name of the entity you want to add a member to.</span></span>  
  
5.  <span data-ttu-id="91e42-114">Clique em **Adicionar membro**.</span><span class="sxs-lookup"><span data-stu-id="91e42-114">Click **Add member**.</span></span>  
  
6.  <span data-ttu-id="91e42-115">No painel **Detalhes** , preencha os campos.</span><span class="sxs-lookup"><span data-stu-id="91e42-115">In the **Details** pane, complete the fields.</span></span>  
  
7.  <span data-ttu-id="91e42-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="91e42-116">Optional.</span></span> <span data-ttu-id="91e42-117">Na caixa **Anotações** , digite um comentário sobre por que o membro foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="91e42-117">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="91e42-118">Todos os usuários que têm acesso ao membro podem exibir a anotação.</span><span class="sxs-lookup"><span data-stu-id="91e42-118">All users who have access to the member can view the annotation.</span></span>  
  
8.  <span data-ttu-id="91e42-119">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="91e42-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e42-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91e42-120">See Also</span></span>  
 <span data-ttu-id="91e42-121">[Carregar ou atualizar Membros no Master Data Services usando o processo de preparo](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="91e42-121">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="91e42-122">[Criar um membro consolidado &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="91e42-122">[Create a Consolidated Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span></span>  
 [<span data-ttu-id="91e42-123">Membros &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91e42-123">Members &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/members-master-data-services.md)  
  
  
