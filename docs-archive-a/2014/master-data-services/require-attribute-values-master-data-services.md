---
title: Exigir valores de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], requiring attribute values
- attributes [Master Data Services], requiring values
ms.assetid: a360ef13-0c34-43b8-a87e-2f5d8732d30e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42b412fc42138c5e186c6c7ad42373f20e35f3cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571424"
---
# <a name="require-attribute-values-master-data-services"></a><span data-ttu-id="513ad-102">Exigir valores de atributos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="513ad-102">Require Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="513ad-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], solicite valores de atributos quando desejar se certificar de que os dados mestres estejam completos.</span><span class="sxs-lookup"><span data-stu-id="513ad-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], require attribute values when you want to ensure your master data is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="513ad-104">Os membros que não possuírem valores de atributos baseados em domínio não serão exibidos em hierarquias derivadas baseadas nessas relações.</span><span class="sxs-lookup"><span data-stu-id="513ad-104">Members that are missing domain-based attribute values are not displayed in derived hierarchies that are based on those relationships.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="513ad-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="513ad-105">Prerequisites</span></span>  
 <span data-ttu-id="513ad-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="513ad-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="513ad-107">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="513ad-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="513ad-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="513ad-108">You must be a model administrator.</span></span> <span data-ttu-id="513ad-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="513ad-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-require-attribute-values"></a><span data-ttu-id="513ad-110">Para solicitar valores de atributos</span><span class="sxs-lookup"><span data-stu-id="513ad-110">To require attribute values</span></span>  
  
1.  <span data-ttu-id="513ad-111">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="513ad-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="513ad-112">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="513ad-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="513ad-113">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="513ad-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="513ad-114">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="513ad-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="513ad-115">Na lista **Tipo de Membro** , selecione um tipo de membro ao qual a regra de negócio será aplicada.</span><span class="sxs-lookup"><span data-stu-id="513ad-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="513ad-116">Na lista **Atributo** , selecione um atributo ou deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="513ad-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="513ad-117">Clique em **Adicionar regra de negócio**.</span><span class="sxs-lookup"><span data-stu-id="513ad-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="513ad-118">Clique em **Editar regra de negócio selecionada**.</span><span class="sxs-lookup"><span data-stu-id="513ad-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="513ad-119">No painel **Componentes** , expanda o nó **Ações** .</span><span class="sxs-lookup"><span data-stu-id="513ad-119">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="513ad-120">Clique em **é obrigatório** e arraste-o para o rótulo de **ação** do painel **then** .</span><span class="sxs-lookup"><span data-stu-id="513ad-120">Click **is required** and drag it to the **THEN** pane's **Action** label.</span></span>  
  
11. <span data-ttu-id="513ad-121">No painel **Atributos** , clique em um atributo e arraste-o até o rótulo **Selecionar atributo** do painel **Editar Ação** .</span><span class="sxs-lookup"><span data-stu-id="513ad-121">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="513ad-122">No painel **Editar Ação** , clique em **Salvar item**.</span><span class="sxs-lookup"><span data-stu-id="513ad-122">In the **Edit Action** pane, click **Save item**.</span></span>  
  
13. <span data-ttu-id="513ad-123">Clique em **Voltar**.</span><span class="sxs-lookup"><span data-stu-id="513ad-123">Click **Back**.</span></span>  
  
14. <span data-ttu-id="513ad-124">Opcionalmente, na página **Manutenção de Regra de Negócio** , na linha que contém sua regra de negócio, clique duas vezes em uma célula da coluna **Nome**, **Descrição**ou **Notificação** para atualizar o valor.</span><span class="sxs-lookup"><span data-stu-id="513ad-124">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
15. <span data-ttu-id="513ad-125">Clique em **Publicar regras de negócio**.</span><span class="sxs-lookup"><span data-stu-id="513ad-125">Click **Publish business rules**.</span></span>  
  
16. <span data-ttu-id="513ad-126">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="513ad-126">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="513ad-127">O status da regra mudará para **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="513ad-127">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="513ad-128">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="513ad-128">Next Steps</span></span>  
  
-   <span data-ttu-id="513ad-129">Aplique regras de negócio a dados seguindo um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="513ad-129">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="513ad-130">Validar membros específicos em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="513ad-130">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="513ad-131">Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="513ad-131">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="513ad-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="513ad-132">See Also</span></span>  
 <span data-ttu-id="513ad-133">[Regras de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="513ad-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="513ad-134">Hierarquias derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="513ad-134">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
