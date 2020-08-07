---
title: Habilitar write-back de dimensão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying dimensions
- writeback [Analysis Services], setting up
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], writeback
- dimensions [Analysis Services], writeback
- writeback [Analysis Services]
- dimensions [Analysis Services], modifying
- manual dimension structure modifications
ms.assetid: a4b5eb5a-366d-4fc8-ad0d-5bdb8e7b4163
author: minewiskan
ms.author: owend
ms.openlocfilehash: cba4a54e8a51d022c6f84a4c81d32f359a95692a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571663"
---
# <a name="enable-dimension-writeback"></a><span data-ttu-id="8e98f-102">Habilitar Write-back de Dimensão</span><span class="sxs-lookup"><span data-stu-id="8e98f-102">Enable Dimension Writeback</span></span>
  <span data-ttu-id="8e98f-103">Adicione o aprimoramento de write-back de dimensão a um cubo ou dimensão para que os usuários possam modificar manualmente a estrutura e os membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e98f-103">Add the dimension writeback enhancement to a cube or dimension to allow users to manually modify the dimension structure and members.</span></span> <span data-ttu-id="8e98f-104">Atualizações em uma dimensão habilitada para gravação são registradas diretamente na tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="8e98f-104">Updates to a write-enabled dimension are recorded directly in the dimension table.</span></span> <span data-ttu-id="8e98f-105">Esse aprimoramento altera a configuração de propriedade `WriteEnabled` de uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e98f-105">This enhancement changes the `WriteEnabled` property setting for a dimension.</span></span>  
  
 <span data-ttu-id="8e98f-106">Para adicionar o write-back da dimensão, use o Assistente de Business Intelligence e selecione a opção **Habilitar o write-back de dimensão** na página **Escolher Aprimoramento** .</span><span class="sxs-lookup"><span data-stu-id="8e98f-106">To add dimension writeback, you use the Business Intelligence Wizard, and select the **Enable dimension writeback** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="8e98f-107">Esse assistente orientará você durante as etapas para selecionar a dimensão à qual você deseja aplicar um write-back de dimensão e para configurar essa opção para a dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e98f-107">This wizard then guides you through the steps of selecting a dimension to which you want to apply dimension writeback and setting this option for the selected dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e98f-108">Write-back tem suporte apenas em bancos de dados relacionais do SQL Server e data marts.</span><span class="sxs-lookup"><span data-stu-id="8e98f-108">Writeback is supported for SQL Server relational databases and data marts only.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="8e98f-109">Selecionando uma dimensão</span><span class="sxs-lookup"><span data-stu-id="8e98f-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="8e98f-110">Na primeira página **Habilitar o Write-back de Dimensão** do assistente, especifique a dimensão à qual você deseja aplicar o write-back de dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e98f-110">On the first **Enable Dimension Writeback** page of the wizard, you specify the dimension to which you want to apply dimension writeback.</span></span> <span data-ttu-id="8e98f-111">O aprimoramento de write-back de dimensão adicionado à dimensão selecionada provocará alterações na dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e98f-111">The dimension writeback enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="8e98f-112">Essas alterações serão herdadas por todos os cubos que tiverem a dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e98f-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="setting-dimension-writeback-capability"></a><span data-ttu-id="8e98f-113">Definindo a capacidade de write-back de dimensão</span><span class="sxs-lookup"><span data-stu-id="8e98f-113">Setting Dimension Writeback Capability</span></span>  
 <span data-ttu-id="8e98f-114">Na segunda página **Habilitar o Write-back de Dimensão** do assistente, você realmente define a opção **Habilitar write-back na dimensão** .</span><span class="sxs-lookup"><span data-stu-id="8e98f-114">On the second **Enable Dimension Writeback** page of the wizard, you actually set the **Enable writeback in the dimension** option.</span></span> <span data-ttu-id="8e98f-115">A seleção dessa opção definirá automaticamente a propriedade `WriteEnabled` da dimensão como `True`.</span><span class="sxs-lookup"><span data-stu-id="8e98f-115">Selecting this option automatically sets the `WriteEnabled` property of the dimension to `True`.</span></span> <span data-ttu-id="8e98f-116">Desmarcar essa opção definirá automaticamente a propriedade como `False`.</span><span class="sxs-lookup"><span data-stu-id="8e98f-116">Clearing this option automatically sets the property to `False`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e98f-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="8e98f-117">Remarks</span></span>  
 <span data-ttu-id="8e98f-118">Ao criar um novo membro, você deve incluir todo atributo em uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e98f-118">When you create a new member, you must include every attribute in a dimension.</span></span> <span data-ttu-id="8e98f-119">Você não pode inserir um membro sem especificar um valor para o atributo de chave da dimensão.</span><span class="sxs-lookup"><span data-stu-id="8e98f-119">You cannot insert a member without specifying a value for the key attribute of the dimension.</span></span> <span data-ttu-id="8e98f-120">Portanto, a criação de membros está sujeita às restrições (como valores de chave não nulos) definidas na tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="8e98f-120">Therefore, creating members is subject to any constraints (such as non-null key values) that are defined on the dimension table.</span></span> <span data-ttu-id="8e98f-121">Você também deve considerar opcionalmente colunas especificadas por propriedades de dimensão, como colunas especificadas na propriedade de dimensão `CustomRollupColumn`, `CustomRollupPropertiesColumn` ou `UnaryOperatorColumn`.</span><span class="sxs-lookup"><span data-stu-id="8e98f-121">You should also consider columns optionally specified by dimension properties, such as columns specified in the `CustomRollupColumn`, `CustomRollupPropertiesColumn` or the `UnaryOperatorColumn` dimension properties.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8e98f-122">Se você usar o SQL Azure como uma fonte de dados para executar writeback em um banco de dados do Analysis Services, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="8e98f-122">If you use SQL Azure as a data source to perform writeback into an Analysis Services database, the operation fails.</span></span> <span data-ttu-id="8e98f-123">Isto ocorre por design, porque a opção de provedor que habilita vários conjuntos de resultados ativos (MARS) não é ativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="8e98f-123">This is by design, because the provider option that enables multiple active result sets (MARS) is not turned on by default.</span></span>  
>   
>  <span data-ttu-id="8e98f-124">A solução alternativa é adicionar a configuração a seguir na cadeia de conexão, para dar suporte a MARS e habilitar writeback:</span><span class="sxs-lookup"><span data-stu-id="8e98f-124">The workaround is to add the following setting in the connection string, to support MARS and to enable writeback:</span></span>  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  <span data-ttu-id="8e98f-125">Para obter mais informações, consulte [Usando MARS &#40;vários conjuntos de resultados ativos&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="8e98f-125">For more information see [Using Multiple Active Result Sets &#40;MARS&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e98f-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e98f-126">See Also</span></span>  
 [<span data-ttu-id="8e98f-127">Dimensões habilitadas para gravação</span><span class="sxs-lookup"><span data-stu-id="8e98f-127">Write-Enabled Dimensions</span></span>](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
