---
title: Criar uma dimensão usando o assistente para dimensões | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], creating
ms.assetid: d84f66ae-7551-49bf-99d0-88368ca2dd0e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ec38dc7170b915dce0cedea60c93385560e11f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683772"
---
# <a name="create-a-dimension-using-the-dimension-wizard"></a><span data-ttu-id="b40ae-102">Criar uma dimensão usando o Assistente para Dimensões</span><span class="sxs-lookup"><span data-stu-id="b40ae-102">Create a Dimension Using the Dimension Wizard</span></span>
  <span data-ttu-id="b40ae-103">Você pode criar uma nova dimensão usando o Assistente para Dimensões no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b40ae-103">You can create a new dimension by using the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-dimension"></a><span data-ttu-id="b40ae-104">Para criar uma nova dimensão</span><span class="sxs-lookup"><span data-stu-id="b40ae-104">To create a new dimension</span></span>  
  
1.  <span data-ttu-id="b40ae-105">No **Gerenciador de Soluções**, clique com o botão direito do mouse em **Dimensões**e clique em **Nova Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="b40ae-105">In **Solution Explorer**, right-click **Dimensions**, and then click **New Dimension**.</span></span>  
  
2.  <span data-ttu-id="b40ae-106">Na página **Selecionar Método de Criação** do Assistente para Dimensões, selecione **Usar uma tabela existente**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b40ae-106">On the **Select Creation Method** page of the Dimension Wizard, select **Use an existing table**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b40ae-107">Ocasionalmente, você pode precisar criar uma dimensão sem usar uma tabela existente.</span><span class="sxs-lookup"><span data-stu-id="b40ae-107">You might occasionally have to create a dimension without using an existing table.</span></span> <span data-ttu-id="b40ae-108">Para obter mais informações, consulte [Criar uma dimensão gerando uma tabela que não seja de tempo na fonte de dados](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) e [Criar uma dimensão de tempo gerando uma tabela de tempo](create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="b40ae-108">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) and [Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
3.  <span data-ttu-id="b40ae-109">Na página **Especificar Informações sobre a Origem** , execute os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b40ae-109">On the **Specify Source Information** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="b40ae-110">Na lista **Exibição da fonte de dados** , selecione uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b40ae-110">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="b40ae-111">Na lista **Tabela principal** , selecione a tabela principal de dimensão.</span><span class="sxs-lookup"><span data-stu-id="b40ae-111">In the **Main table** list, select the main dimension table.</span></span>  
  
    3.  <span data-ttu-id="b40ae-112">Na lista **Colunas de Chaves** , examine as colunas de chave que o assistente selecionou automaticamente com base na chave primária definida na tabela principal de dimensão.</span><span class="sxs-lookup"><span data-stu-id="b40ae-112">In the **Key columns** list, review the key columns that the wizard has automatically selected based on the primary key that is defined in the main dimension table.</span></span> <span data-ttu-id="b40ae-113">Para alterar essa configuração padrão, especifique as colunas de chaves que vinculam a tabela de dimensões à tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="b40ae-113">To change this default setting, specify the key columns that link the dimension table to the fact table.</span></span>  
  
    4.  <span data-ttu-id="b40ae-114">Na lista suspensa **Coluna de Nome** , examine a coluna de nome que o assistente selecionou automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b40ae-114">In the **Name column** drop-down list, review the name column that the wizard has automatically selected.</span></span>  
  
         <span data-ttu-id="b40ae-115">Esse nome padrão é apropriado quando a coluna contém informações descritivas.</span><span class="sxs-lookup"><span data-stu-id="b40ae-115">This default name is appropriate when the column contains descriptive information.</span></span> <span data-ttu-id="b40ae-116">Porém, convém especificar um nome que contenha valores mais significativos para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="b40ae-116">However, you might want to specify a name that contains values that are more meaningful for the end user.</span></span> <span data-ttu-id="b40ae-117">Por exemplo, se um atributo de categoria de produto em uma dimensão de Produtos usar a coluna **ProductCategoryKey** como sua coluna de chaves, você poderá especificar a coluna **ProductCategoryName** como sua coluna de nome.</span><span class="sxs-lookup"><span data-stu-id="b40ae-117">For example, if a product category attribute in a Products dimension uses the **ProductCategoryKey** column as its key column, you can specify the **ProductCategoryName** column as its name column.</span></span>  
  
         <span data-ttu-id="b40ae-118">Se a lista **Colunas de Chaves** contiver várias colunas de chaves, você deverá especificar uma coluna de nome que forneça os valores de membro para o atributo de chave.</span><span class="sxs-lookup"><span data-stu-id="b40ae-118">If the **Key columns** list contains multiple key columns, you must specify a name column that provides the member values for the key attribute.</span></span> <span data-ttu-id="b40ae-119">Para fazer isso, você pode criar um cálculo nomeado na exibição da fonte de dados e usá-lo como a coluna de nome.</span><span class="sxs-lookup"><span data-stu-id="b40ae-119">To do this, you can create a named calculation in the data source view and use that as the name column.</span></span>  
  
    5.  <span data-ttu-id="b40ae-120">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b40ae-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="b40ae-121">Na página **Selecionar Tabelas Relacionadas** , selecione as tabelas relacionadas que você quer incluir em sua dimensão e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b40ae-121">On the **Select Related Tables** page, select the related tables that you want to include in your dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b40ae-122">A página **Selecionar Tabelas Relacionadas** será exibida se a tabela principal de dimensão especificada tiver relações com outras tabelas de dimensão.</span><span class="sxs-lookup"><span data-stu-id="b40ae-122">The **Select Related Tables** page appears if the main dimension table that you specified has relationships to other dimension tables.</span></span>  
  
5.  <span data-ttu-id="b40ae-123">Na página **Selecionar Atributos de Dimensão** , selecione os atributos que você quer incluir na dimensão e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b40ae-123">On the **Select Dimension Attributes** page, select the attributes that you want to include in the dimension, and then click **Next**.</span></span>  
  
     <span data-ttu-id="b40ae-124">Opcionalmente, você pode alterar os nomes de atributo, habilitar ou desabilitar a navegação, e especificar o tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="b40ae-124">Optionally, you can change the attribute names, enable or disable browsing, and specify the attribute type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b40ae-125">Para ativar os campos **Habilitar Navegação** e **Tipo de Atributo** de um atributo, o atributo deve ser selecionado para inclusão na dimensão.</span><span class="sxs-lookup"><span data-stu-id="b40ae-125">To make the **Enable Browsing** and **Attribute Type** fields of an attribute active, the attribute must be selected for inclusion in the dimension.</span></span>  
  
6.  <span data-ttu-id="b40ae-126">Na página **Definir Inteligência de Conta** , na coluna **Tipos de Conta Interna** , selecione o tipo de conta e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b40ae-126">On the **Define Account Intelligence** page, in the **Built-In Account Types** column, select the account type, and then click **Next**.</span></span>  
  
     <span data-ttu-id="b40ae-127">O tipo de conta deve corresponder ao tipo de conta da tabela de origem que está listada na coluna **Tipos de Conta de Tabela de Origem** .</span><span class="sxs-lookup"><span data-stu-id="b40ae-127">The account type must correspond to the account type of the source table that is listed in the **Source Table Account Types** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b40ae-128">A página **Definir Inteligência de Conta** aparecerá se você definir um atributo de dimensão **Tipo de Conta** na página **Selecionar Atributos da Dimensão** do assistente.</span><span class="sxs-lookup"><span data-stu-id="b40ae-128">The **Define Account Intelligence** page appears if you defined an **Account Type** dimension attribute on the **Select Dimension Attributes** page of the wizard.</span></span>  
  
7.  <span data-ttu-id="b40ae-129">Na página **Concluindo o Assistente** , digite um nome para a nova dimensão e examine a estrutura da dimensão.</span><span class="sxs-lookup"><span data-stu-id="b40ae-129">On the **Completing the Wizard** page, enter a name for the new dimension and review the dimension structure.</span></span> <span data-ttu-id="b40ae-130">Se você quiser fazer mudanças, clique em **Voltar**; caso contrário, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b40ae-130">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b40ae-131">Você pode usar o Designer de Dimensão depois de concluir o Assistente para Dimensões para adicionar, remover, e configurar atributos e hierarquias na dimensão.</span><span class="sxs-lookup"><span data-stu-id="b40ae-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b40ae-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b40ae-132">See Also</span></span>  
 [<span data-ttu-id="b40ae-133">Criar uma dimensão usando uma tabela existente</span><span class="sxs-lookup"><span data-stu-id="b40ae-133">Create a Dimension by Using an Existing Table</span></span>](create-a-dimension-by-using-an-existing-table.md)  
  
  
