---
title: Criar um atributo baseado em domínio (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 7b3e30dc-8f41-4a5d-8009-ae5a4426a64b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bda0c7f63ad380aaea5d980d2e729822ec9a3d22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568677"
---
# <a name="create-a-domain-based-attribute-mds-add-in-for-excel"></a><span data-ttu-id="5147e-102">Criar um atributo baseado em domínio (Suplemento do MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="5147e-102">Create a Domain-based Attribute (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="5147e-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], os administradores podem criar um atributo baseado em domínio quando desejarem restringir os valores em uma coluna a um conjunto específico de valores.</span><span class="sxs-lookup"><span data-stu-id="5147e-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create a domain-based attribute when they want to constrain the values in a column to a specific set of values.</span></span>  
  
 <span data-ttu-id="5147e-104">Os valores já podem estar na planilha ou podem vir de uma entidade existente.</span><span class="sxs-lookup"><span data-stu-id="5147e-104">The values can already be in the worksheet or they can come from an existing entity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5147e-105"> Se os usuários digitarem um valor na coluna restrita, em vez de selecionar na lista, serão exibidos erros na coluna **$ InputStatus $** quando eles publicarem.</span><span class="sxs-lookup"><span data-stu-id="5147e-105">If users type a value in the constrained column, rather than selecting from the list, errors are displayed in the **$InputStatus$** column when they publish.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5147e-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5147e-106">Prerequisites</span></span>  
 <span data-ttu-id="5147e-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="5147e-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5147e-108">Você precisa ter permissão para acessar as áreas funcionais **Administração do Sistema** e **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="5147e-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="5147e-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="5147e-109">You must be a model administrator.</span></span> <span data-ttu-id="5147e-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5147e-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="5147e-111">O modelo e a entidade já devem existir.</span><span class="sxs-lookup"><span data-stu-id="5147e-111">The model and entity must already exist.</span></span>  
  
### <a name="to-perform-this-procedure"></a><span data-ttu-id="5147e-112">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="5147e-112">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="5147e-113">No Excel, carregue a entidade que contém a coluna (atributo) a ser restringida.</span><span class="sxs-lookup"><span data-stu-id="5147e-113">In Excel, load the entity that contains the column (attribute) you want to constrain.</span></span> <span data-ttu-id="5147e-114">Para obter mais informações, consulte [carregar dados do MDS para o Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5147e-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="5147e-115">Clique em qualquer célula da coluna que você deseja restringir.</span><span class="sxs-lookup"><span data-stu-id="5147e-115">Click any cell in the column you want to constrain.</span></span>  
  
3.  <span data-ttu-id="5147e-116">No grupo **Compilar Modelo** , clique em **Propriedades do Atributo**.</span><span class="sxs-lookup"><span data-stu-id="5147e-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="5147e-117">Na caixa de diálogo **Propriedades de Atributo** , na lista **Tipo de atributo** , escolha **Lista restrita (baseada em domínio)**.</span><span class="sxs-lookup"><span data-stu-id="5147e-117">In the **Attribute Properties** dialog box, in the **Attribute type** list, choose **Constrained list (domain-based)**.</span></span>  
  
5.  <span data-ttu-id="5147e-118">Na lista **Popular o atributo com valores de** :</span><span class="sxs-lookup"><span data-stu-id="5147e-118">In the **Populate the attribute with values from** list:</span></span>  
  
    -   <span data-ttu-id="5147e-119">Para usar valores da planilha, escolha **a coluna selecionada**.</span><span class="sxs-lookup"><span data-stu-id="5147e-119">To use values from the worksheet, choose **the selected column**.</span></span> <span data-ttu-id="5147e-120">Serão criadas uma nova entidade e uma nova tabela de preparo com os valores da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="5147e-120">A new entity and new staging table will be created with the values from the selected column.</span></span>  
  
    -   <span data-ttu-id="5147e-121">Para usar valores de uma entidade existente, escolha o nome da entidade.</span><span class="sxs-lookup"><span data-stu-id="5147e-121">To use values from an existing entity, choose the name of the entity.</span></span>  
  
6.  <span data-ttu-id="5147e-122">Se você escolheu **a coluna selecionada** na etapa anterior, na caixa **Novo nome da entidade** , digite um nome para a nova entidade.</span><span class="sxs-lookup"><span data-stu-id="5147e-122">If you chose **the selected column** in the previous step, in the **New entity name** box, type a name for the new entity.</span></span> <span data-ttu-id="5147e-123">Esse pode ser igual ao nome da coluna (atributo).</span><span class="sxs-lookup"><span data-stu-id="5147e-123">This can be the same as the column (attribute) name.</span></span>  
  
7.  <span data-ttu-id="5147e-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5147e-124">Click **OK**.</span></span> <span data-ttu-id="5147e-125">Agora, cada célula na coluna tem uma lista de valores que os usuários podem escolher.</span><span class="sxs-lookup"><span data-stu-id="5147e-125">Each cell in the column now has a list of values for users to choose from.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5147e-126">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5147e-126">Next Steps</span></span>  
  
-   <span data-ttu-id="5147e-127">Para adicionar e excluir valores na lista restrita, carregue a entidade na qual o atributo se baseia.</span><span class="sxs-lookup"><span data-stu-id="5147e-127">To add and delete values in the constrained list, load the entity that the attribute is based on.</span></span> <span data-ttu-id="5147e-128">Para obter mais informações sobre como carregar entidades, consulte [carregar dados do MDS para o Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5147e-128">For more information on loading entities, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5147e-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5147e-129">See Also</span></span>  
 <span data-ttu-id="5147e-130">[Atributos baseados em domínio &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5147e-130">[Domain-Based Attributes &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="5147e-131">[Criar uma entidade &#40;Suplemento MDS para Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="5147e-131">[Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="5147e-132">Criando um modelo &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5147e-132">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
