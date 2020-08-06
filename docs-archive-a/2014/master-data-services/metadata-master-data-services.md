---
title: Metadados (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined metadata [Master Data Services], about user-defined metadata
- metadata [Master Data Services], about metadata
- metadata [Master Data Services]
- user-defined metadata [Master Data Services]
ms.assetid: ac1aabe3-d8d4-4d7a-8954-50ee3c185d81
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 39ab95b7925306febb551962495da7ec9751589b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680021"
---
# <a name="metadata-master-data-services"></a><span data-ttu-id="41153-102">Metadados (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="41153-102">Metadata (Master Data Services)</span></span>
  <span data-ttu-id="41153-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], metadados definidos pelo usuário são informações usadas para descrever objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="41153-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], user-defined metadata is information that you use to describe model objects.</span></span> <span data-ttu-id="41153-104">Por exemplo, você pode acompanhar os proprietários de um modelo ou entidade específicos ou acompanhar os sistemas de origem que fornecem dados a uma entidade.</span><span class="sxs-lookup"><span data-stu-id="41153-104">For example, you may want to track the owners of a particular model or entity, or track the source systems that supply data to an entity.</span></span>  
  
 <span data-ttu-id="41153-105">Os metadados definidos pelo usuário são gerenciados por um modelo chamado **metadados**.</span><span class="sxs-lookup"><span data-stu-id="41153-105">User-defined metadata is managed by a model called **Metadata**.</span></span> <span data-ttu-id="41153-106">Esse modelo é incluído automaticamente quando o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] é instalado e é semelhante a todos os outros modelos do MDS, exceto pelo fato de que você não pode criar versões dele.</span><span class="sxs-lookup"><span data-stu-id="41153-106">This model is automatically included when [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed, and it is similar to all other MDS models, except that you cannot create versions of it.</span></span>  
  
 <span data-ttu-id="41153-107">Depois de popular o modelo de Metadados com metadados definidos pelo usuário, você pode incluí-lo em exibições de assinatura para que seja consumido por sistemas assinantes.</span><span class="sxs-lookup"><span data-stu-id="41153-107">After you populate the Metadata model with user-defined metadata, you can include it in subscription views, so it can be consumed by subscribing systems.</span></span>  
  
## <a name="metadata-entities"></a><span data-ttu-id="41153-108">Entidades de metadados</span><span class="sxs-lookup"><span data-stu-id="41153-108">Metadata Entities</span></span>  
 <span data-ttu-id="41153-109">O modelo Metadados inclui cinco entidades, cada uma representando um tipo de objeto de modelo de dados mestres que oferece suporte a metadados definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="41153-109">The Metadata model includes five entities, each of which represents a type of master data model object that supports user-defined metadata.</span></span> <span data-ttu-id="41153-110">Por exemplo, a entidade **modelo de definição de metadados** contém membros que representam modelos e a entidade de definição de metadados de **atributo** tem membros que representam todos os atributos em todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="41153-110">For example, the **Model Metadata Definition** entity contains members that represent models, and the **Attribute Metadata Definition** entity has members that represent all attributes in all models.</span></span>  
  
 <span data-ttu-id="41153-111">Para definir metadados para um objeto de modelo, popule um destes atributos de membro.</span><span class="sxs-lookup"><span data-stu-id="41153-111">To define metadata for a model object, you populate one of these member's attributes.</span></span> <span data-ttu-id="41153-112">Por exemplo, na entidade de **definição de metadados de entidade** , você pode preencher o atributo de descrição do membro de preço com o texto: **o preço do produto quando vendido a um cliente**.</span><span class="sxs-lookup"><span data-stu-id="41153-112">For example, in the **Entity Metadata Definition** entity, you can populate the Price member's Description attribute with the text: **The product price when sold to a customer**.</span></span>  
  
 <span data-ttu-id="41153-113">Os membros do modelo Metadados são atualizados automaticamente sempre que objetos de modelo que oferecem suporte a metadados definidos pelo usuário são adicionados ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="41153-113">The members in the Metadata model are automatically updated whenever model objects that support user-defined metadata are added or deleted.</span></span>  
  
 <span data-ttu-id="41153-114">O modelo de Metadados não pode ter controle de versão, ter sinalizadores de versão adicionados ou alterados, nem ser salvo como um pacote de implantação de modelo.</span><span class="sxs-lookup"><span data-stu-id="41153-114">The Metadata model cannot be versioned, have version flags added or changed, or be saved as a model deployment package.</span></span> <span data-ttu-id="41153-115">No entanto, ele tem as mesmas outras funcionalidades disponíveis para outros modelos de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="41153-115">However, it has all the same other functionality available to other master data models.</span></span> <span data-ttu-id="41153-116">Por exemplo, você pode implementar um conjunto de regras de negócio no modelo de Metadados para impor políticas de dados.</span><span class="sxs-lookup"><span data-stu-id="41153-116">For example, you might implement a set of business rules on the Metadata model to enforce data policies.</span></span>  
  
## <a name="customizing-your-metadata-model"></a><span data-ttu-id="41153-117">Personalizando seu modelo de metadados</span><span class="sxs-lookup"><span data-stu-id="41153-117">Customizing Your Metadata Model</span></span>  
 <span data-ttu-id="41153-118">Cada entidade de definição de metadados inclui os atributos Nome, Código e Descrição.</span><span class="sxs-lookup"><span data-stu-id="41153-118">Each metadata definition entity includes Name, Code, and Description attributes.</span></span> <span data-ttu-id="41153-119">Você pode criar atributos adicionais para mais descrever seus objetos de modelo com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="41153-119">You may want to create additional attributes to further describe your model objects.</span></span>  
  
 <span data-ttu-id="41153-120">Por exemplo, você pode criar:</span><span class="sxs-lookup"><span data-stu-id="41153-120">For example, you might create:</span></span>  
  
-   <span data-ttu-id="41153-121">Um atributo baseado em domínio chamado Proprietário, que você usa para acompanhar o proprietário de cada objeto de modelo.</span><span class="sxs-lookup"><span data-stu-id="41153-121">A domain-based attribute named Owner, which you use to track the owner of each model object.</span></span>  
  
-   <span data-ttu-id="41153-122">Um atributo de forma livre chamado Data da Última Revisão, que você usa para acompanhar a data que um objeto foi revisado pela última vez pelo proprietário.</span><span class="sxs-lookup"><span data-stu-id="41153-122">A free-form attribute named Last Review Date, which you use to track the date that an object was last reviewed by the owner.</span></span>  
  
-   <span data-ttu-id="41153-123">Um atributo baseado em domínio chamado fontes, que você usa para acompanhar e gerenciar os sistemas de origem que interagem com a [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instância do.</span><span class="sxs-lookup"><span data-stu-id="41153-123">A domain-based attribute named Sources, which you use to track and manage the source systems that interact with the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instance.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="41153-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="41153-124">Related Tasks</span></span>  
  
|<span data-ttu-id="41153-125">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="41153-125">Task Description</span></span>|<span data-ttu-id="41153-126">Tópico</span><span class="sxs-lookup"><span data-stu-id="41153-126">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="41153-127">Adicionar metadados a um objeto de modelo.</span><span class="sxs-lookup"><span data-stu-id="41153-127">Add metadata to a model object.</span></span>|[<span data-ttu-id="41153-128">Adicionar metadados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="41153-128">Add Metadata &#40;Master Data Services&#41;</span></span>](add-metadata-master-data-services.md)
|&nbsp;|&nbsp;|
  
## <a name="related-content"></a><span data-ttu-id="41153-129">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="41153-129">Related Content</span></span>  
  
-   [<span data-ttu-id="41153-130">Exportando dados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="41153-130">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
