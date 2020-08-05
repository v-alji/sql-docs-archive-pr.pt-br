---
title: Definir a ordenação de uma dimensão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OrderBy property
- dimensions [Analysis Services], ordering
- Business Intelligence enhancements [Analysis Services], ordering
- dimensions [Analysis Services], Business Intelligence enhancements
- ordering dimensions [Analysis Services]
- OrderByAttributeID property
ms.assetid: c42fbd58-244d-4e0a-b715-6f919cbc3ad9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8cd5ea148e374c18c530ba0a15c80dbb23983020
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571667"
---
# <a name="define-the-ordering-for-a-dimension"></a><span data-ttu-id="caccd-102">Definir a ordenação para uma dimensão</span><span class="sxs-lookup"><span data-stu-id="caccd-102">Define the Ordering for a Dimension</span></span>
  <span data-ttu-id="caccd-103">Adicione o aprimoramento de ordenação de atributos a um cubo ou dimensão para especificar como os membros de um atributo são ordenados.</span><span class="sxs-lookup"><span data-stu-id="caccd-103">Add the attribute ordering enhancement to a cube or dimension to specify how the members of an attribute are ordered.</span></span> <span data-ttu-id="caccd-104">Os membros podem ser ordenados pelo nome ou pela chave do atributo ou pelo nome ou pela chave de outro atributo (com base na relação de um atributo).</span><span class="sxs-lookup"><span data-stu-id="caccd-104">Members can be ordered by the name or the key of the attribute, or by the name or the key of another attribute (based on an attribute relationship).</span></span> <span data-ttu-id="caccd-105">Por padrão, os membros são ordenados por nome.</span><span class="sxs-lookup"><span data-stu-id="caccd-105">By default, members are ordered by the name.</span></span> <span data-ttu-id="caccd-106">Esse aprimoramento altera as configurações das propriedades `OrderBy` e `OrderByAttributeID` dos atributos de uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="caccd-106">This enhancement changes the `OrderBy` and `OrderByAttributeID` property settings for attributes in a dimension.</span></span>  
  
 <span data-ttu-id="caccd-107">Para adicionar uma ordenação de atributos, use o Assistente de Business Intelligence e selecione a opção **Especificar a Ordenação de Atributos** na página **Escolher Aprimoramento** .</span><span class="sxs-lookup"><span data-stu-id="caccd-107">To add attribute ordering, you use the Business Intelligence Wizard, and select the **Specify attribute ordering** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="caccd-108">Esse assistente orientará você durante as etapas para selecionar a dimensão à qual você deseja aplicar a ordenação de atributos e especificar como ordenar os atributos da dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="caccd-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply attribute ordering and specifying how to order the attributes for the selected dimension.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="caccd-109">Selecionando uma dimensão</span><span class="sxs-lookup"><span data-stu-id="caccd-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="caccd-110">Na primeira página **Especificar a Ordenação de Atributos** do assistente, especifique a dimensão à qual você deseja aplicar a ordenação de atributos.</span><span class="sxs-lookup"><span data-stu-id="caccd-110">On the first **Specify Attribute Ordering** page of the wizard, you specify the dimension to which you want to apply attribute ordering.</span></span> <span data-ttu-id="caccd-111">O aprimoramento de ordenação de atributos adicionado à dimensão selecionada provocará alterações na dimensão.</span><span class="sxs-lookup"><span data-stu-id="caccd-111">The attribute ordering enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="caccd-112">Essas alterações serão herdadas por todos os cubos que tiverem a dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="caccd-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="specifying-ordering"></a><span data-ttu-id="caccd-113">Especificando a ordenação</span><span class="sxs-lookup"><span data-stu-id="caccd-113">Specifying Ordering</span></span>  
 <span data-ttu-id="caccd-114">Na segunda página **Especificar a Ordenação de Atributos** do assistente, especifique como os atributos da dimensão serão ordenados.</span><span class="sxs-lookup"><span data-stu-id="caccd-114">On the second **Specify Attribute Ordering** page of the wizard, you specify how all the attributes in the dimension will be ordered.</span></span>  
  
 <span data-ttu-id="caccd-115">Na coluna **Atributo de Ordenação** , você pode alterar o atributo usado para fazer a ordenação.</span><span class="sxs-lookup"><span data-stu-id="caccd-115">In the **Ordering Attribute** column, you can change the attribute used to do the ordering.</span></span> <span data-ttu-id="caccd-116">Se o atributo que você deseja usar para ordenar Membros não estiver na lista, role para baixo na lista e, em seguida, selecione **\<New attribute...>** para abrir a caixa de diálogo **selecionar uma coluna** , onde você pode selecionar uma coluna em uma tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="caccd-116">If the attribute that you want to use to order members is not in the list, scroll down the list, and then select **\<New attribute...>** to open the **Select a Column** dialog box, where you can select a column in a dimension table.</span></span> <span data-ttu-id="caccd-117">Com a seleção de uma coluna pela caixa de diálogo **Selecionar uma Coluna** , é criado um atributo adicional que será usado para ordenar os membros de um atributo.</span><span class="sxs-lookup"><span data-stu-id="caccd-117">Selecting a column by using the **Select a Column** dialog box creates an additional attribute with which to order members of an attribute.</span></span>  
  
 <span data-ttu-id="caccd-118">Na coluna **Critérios** , você pode selecionar ordenar os membros do atributo por **Chave** ou **Nome**.</span><span class="sxs-lookup"><span data-stu-id="caccd-118">In the **Criteria** column, you can then select whether to order the members of the attribute by either **Key** or **Name**.</span></span>  
  
  
