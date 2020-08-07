---
title: Hierarquias recursivas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- recursive hierarchies [Master Data Services]
- hierarchies [Master Data Services], recursive hierarchies
ms.assetid: 9408c6ea-d9c4-4a0b-8a1b-1457fb6944af
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3c149d500ce1499ad36247d5e32bb6f2d55b4250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582484"
---
# <a name="recursive-hierarchies-master-data-services"></a><span data-ttu-id="0862b-102">Hierarquias recursivas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0862b-102">Recursive Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="0862b-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], uma hierarquia recursiva é uma hierarquia derivada que inclui uma relação recursiva.</span><span class="sxs-lookup"><span data-stu-id="0862b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a recursive hierarchy is a derived hierarchy that includes a recursive relationship.</span></span> <span data-ttu-id="0862b-104">Uma relação recursiva existe quando uma entidade tem um atributo baseado em domínio com base na própria entidade.</span><span class="sxs-lookup"><span data-stu-id="0862b-104">A recursive relationship exists when an entity has a domain-based attribute based on the entity itself.</span></span>

## <a name="recursive-hierarchy-example"></a><span data-ttu-id="0862b-105">Exemplo de hierarquia recursiva</span><span class="sxs-lookup"><span data-stu-id="0862b-105">Recursive Hierarchy Example</span></span>
 <span data-ttu-id="0862b-106">Um exemplo típico de hierarquia recursiva é uma estrutura organizacional.</span><span class="sxs-lookup"><span data-stu-id="0862b-106">A typical recursive hierarchy example is an organizational structure.</span></span> <span data-ttu-id="0862b-107">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], você pode fazer isso criando uma entidade Funcionário com um atributo baseado em domínio chamado Gerente.</span><span class="sxs-lookup"><span data-stu-id="0862b-107">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you would do this by creating an Employee entity with a domain-based attribute called Manager.</span></span> <span data-ttu-id="0862b-108">O atributo Gerente é populado da lista de funcionários.</span><span class="sxs-lookup"><span data-stu-id="0862b-108">The Manager attribute is populated from the list of employees.</span></span> <span data-ttu-id="0862b-109">Nesta organização de exemplo, todos os funcionários podem ser gerentes.</span><span class="sxs-lookup"><span data-stu-id="0862b-109">In this sample organization, all employees can be managers.</span></span>

 <span data-ttu-id="0862b-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span><span class="sxs-lookup"><span data-stu-id="0862b-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span></span>

 <span data-ttu-id="0862b-111">Você pode criar uma hierarquia derivada que destaca a relação entre a entidade Funcionário e o atributo Gerente baseado em domínio.</span><span class="sxs-lookup"><span data-stu-id="0862b-111">You can create a derived hierarchy that highlights the relationship between the Employee entity and the Manager domain-based attribute.</span></span>

 <span data-ttu-id="0862b-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="0862b-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span></span>

 <span data-ttu-id="0862b-113">Para incluir cada membro na hierarquia apenas uma vez, você pode ancorar relações nulas.</span><span class="sxs-lookup"><span data-stu-id="0862b-113">To include each member in the hierarchy only once, you can anchor null relationships.</span></span> <span data-ttu-id="0862b-114">Quando você fizer isso, os membros com valores de atributo baseado em domínio em branco serão exibidos no nível superior da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="0862b-114">When you do, members with blank domain-based attribute values are displayed at the top level of the hierarchy.</span></span>

 <span data-ttu-id="0862b-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span><span class="sxs-lookup"><span data-stu-id="0862b-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span></span>

 <span data-ttu-id="0862b-116">Se você não ancorar relações nulas, os membros serão incluídos várias vezes.</span><span class="sxs-lookup"><span data-stu-id="0862b-116">If you do not anchor null relationships, members are included multiple times.</span></span> <span data-ttu-id="0862b-117">Todos os membros são exibidos no nível superior.</span><span class="sxs-lookup"><span data-stu-id="0862b-117">All members are displayed at the top level.</span></span> <span data-ttu-id="0862b-118">Eles também são exibidos sob membros dos quais eles são atributos.</span><span class="sxs-lookup"><span data-stu-id="0862b-118">They are also displayed under members of which they are attributes.</span></span>

 <span data-ttu-id="0862b-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span><span class="sxs-lookup"><span data-stu-id="0862b-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span></span>

 <span data-ttu-id="0862b-120">Neste exemplo, Marcia está no nível superior.</span><span class="sxs-lookup"><span data-stu-id="0862b-120">In this example, Marcia is at the top level.</span></span> <span data-ttu-id="0862b-121">Ela não é gerente de nenhum funcionário porque não é usada como um valor de atributo baseado em domínio para qualquer outro Funcionário membro.</span><span class="sxs-lookup"><span data-stu-id="0862b-121">She is not the manager of any employees because she is not used as a domain-based attribute value for any other Employee members.</span></span> <span data-ttu-id="0862b-122">Por outro lado, Robert tem um nível abaixo dele porque Marcia tem Robert como seu valor de atributo de Gerente.</span><span class="sxs-lookup"><span data-stu-id="0862b-122">Robert, in contrast, has a level beneath him because Marcia has Robert as her Manager attribute value.</span></span>

## <a name="rules"></a><span data-ttu-id="0862b-123">Regras</span><span class="sxs-lookup"><span data-stu-id="0862b-123">Rules</span></span>

-   <span data-ttu-id="0862b-124">Uma hierarquia derivada não pode conter mais de uma relação recursiva.</span><span class="sxs-lookup"><span data-stu-id="0862b-124">A derived hierarchy cannot contain more than one recursive relationship.</span></span> <span data-ttu-id="0862b-125">Entretanto, ela pode ter outras relações derivadas (por exemplo, uma hierarquia derivada que contém uma relação recursiva Gerenciador para Funcionário também pode ter relações País para Gerenciador e Funcionário para Repositório).</span><span class="sxs-lookup"><span data-stu-id="0862b-125">It can, however, have other derived relationships (for example, a derived hierarchy that contains a recursive Manager to Employee relationship can also have Country to Manager and Employee to Store relationships).</span></span>

-   <span data-ttu-id="0862b-126">Você não pode atribuir permissões (na guia **Membros da Hierarquia** ) a membros de uma hierarquia recursiva.</span><span class="sxs-lookup"><span data-stu-id="0862b-126">You cannot assign member permissions (on the **Hierarchy Members** tab) to members in a recursive hierarchy.</span></span>

-   <span data-ttu-id="0862b-127">Hierarquias recursivas não podem incluir relações circulares.</span><span class="sxs-lookup"><span data-stu-id="0862b-127">Recursive hierarchies cannot include circular relationships.</span></span> <span data-ttu-id="0862b-128">Por exemplo, Katherine não poderá ser o gerente de Sandeep se Sandeep for o gerente dela.</span><span class="sxs-lookup"><span data-stu-id="0862b-128">For example, Katherine cannot be Sandeep's manager if Sandeep is her manager.</span></span> <span data-ttu-id="0862b-129">Katherine também não pode ser gerente de si mesma.</span><span class="sxs-lookup"><span data-stu-id="0862b-129">Also, Katherine cannot manage herself.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="0862b-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0862b-130">Related Tasks</span></span>

|<span data-ttu-id="0862b-131">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="0862b-131">Task Description</span></span>|<span data-ttu-id="0862b-132">Tópico</span><span class="sxs-lookup"><span data-stu-id="0862b-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="0862b-133">Criar uma hierarquia derivada.</span><span class="sxs-lookup"><span data-stu-id="0862b-133">Create a derived hierarchy.</span></span>|[<span data-ttu-id="0862b-134">Criar uma hierarquia derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0862b-134">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="0862b-135">Alterar o nome de uma hierarquia derivada existente.</span><span class="sxs-lookup"><span data-stu-id="0862b-135">Change the name of an existing derived hierarchy.</span></span>|[<span data-ttu-id="0862b-136">Alterar o nome de uma hierarquia derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0862b-136">Change a Derived Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-derived-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="0862b-137">Excluir uma hierarquia derivada existente.</span><span class="sxs-lookup"><span data-stu-id="0862b-137">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="0862b-138">Excluir uma hierarquia derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0862b-138">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="0862b-139">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="0862b-139">Related Content</span></span>

-   [<span data-ttu-id="0862b-140">Atributos baseados em domínio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0862b-140">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)

-   [<span data-ttu-id="0862b-141">Hierarquias derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0862b-141">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)


