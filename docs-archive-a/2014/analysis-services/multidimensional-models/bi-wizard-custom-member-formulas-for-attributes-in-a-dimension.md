---
title: Definir fórmulas de membro personalizado para atributos em uma dimensão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Business Intelligence enhancements [Analysis Services], custom member formulas
- member formulas [Analysis Services]
- dimensions [Analysis Services], Business Intelligence enhancements
- custom member formulas [Analysis Services]
- CustomRollupColumn property
ms.assetid: c4467b08-ce59-4de7-a2d9-c22e246bdd52
author: minewiskan
ms.author: owend
ms.openlocfilehash: 112f8944bd20b2b6a464b0d84fb8ac1a0e89d976
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571665"
---
# <a name="set-custom-member-formulas-for-attributes-in-a-dimension"></a><span data-ttu-id="bf987-102">Definir fórmulas de membro personalizado para os atributos de uma dimensão</span><span class="sxs-lookup"><span data-stu-id="bf987-102">Set Custom Member Formulas for Attributes in a Dimension</span></span>
  <span data-ttu-id="bf987-103">Adicione um aprimoramento de fórmula de membro personalizado a um cubo ou a uma dimensão para substituir as agregações padrão associadas a um membro da dimensão pelos resultados de uma expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="bf987-103">Add a custom member formula enhancement to a cube or dimension to replace the default aggregation that is associated with a dimension member with the results of a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="bf987-104">(Esse aprimoramento define a propriedade `CustomRollupColumn` em um atributo especificado de uma dimensão.)</span><span class="sxs-lookup"><span data-stu-id="bf987-104">(This enhancement sets the `CustomRollupColumn` property on a specified attribute in a dimension.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf987-105">Uma fórmula de membro personalizado estará disponível somente para dimensões baseadas em fontes de dados existentes.</span><span class="sxs-lookup"><span data-stu-id="bf987-105">A custom member formula is available only for dimensions that are based on existing data sources.</span></span> <span data-ttu-id="bf987-106">Para dimensões que foram criadas sem usar uma fonte de dados, execute o Assistente de Geração de Esquema para criar uma exibição da fonte de dados antes de adicionar a fórmula de membro personalizado.</span><span class="sxs-lookup"><span data-stu-id="bf987-106">For dimensions that were created without using a data source, you must run the Schema Generation Wizard to create a data source view before adding a custom member formula.</span></span>  
  
 <span data-ttu-id="bf987-107">Para adicionar uma fórmula de membro personalizado, use o Assistente de Business Intelligence e selecione a opção **Criar uma fórmula de membro personalizado** na página **Escolher Aprimoramento** .</span><span class="sxs-lookup"><span data-stu-id="bf987-107">To add a custom member formula, you use the Business Intelligence Wizard, and select the **Create a custom member formula** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="bf987-108">Esse assistente orientará você durante as etapas para selecionar a dimensão à qual você deseja aplicar a fórmula de membro personalizado e habilitá-la.</span><span class="sxs-lookup"><span data-stu-id="bf987-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply a custom member formula and enabling the custom member formula.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="bf987-109">Selecionando uma dimensão</span><span class="sxs-lookup"><span data-stu-id="bf987-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="bf987-110">Na primeira página **Criar uma Fórmula de Membro Personalizado** do assistente, especifique a dimensão à qual você deseja aplicar fórmula de membro personalizado.</span><span class="sxs-lookup"><span data-stu-id="bf987-110">On the first **Create a Custom Member Formula** page of the wizard, you specify the dimension to which you want to apply a custom member formula.</span></span> <span data-ttu-id="bf987-111">O aprimoramento de fórmula de membro personalizado adicionado à dimensão selecionada provocará alterações na dimensão.</span><span class="sxs-lookup"><span data-stu-id="bf987-111">The custom member formula enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="bf987-112">Essas alterações serão herdadas por todos os cubos que tiverem a dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="bf987-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="enabling-a-custom-member-formula"></a><span data-ttu-id="bf987-113">Habilitando uma fórmula de membro personalizado</span><span class="sxs-lookup"><span data-stu-id="bf987-113">Enabling a Custom Member Formula</span></span>  
 <span data-ttu-id="bf987-114">Na segunda página **Criar Fórmula de Membro Personalizado** , associe a coluna de origem que contém a fórmula de membro personalizado a um ou mais atributos da dimensão.</span><span class="sxs-lookup"><span data-stu-id="bf987-114">On the second **Create a Custom Member Formula** page, you associate the source column that contains the custom member formula with one or more attributes in the dimension.</span></span> <span data-ttu-id="bf987-115">Na coluna **Atributo** , marque a caixa de seleção junto ao atributo que você deseja associar à coluna de fórmula de membro personalizado.</span><span class="sxs-lookup"><span data-stu-id="bf987-115">In the **Attribute** column, select the check box next to the attribute that you want to associate with the custom member formula column.</span></span> <span data-ttu-id="bf987-116">Depois que você selecionar cada atributo, o assistente exibirá a caixa de diálogo **Selecionar uma Coluna** .</span><span class="sxs-lookup"><span data-stu-id="bf987-116">After you select each attribute, the wizard displays the **Select a Column** dialog box.</span></span> <span data-ttu-id="bf987-117">Nessa caixa de diálogo, clique na coluna da tabela de dimensão que contém a fórmula.</span><span class="sxs-lookup"><span data-stu-id="bf987-117">In this dialog box, click the column in the dimension table that contains the formula.</span></span> <span data-ttu-id="bf987-118">Para alterar a seleção depois de fechar a caixa de diálogo **Selecionar uma Coluna** , clique na célula **Coluna de Origem** que você deseja alterar e, em seguida, clique nas reticências (**...**) para abrir novamente a caixa de diálogo **Selecionar uma Coluna** .</span><span class="sxs-lookup"><span data-stu-id="bf987-118">If you want to change a selection after you close the **Select a Column** dialog box, click the **Source Column** cell that you want to change, and then click the ellipsis (**...**) to open the **Select a Column** dialog box again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf987-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf987-119">See Also</span></span>  
 [<span data-ttu-id="bf987-120">Usar o Assistente de Business Intelligence para aprimorar dimensões</span><span class="sxs-lookup"><span data-stu-id="bf987-120">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
  
  
