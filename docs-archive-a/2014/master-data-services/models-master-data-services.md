---
title: Modelos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], about models
- models [Master Data Services]
ms.assetid: 9f862a3d-25ab-41e9-b833-1db99959e825
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d5a4a431d3ca7b6fa499de68a2bc4c5033cd086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583121"
---
# <a name="models-master-data-services"></a><span data-ttu-id="67fb1-102">Modelos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="67fb1-102">Models (Master Data Services)</span></span>
  <span data-ttu-id="67fb1-103">Modelos são o nível mais alto da organização de dados no [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67fb1-103">Models are the highest level of data organization in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="67fb1-104">Um modelo define a estrutura de dados em sua solução de gerenciamento de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="67fb1-104">A model defines the structure of data in your master data management solution.</span></span> <span data-ttu-id="67fb1-105">Um modelo contém os seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="67fb1-105">A model contains the following objects:</span></span>  
  
-   <span data-ttu-id="67fb1-106">Entidades</span><span class="sxs-lookup"><span data-stu-id="67fb1-106">Entities</span></span>  
  
-   <span data-ttu-id="67fb1-107">Atributos e grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="67fb1-107">Attributes and attribute groups</span></span>  
  
-   <span data-ttu-id="67fb1-108">Hierarquias derivadas e explícitas</span><span class="sxs-lookup"><span data-stu-id="67fb1-108">Explicit and derived hierarchies</span></span>  
  
-   <span data-ttu-id="67fb1-109">Coleções</span><span class="sxs-lookup"><span data-stu-id="67fb1-109">Collections</span></span>  
  
 <span data-ttu-id="67fb1-110">Os modelos organizam a estrutura de seus dados mestre.</span><span class="sxs-lookup"><span data-stu-id="67fb1-110">Models organize the structure of your master data.</span></span> <span data-ttu-id="67fb1-111">Sua implementação [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] pode ter um ou vários modelos nos quais cada um agrupa tipos semelhantes de dados.</span><span class="sxs-lookup"><span data-stu-id="67fb1-111">Your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] implementation can have one or many models that each group similar kinds of data.</span></span> <span data-ttu-id="67fb1-112">No geral, os dados mestres podem ser categorizados de uma das quatro maneiras: pessoas, locais, coisas ou conceitos.</span><span class="sxs-lookup"><span data-stu-id="67fb1-112">In general, master data can be categorized in one of four ways: people, places, things, or concepts.</span></span> <span data-ttu-id="67fb1-113">Por exemplo, você pode criar um modelo Product para conter dados relativos aos produtos ou um modelo Customer para conter dados relativos aos clientes.</span><span class="sxs-lookup"><span data-stu-id="67fb1-113">For example, you can create a Product model to contain product-related data or a Customer model to contain customer-related data.</span></span>  
  
 <span data-ttu-id="67fb1-114">Você pode atribuir aos usuários e grupos permissão para exibir e atualizar objetos dentro do modelo.</span><span class="sxs-lookup"><span data-stu-id="67fb1-114">You can assign users and groups permission to view and update objects within the model.</span></span> <span data-ttu-id="67fb1-115">Se você não der permissão ao modelo, ele não será exibido.</span><span class="sxs-lookup"><span data-stu-id="67fb1-115">If you do not give permission to the model, it is not displayed.</span></span>  
  
 <span data-ttu-id="67fb1-116">A qualquer momento, você pode criar cópias dos dados mestre dentro de um modelo.</span><span class="sxs-lookup"><span data-stu-id="67fb1-116">At any given time, you can create copies of the master data within a model.</span></span> <span data-ttu-id="67fb1-117">Essas cópias são chamadas de versões.</span><span class="sxs-lookup"><span data-stu-id="67fb1-117">These copies are called versions.</span></span>  
  
 <span data-ttu-id="67fb1-118">Quando você define um modelo em um ambiente de teste, pode implantá-lo, com ou sem os dados correspondentes, do ambiente de teste para um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="67fb1-118">When you have defined a model in a test environment, you can deploy it, with or without the corresponding data, from the test environment to a production environment.</span></span> <span data-ttu-id="67fb1-119">Isso elimina a necessidade de recriar seus modelos em seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="67fb1-119">This eliminates the need to recreate your models in your production environment.</span></span>  
  
## <a name="how-models-relate-to-other-objects"></a><span data-ttu-id="67fb1-120">Como os modelos se relacionam com outros objetos</span><span class="sxs-lookup"><span data-stu-id="67fb1-120">How Models Relate to Other Objects</span></span>  
 <span data-ttu-id="67fb1-121">Um modelo contém entidades.</span><span class="sxs-lookup"><span data-stu-id="67fb1-121">A model contains entities.</span></span> <span data-ttu-id="67fb1-122">Entidades contêm atributos, hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="67fb1-122">Entities contain attributes, explicit hierarchies, and collections.</span></span> <span data-ttu-id="67fb1-123">Atributos podem ser contidos em grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="67fb1-123">Attributes can be contained in attribute groups.</span></span> <span data-ttu-id="67fb1-124">Atributos baseados em domínio existem quando uma entidade é usada como um atributo para outra entidade.</span><span class="sxs-lookup"><span data-stu-id="67fb1-124">Domain-based attributes exist when an entity is used as an attribute for another entity.</span></span>  
  
 <span data-ttu-id="67fb1-125">Esta imagem mostra as relações entre os objetos em um modelo.</span><span class="sxs-lookup"><span data-stu-id="67fb1-125">This image shows the relationships among the objects in a model.</span></span>  
  
 <span data-ttu-id="67fb1-126">![Objetos em um modelo de Master Data Services](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objetos em um modelo de Master Data Services")</span><span class="sxs-lookup"><span data-stu-id="67fb1-126">![Objects in a Master Data Services Model](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objects in a Master Data Services Model")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67fb1-127">As hierarquias derivadas também são objetos de modelo, mas elas não são mostradas na imagem.</span><span class="sxs-lookup"><span data-stu-id="67fb1-127">Derived hierarchies are also model objects, but they are not shown in the image.</span></span> <span data-ttu-id="67fb1-128">As hierarquias derivadas são derivadas de relações de atributos baseados em domínio que existem entre entidades.</span><span class="sxs-lookup"><span data-stu-id="67fb1-128">Derived hierarchies are derived from the domain-based attribute relationships that exist between entities.</span></span> <span data-ttu-id="67fb1-129">Consulte [Hierarquias derivadas &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="67fb1-129">See [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) for more information.</span></span>  
  
 <span data-ttu-id="67fb1-130">Os dados mestres são os dados contidos nos objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="67fb1-130">Master data is the data that is contained in the model objects.</span></span> <span data-ttu-id="67fb1-131">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], os dados mestres são armazenados como membros em uma entidade.</span><span class="sxs-lookup"><span data-stu-id="67fb1-131">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], master data is stored as members in an entity.</span></span>  
  
 <span data-ttu-id="67fb1-132">Objetos de modelo são mantidos na área funcional **Administração do Sistema** da interface de usuário do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67fb1-132">Model objects are maintained in the **System Administration** functional area of the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface.</span></span>  
  
## <a name="model-example"></a><span data-ttu-id="67fb1-133">Exemplo de modelo</span><span class="sxs-lookup"><span data-stu-id="67fb1-133">Model Example</span></span>  
 <span data-ttu-id="67fb1-134">No exemplo a seguir, os objetos no modelo Product agrupam logicamente os dados relativos aos produtos.</span><span class="sxs-lookup"><span data-stu-id="67fb1-134">In the following example, the objects in the Product model logically group product-related data.</span></span>  
  
 <span data-ttu-id="67fb1-135">![Exemplo de dados mestre de modelo de produto](../../2014/master-data-services/media/mds-conc-model.gif "Exemplo de dados mestre de modelo de produto")</span><span class="sxs-lookup"><span data-stu-id="67fb1-135">![Product Model Master Data Example](../../2014/master-data-services/media/mds-conc-model.gif "Product Model Master Data Example")</span></span>  
  
 <span data-ttu-id="67fb1-136">Outros modelos comuns são:</span><span class="sxs-lookup"><span data-stu-id="67fb1-136">Other common models are:</span></span>  
  
-   <span data-ttu-id="67fb1-137">Contas, que podem incluir entidades tais como contas de demonstração financeira, contas de demonstrativo de renda, estatísticas e tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="67fb1-137">Accounts, which could include entities such as balance sheet accounts, income statement accounts, statistics, and account type.</span></span>  
  
-   <span data-ttu-id="67fb1-138">Cliente, que pode incluir entidades tais como gênero, educação, ocupação e estado civil.</span><span class="sxs-lookup"><span data-stu-id="67fb1-138">Customer, which could include entities such as gender, education, occupation, and marital status.</span></span>  
  
-   <span data-ttu-id="67fb1-139">Geografia, que pode incluir entidades tais como códigos postais, cidades, municípios, estados, províncias, regiões, territórios, países e continentes.</span><span class="sxs-lookup"><span data-stu-id="67fb1-139">Geography, which could include entities such as postal codes, cities, counties, states, provinces, regions, territories, countries, and continents.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="67fb1-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="67fb1-140">Related Tasks</span></span>  
  
|<span data-ttu-id="67fb1-141">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="67fb1-141">Task Description</span></span>|<span data-ttu-id="67fb1-142">Tópico</span><span class="sxs-lookup"><span data-stu-id="67fb1-142">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="67fb1-143">Criar um modelo para organizar seus dados mestre.</span><span class="sxs-lookup"><span data-stu-id="67fb1-143">Create a model to organize your master data.</span></span>|[<span data-ttu-id="67fb1-144">Criar um modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67fb1-144">Create a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-master-data-services.md)|  
|<span data-ttu-id="67fb1-145">Alterar o nome de um modelo existente.</span><span class="sxs-lookup"><span data-stu-id="67fb1-145">Change the name of an existing model.</span></span>|[<span data-ttu-id="67fb1-146">Alterar um nome de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67fb1-146">Change a Model Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-model-name-master-data-services.md)|  
|<span data-ttu-id="67fb1-147">Excluir um modelo existente.</span><span class="sxs-lookup"><span data-stu-id="67fb1-147">Delete an existing model.</span></span>|[<span data-ttu-id="67fb1-148">Excluir um modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67fb1-148">Delete a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-model-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="67fb1-149">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="67fb1-149">Related Content</span></span>  
  
-   [<span data-ttu-id="67fb1-150">Visão geral de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="67fb1-150">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
-   [<span data-ttu-id="67fb1-151">Entidades &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67fb1-151">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)  
  
-   [<span data-ttu-id="67fb1-152">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67fb1-152">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
-   [<span data-ttu-id="67fb1-153">Implantando modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67fb1-153">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
-   [<span data-ttu-id="67fb1-154">Permissões de objeto de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="67fb1-154">Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/model-object-permissions-master-data-services.md)  
  
  
