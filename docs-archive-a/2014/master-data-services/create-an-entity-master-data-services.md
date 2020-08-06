---
title: Criar uma entidade (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], creating
- creating entities [Master Data Services]
ms.assetid: d9a6a51e-7b53-4785-a118-3baeb7ca2d48
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7cefdedd07ee248f12b3b17337878934a2b1aa84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583135"
---
# <a name="create-an-entity-master-data-services"></a><span data-ttu-id="2220f-102">Criar uma entidade (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2220f-102">Create an Entity (Master Data Services)</span></span>
  <span data-ttu-id="2220f-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], crie uma entidade para conter os membros e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="2220f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an entity to contain members and their attributes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2220f-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2220f-104">Prerequisites</span></span>  
 <span data-ttu-id="2220f-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="2220f-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2220f-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="2220f-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="2220f-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="2220f-107">You must be a model administrator.</span></span> <span data-ttu-id="2220f-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2220f-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="2220f-109">Deve existir um modelo.</span><span class="sxs-lookup"><span data-stu-id="2220f-109">A model must exist.</span></span> <span data-ttu-id="2220f-110">Para obter mais informações, consulte [Criar um modelo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2220f-110">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-an-entity"></a><span data-ttu-id="2220f-111">Para criar uma entidade</span><span class="sxs-lookup"><span data-stu-id="2220f-111">To create an entity</span></span>  
  
1.  <span data-ttu-id="2220f-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="2220f-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="2220f-113">Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="2220f-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="2220f-114">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="2220f-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="2220f-115">Clique em **Adicionar entidade**.</span><span class="sxs-lookup"><span data-stu-id="2220f-115">Click **Add entity**.</span></span>  
  
5.  <span data-ttu-id="2220f-116">Na caixa **nome da entidade** , digite o nome da entidade.</span><span class="sxs-lookup"><span data-stu-id="2220f-116">In the **Entity name** box, type the name of the entity.</span></span>  
  
6.  <span data-ttu-id="2220f-117">Na caixa **nome para tabelas de preparo** , digite um nome para a tabela de preparo.</span><span class="sxs-lookup"><span data-stu-id="2220f-117">In the **Name for staging tables** box, type a name for the staging table.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="2220f-118">Use o nome do modelo como parte do nome da tabela de preparo, por exemplo, *Modelname_Entityname*.</span><span class="sxs-lookup"><span data-stu-id="2220f-118">Use the model name as part of the staging table name, for example *Modelname_Entityname*.</span></span> <span data-ttu-id="2220f-119">Isto facilita a localização das tabelas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2220f-119">This makes the tables easier to find in the database.</span></span> <span data-ttu-id="2220f-120">Para obter mais informações sobre as tabelas de preparo, consulte [&#40;de importação de dados Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2220f-120">For more information about the staging tables, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
7.  <span data-ttu-id="2220f-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2220f-121">Optional.</span></span> <span data-ttu-id="2220f-122">Marque a caixa de seleção **Criar valores de códigos automaticamente** .</span><span class="sxs-lookup"><span data-stu-id="2220f-122">Select the **Create Code values automatically** check box.</span></span> <span data-ttu-id="2220f-123">Para obter mais informações, consulte [criação automática de código &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2220f-123">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="2220f-124">Na lista **habilitar hierarquias explícitas e coleções** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="2220f-124">From the **Enable explicit hierarchies and collections** list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="2220f-125">**Não**.</span><span class="sxs-lookup"><span data-stu-id="2220f-125">**No**.</span></span> <span data-ttu-id="2220f-126">Selecione essa opção se não precisar habilitar a entidade para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="2220f-126">Select this option if you do not need to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="2220f-127">É possível alterar isso mais tarde se necessário.</span><span class="sxs-lookup"><span data-stu-id="2220f-127">You can change this later if needed.</span></span>  
  
    -   <span data-ttu-id="2220f-128">**Sim**.</span><span class="sxs-lookup"><span data-stu-id="2220f-128">**Yes**.</span></span> <span data-ttu-id="2220f-129">Selecione essa opção quando desejar habilitar a entidade para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="2220f-129">Select this option when you want to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="2220f-130">Na caixa **nome da hierarquia explícita** , digite um nome.</span><span class="sxs-lookup"><span data-stu-id="2220f-130">In the **Explicit hierarchy name** box, type a name.</span></span> <span data-ttu-id="2220f-131">Opcionalmente, selecione **hierarquia obrigatória (todos os membros folha são incluídos** para tornar a hierarquia explícita uma hierarquia obrigatória.</span><span class="sxs-lookup"><span data-stu-id="2220f-131">Optionally, select **Mandatory hierarchy (all leaf members are included** to make the explicit hierarchy a mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="2220f-132">Clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="2220f-132">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2220f-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2220f-133">Next Steps</span></span>  
  
-   [<span data-ttu-id="2220f-134">Criar um atributo de texto &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2220f-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="2220f-135">Criar um atributo baseado em domínio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2220f-135">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="2220f-136">Criar um atributo de arquivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2220f-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2220f-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2220f-137">See Also</span></span>  
 <span data-ttu-id="2220f-138">[Entidades &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2220f-138">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="2220f-139">[Hierarquias explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2220f-139">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="2220f-140">[Alterar um nome de entidade &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2220f-140">[Change an Entity Name &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span></span>  
 [<span data-ttu-id="2220f-141">Excluir uma entidade &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2220f-141">Delete an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-entity-master-data-services.md)  
  
  
