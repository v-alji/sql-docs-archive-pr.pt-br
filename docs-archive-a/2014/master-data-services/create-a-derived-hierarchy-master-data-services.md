---
title: Criar uma hierarquia derivada (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, creating
- creating derived hierarchies [Master Data Services]
ms.assetid: fec653c4-11cc-46a2-8dd8-b605341ebb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 20469ad30222e43a3104503cc32187c2e6512743
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680972"
---
# <a name="create-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="d0a6c-102">Criar uma hierarquia derivada (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d0a6c-102">Create a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="d0a6c-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie uma hierarquia derivada quando desejar uma hierarquia baseada em nível que assegure que os membros existam no nível correto.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a derived hierarchy when you want a level-based hierarchy that ensures that members exist at the correct level.</span></span> <span data-ttu-id="d0a6c-104">As hierarquias derivadas são baseadas em relações de atributos baseados em domínio que existem em um modelo.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-104">Derived hierarchies are based on the domain-based attribute relationships that exist in a model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0a6c-105">Se não existir um valor de atributo baseado em domínio para um membro, o membro não será incluído na hierarquia derivada.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-105">If a domain-based attribute value doesn't exist for a member, the member is not included in the derived hierarchy.</span></span> <span data-ttu-id="d0a6c-106">Consulte [Exigir valores de atributos &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) para exigir um valor de atributo baseado em domínio para todos os membros.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-106">See [Require Attribute Values &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) to require a domain-based attribute value for all members.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d0a6c-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d0a6c-107">Prerequisites</span></span>  
 <span data-ttu-id="d0a6c-108">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="d0a6c-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d0a6c-109">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="d0a6c-109">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="d0a6c-110">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-110">You must be a model administrator.</span></span> <span data-ttu-id="d0a6c-111">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d0a6c-111">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-derived-hierarchy"></a><span data-ttu-id="d0a6c-112">Para criar uma hierarquia derivada</span><span class="sxs-lookup"><span data-stu-id="d0a6c-112">To create a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="d0a6c-113">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="d0a6c-114">Na página **exibição de modelo** , na barra de menus, aponte para **gerenciar** e clique em **hierarquias derivadas**.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="d0a6c-115">Na página **Manutenção da Hierarquia Derivada** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-115">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="d0a6c-116">Clique em **Adicionar hierarquia derivada**.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-116">Click **Add derived hierarchy**.</span></span>  
  
5.  <span data-ttu-id="d0a6c-117">Na página **Adicionar Hierarquia Derivada** , na caixa **Nome da hierarquia derivada** , digite um nome para a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-117">On the **Add Derived Hierarchy** page, in the **Derived hierarchy name** box, type a name for the hierarchy.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="d0a6c-118">Use um nome que descreva os níveis na hierarquia, por exemplo, **Produto para Subcategoria para Categoria**.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-118">Use a name that describes the levels in the hierarchy, for example **Product to Subcategory to Category**.</span></span>  
  
6.  <span data-ttu-id="d0a6c-119">Clique em **Salvar hierarquia derivada**.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-119">Click **Save derived hierarchy**.</span></span>  
  
7.  <span data-ttu-id="d0a6c-120">Na página **Editar hierarquia derivada** , no painel **entidades e hierarquias disponíveis** , clique em uma entidade ou hierarquia e arraste-a para o painel **níveis atuais** .</span><span class="sxs-lookup"><span data-stu-id="d0a6c-120">On the **Edit Derived Hierarchy** page, in the **Available Entities and Hierarchies** pane, click an entity or hierarchy and drag it to the **Current Levels** pane.</span></span>  
  
8.  <span data-ttu-id="d0a6c-121">Continue a arrastar entidades ou hierarquias até que sua hierarquia esteja completa.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-121">Continue dragging entities or hierarchies until your hierarchy is complete.</span></span>  
  
9. <span data-ttu-id="d0a6c-122">Clique em **Voltar**.</span><span class="sxs-lookup"><span data-stu-id="d0a6c-122">Click **Back**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a6c-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0a6c-123">See Also</span></span>  
 <span data-ttu-id="d0a6c-124">[Hierarquias derivadas &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d0a6c-124">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="d0a6c-125">[Hierarquias derivadas com limites explícitos &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d0a6c-125">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="d0a6c-126">Atributos baseados em domínio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d0a6c-126">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)  
  
  
