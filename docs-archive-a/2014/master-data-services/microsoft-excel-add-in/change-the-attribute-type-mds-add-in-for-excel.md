---
title: Alterar o tipo de atributo (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9d3001d9-8d0f-4e4a-8e04-4f666bf0df69
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a55ca53fcf6923957e2196840aea2fb5914e1746
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680016"
---
# <a name="change-the-attribute-type-mds-add-in-for-excel"></a><span data-ttu-id="22444-102">Alterar o tipo de atributo (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="22444-102">Change the Attribute Type (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="22444-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], os administradores podem alterar o tipo de atributo quando o tipo de dados ou número de caracteres permitido está incorreto.</span><span class="sxs-lookup"><span data-stu-id="22444-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can change the attribute type when the data type or number of allowed characters is incorrect.</span></span>  
  
 <span data-ttu-id="22444-104">Se você quiser alterar o tipo de atributo para criar uma lista restrita (atributo baseado em domínio), consulte [Criar um atributo baseado em domínio &#40;Suplemento MDS para Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="22444-104">If you want to change the attribute type to create a constrained list (domain-based attribute), see [Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22444-105">Não é possível atualizar o tipo ou o tamanho da coluna **Nome** ou **Código**.</span><span class="sxs-lookup"><span data-stu-id="22444-105">You cannot update the type or length of the **Name** or **Code** columns.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="22444-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="22444-106">Prerequisites</span></span>  
 <span data-ttu-id="22444-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="22444-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="22444-108">Você precisa ter permissão para acessar as áreas funcionais **Administração do Sistema** e **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="22444-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="22444-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="22444-109">You must be a model administrator.</span></span> <span data-ttu-id="22444-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="22444-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="22444-111">Deve haver um modelo, entidade e atributo existente.</span><span class="sxs-lookup"><span data-stu-id="22444-111">There must be an existing model, entity, and attribute.</span></span>  
  
### <a name="to-change-the-attribute-type"></a><span data-ttu-id="22444-112">Para alterar o tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="22444-112">To change the attribute type</span></span>  
  
1.  <span data-ttu-id="22444-113">No Excel, carregue a entidade que contém a coluna (atributo) a ser alterada.</span><span class="sxs-lookup"><span data-stu-id="22444-113">In Excel, load the entity that contains the column (attribute) you want to change.</span></span> <span data-ttu-id="22444-114">Para obter mais informações, consulte [carregar dados do MDS para o Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="22444-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="22444-115">Clique em qualquer célula da coluna que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="22444-115">Click any cell in the column you want to change.</span></span>  
  
3.  <span data-ttu-id="22444-116">No grupo **Compilar Modelo** , clique em **Propriedades do Atributo**.</span><span class="sxs-lookup"><span data-stu-id="22444-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="22444-117">Na caixa de diálogo **Propriedades do Atributo** , é necessário atualizar as configurações.</span><span class="sxs-lookup"><span data-stu-id="22444-117">In the **Attribute Properties** dialog box, update settings as needed.</span></span>  
  
5.  <span data-ttu-id="22444-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="22444-118">Click **OK**.</span></span>  
  
## <a name="what-happens-when-you-change-the-attribute-type"></a><span data-ttu-id="22444-119">O que acontece quando você altera o tipo de atributo?</span><span class="sxs-lookup"><span data-stu-id="22444-119">What happens when you change the attribute type?</span></span>  
 <span data-ttu-id="22444-120">Se houver qualquer dependência no atributo, por exemplo, o atributo ser referenciado por qualquer regra de negócio do MDS ou o atributo ser incluído em uma exibição de assinatura, e você alterar o tipo de dados de um atributo, o MD irá:</span><span class="sxs-lookup"><span data-stu-id="22444-120">If there is any dependency on the attribute, such as the attribute is referenced by any MDS business rule or the attribute is included in a subscription view, and you change the data type of an attribute, MDS will:</span></span>  
  
-   <span data-ttu-id="22444-121">Alterar o tipo de dados do atributo.</span><span class="sxs-lookup"><span data-stu-id="22444-121">Change the data type of the attribute.</span></span>  
  
-   <span data-ttu-id="22444-122">Gere uma cópia do atributo com o sufixo "_old" que não contenha nenhum valor.</span><span class="sxs-lookup"><span data-stu-id="22444-122">Generate a copy of the attribute with the suffix "_old" that does not contain any value.</span></span> <span data-ttu-id="22444-123">Isso é chamado de atributo **preterido** .</span><span class="sxs-lookup"><span data-stu-id="22444-123">This is called a **deprecated** attribute.</span></span>  
  
 <span data-ttu-id="22444-124">Porém, todas as dependências existentes no atributo original apontarão para o atributo substituído, e não para o alterado.</span><span class="sxs-lookup"><span data-stu-id="22444-124">However, all the existing dependencies on the original attribute will point to the deprecated attribute, and not to the changed one.</span></span>  
  
 <span data-ttu-id="22444-125">Isso significa que:</span><span class="sxs-lookup"><span data-stu-id="22444-125">This implies that:</span></span>  
  
-   <span data-ttu-id="22444-126">Você deve atualizar as regras de negócio para apontar para o atributo alterado porque a lógica pode não ser a mesma considerando o novo tipo de dados do atributo.</span><span class="sxs-lookup"><span data-stu-id="22444-126">You must refresh the business rules to point to the changed attribute because the logic may not be the same given the new data type of the attribute.</span></span> <span data-ttu-id="22444-127">Será necessário editar cada regra afetada e, em seguida, retrabalhar as expressões para apontar para remover as referências do atributo substituído (_old) para apontar para o atributo atualizado.</span><span class="sxs-lookup"><span data-stu-id="22444-127">You will have to edit each affected rule, and then rework the expressions to point to remove references from the deprecated attribute (_old) to point to the updated attribute.</span></span>  
  
-   <span data-ttu-id="22444-128">Você deve abrir as exibições de assinatura na seleção de gerenciamento de integração, selecionar a linha de exibição, abri-la para edição clicando no ícone de lápis e, em seguida, no ícone **salvar disco** para atualizar a definição da exibição.</span><span class="sxs-lookup"><span data-stu-id="22444-128">You must open any subscription views under the Integration Management selection, select the view row, open it for editing by clicking the pencil icon, and then click the **Save disk** icon to refresh the view definition.</span></span> <span data-ttu-id="22444-129">Nenhuma outra alteração é necessária para regenerar a sintaxe da exibição.</span><span class="sxs-lookup"><span data-stu-id="22444-129">No other change is needed to regenerate the view syntax.</span></span>  
  
-   <span data-ttu-id="22444-130">As tabelas de preparo que incluem o atributo terão uma coluna de atributo substituído adicionada a ele, o que significa que o código de preparação será afetado.</span><span class="sxs-lookup"><span data-stu-id="22444-130">Staging tables that include the attribute will have a deprecated attribute column added to them, which means that your staging code will be affected.</span></span> <span data-ttu-id="22444-131">Para livrar-se do atributo substituído, você poderá excluí-lo depois de atualizar as regras de negócio e as exibições de assinatura.</span><span class="sxs-lookup"><span data-stu-id="22444-131">To get rid of the deprecated attribute, you can delete it after you have updated the business rules and subscription views.</span></span>  
  
 <span data-ttu-id="22444-132">**Excluindo o atributo substituído**</span><span class="sxs-lookup"><span data-stu-id="22444-132">**Deleting the deprecated attribute**</span></span>  
  
 <span data-ttu-id="22444-133">Antes de excluir qualquer atributo substituído, você deverá remover as referências ao atributo, por exemplo, corrigindo as regras de negócio e regenerando as exibições de assinatura conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="22444-133">Before you delete any deprecated attribute, you must remove any references to the attribute such as fixing the business rules and regenerating subscription views as described earlier.</span></span> <span data-ttu-id="22444-134">Caso contrário, você obterá um erro na página da Web da administração do sistema ao tentar excluir o atributo substituído indicando que o atributo não poderá ser excluído porque é referenciado por um objeto.</span><span class="sxs-lookup"><span data-stu-id="22444-134">Otherwise, you will get an error in the System Administration web page when you attempt to delete the deprecated attribute stating that the attribute cannot be deleted because it is referenced by an object.</span></span>  
  
 <span data-ttu-id="22444-135">Para excluir um atributo, consulte [excluir um atributo &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="22444-135">To delete an attribute, see [Delete an Attribute &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="22444-136">É incômodo alterar tipos de dados para os atributos do MDS que tenham dados existentes e entidades relacionadas, especialmente se houver uma regra de negócio ou uma exibição de assinatura declarada que depende da entidade.</span><span class="sxs-lookup"><span data-stu-id="22444-136">It is cumbersome to change data types for MDS attributes that have existing data and related entities, especially if there is a business rule or subscription view declared which depends on the entity.</span></span> <span data-ttu-id="22444-137">A prática recomendada é iniciar com um tipo de dados que é flexível o suficiente para manter os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="22444-137">The best practice is to start with a data type that is flexible enough to hold the necessary values.</span></span> <span data-ttu-id="22444-138">Por exemplo, as cadeias de caracteres podem começar pequenas, mas podem precisar ser aumentadas com o passar do tempo; portanto, considere o pior cenário.</span><span class="sxs-lookup"><span data-stu-id="22444-138">For example, strings may start small, but may need to be lengthened over time, so consider the worst case scenarios.</span></span> <span data-ttu-id="22444-139">O comprimento adicional de cadeia de caracteres de texto pode ser penoso (por exemplo, é difícil ajustar na tela as caixas de texto largas da GUI), portanto evite o comprimento muito longo da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="22444-139">Extra text string length can be burdensome (for example, wide GUI text boxes are hard to fit on the screen), so avoid too long string length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22444-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22444-140">See Also</span></span>  
 <span data-ttu-id="22444-141">[Atributos &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="22444-141">[Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span></span>  
 [<span data-ttu-id="22444-142">Criando um modelo &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="22444-142">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
