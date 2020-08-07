---
title: Gerar automaticamente valores de atributo diferentes de código (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b82f6f81-6e9c-4918-9ea9-4ab5f5d11b15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8db6c89bdce2a11a5a54ed3a763a7bc41bd7f1be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581995"
---
# <a name="automatically-generate-attribute-values-other-than-code-master-data-services"></a><span data-ttu-id="c6818-102">Gerar automaticamente valores de atributo diferentes de código (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c6818-102">Automatically Generate Attribute Values Other Than Code (Master Data Services)</span></span>
  <span data-ttu-id="c6818-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], gera automaticamente valores para os valores de atributo da entidade quando você deseja atribuir um inteiro automaticamente como o valor sempre que as regras de negócio são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="c6818-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's attribute values when you want an integer to be automatically assigned as the value each time business rules are applied.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c6818-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c6818-104">Prerequisites</span></span>  
 <span data-ttu-id="c6818-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="c6818-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c6818-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="c6818-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c6818-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="c6818-107">You must be a model administrator.</span></span> <span data-ttu-id="c6818-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c6818-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c6818-109">Um atributo numérico deve existir.</span><span class="sxs-lookup"><span data-stu-id="c6818-109">A numeric attribute must exist.</span></span> <span data-ttu-id="c6818-110">Para obter mais informações, consulte [Criar um atributo numérico &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c6818-110">For more information, see [Create a Numeric Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-an-attribute-value"></a><span data-ttu-id="c6818-111">Para gerar automaticamente um valor de atributo</span><span class="sxs-lookup"><span data-stu-id="c6818-111">To automatically generate an attribute value</span></span>  
  
1.  <span data-ttu-id="c6818-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="c6818-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c6818-113">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="c6818-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="c6818-114">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="c6818-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c6818-115">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="c6818-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="c6818-116">Na lista **Tipo de Membro** , selecione um tipo de membro ao qual a regra de negócio será aplicada.</span><span class="sxs-lookup"><span data-stu-id="c6818-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="c6818-117">Na lista **Atributo** , deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="c6818-117">From the **Attribute** list, leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="c6818-118">Clique em **Adicionar regra de negócio**.</span><span class="sxs-lookup"><span data-stu-id="c6818-118">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="c6818-119">Clique em **Editar regra de negócio selecionada**.</span><span class="sxs-lookup"><span data-stu-id="c6818-119">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="c6818-120">No painel **Componentes** , expanda o nó **Ações** .</span><span class="sxs-lookup"><span data-stu-id="c6818-120">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="c6818-121">No nó Valor Padrão, clique em **padrões para um valor gerado** e arraste-o até o rótulo **Ações** do painel **THEN**.</span><span class="sxs-lookup"><span data-stu-id="c6818-121">In the Default Value node, click **defaults to a generated value** and drag it to the **THEN** pane's **Actions** label.</span></span>  
  
11. <span data-ttu-id="c6818-122">No painel **Atributos** , clique no atributo com o valor que você deseja gerar e arraste-o para o rótulo **Selecionar atributo** do painel **Editar Ação** .</span><span class="sxs-lookup"><span data-stu-id="c6818-122">In the **Attributes** pane, click the attribute with the value you want to generated and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="c6818-123">Digite um valor nas caixas **Iniciar com** e **Incrementar por** .</span><span class="sxs-lookup"><span data-stu-id="c6818-123">Type a value in the **Start with** and **Increment by** boxes.</span></span> <span data-ttu-id="c6818-124">Se os membros já existirem, o valor será definido com base no valor existente mais alto.</span><span class="sxs-lookup"><span data-stu-id="c6818-124">If members already exist, the value will be set based on the highest existing value.</span></span> <span data-ttu-id="c6818-125">Por exemplo, se o valor existente mais alto for 299 e você definir **Incrementar por** como **1**, o valor do próximo membro será definido como 300.</span><span class="sxs-lookup"><span data-stu-id="c6818-125">For example, if the highest existing value is 299 and you set **Increment by** to **1**, the next member's value will be set to 300.</span></span>  
  
13. <span data-ttu-id="c6818-126">No painel **Editar Ação** , clique em **Salvar item**.</span><span class="sxs-lookup"><span data-stu-id="c6818-126">In the **Edit Action** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="c6818-127">Clique em **Voltar**.</span><span class="sxs-lookup"><span data-stu-id="c6818-127">Click **Back**.</span></span>  
  
15. <span data-ttu-id="c6818-128">Opcionalmente, na página **Manutenção de Regra de Negócio** , na linha que contém sua regra de negócio, clique duas vezes em uma célula da coluna **Nome**, **Descrição**ou **Notificação** para atualizar o valor.</span><span class="sxs-lookup"><span data-stu-id="c6818-128">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
16. <span data-ttu-id="c6818-129">Clique em **Publicar regras de negócio**.</span><span class="sxs-lookup"><span data-stu-id="c6818-129">Click **Publish business rules**.</span></span>  
  
17. <span data-ttu-id="c6818-130">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6818-130">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="c6818-131">O status da regra mudará para **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="c6818-131">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c6818-132">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c6818-132">Next Steps</span></span>  
  
-   [<span data-ttu-id="c6818-133">Validar membros específicos em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c6818-133">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="c6818-134">Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c6818-134">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c6818-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6818-135">See Also</span></span>  
 <span data-ttu-id="c6818-136">[Criação de código automática &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c6818-136">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 <span data-ttu-id="c6818-137">[Regras de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c6818-137">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="c6818-138">Validação &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c6818-138">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
  
