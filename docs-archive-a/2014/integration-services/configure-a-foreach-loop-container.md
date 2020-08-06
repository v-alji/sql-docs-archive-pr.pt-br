---
title: Configurar um contêiner Loop Foreach | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Foreach Loop containers
- containers [Integration Services], Foreach Loop
ms.assetid: 519c6f96-5e1f-47d2-b96a-d49946948c25
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 85fb399f51e22e091fac9b1d8d332b9a12e7d77e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570172"
---
# <a name="configure-a-foreach-loop-container"></a><span data-ttu-id="e9e72-102">Para configurar um contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="e9e72-102">Configure a Foreach Loop Container</span></span>
  <span data-ttu-id="e9e72-103">Este procedimento descreve como configurar um contêiner Loop Foreach, incluindo expressões de propriedade nos níveis de enumerador e contêiner.</span><span class="sxs-lookup"><span data-stu-id="e9e72-103">This procedure describes how to configure a Foreach Loop container, including property expressions at the enumerator and container levels.</span></span>  
  
### <a name="to-configure-the-foreach-loop-container"></a><span data-ttu-id="e9e72-104">Para configurar o contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="e9e72-104">To configure the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="e9e72-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="e9e72-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="e9e72-106">Clique na guia **Fluxo de Controle** e clique duas vezes no Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="e9e72-106">Click the **Control Flow** tab and double-click the Foreach Loop.</span></span>  
  
3.  <span data-ttu-id="e9e72-107">Na caixa de diálogo **Editor de Loop Foreach** , clique em **Geral** e, como alternativa, modifique o nome e a descrição do Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="e9e72-107">In the **Foreach Loop Editor** dialog box, click **General** and, optionally, modify the name and description of the Foreach Loop.</span></span>  
  
4.  <span data-ttu-id="e9e72-108">Clique em **Coleção** e selecione um tipo de enumerador na lista **Enumerador** .</span><span class="sxs-lookup"><span data-stu-id="e9e72-108">Click **Collection** and select an enumerator type from the **Enumerator** list.</span></span>  
  
5.  <span data-ttu-id="e9e72-109">Especifique um enumerador e defina opções de enumerador conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9e72-109">Specify an enumerator and set enumerator options as follows:</span></span>  
  
    -   <span data-ttu-id="e9e72-110">Para usar o enumerador de Arquivo Foreach, forneça a pasta que contém os arquivos a serem enumerados, especifique um filtro do nome e tipo de arquivo e especifique se o nome de arquivo totalmente qualificado deverá ser retornado.</span><span class="sxs-lookup"><span data-stu-id="e9e72-110">To usethe Foreach File enumerator, provide the folder that contains the files to enumerate, specify a filter for the file name and type, and specify whether the fully qualified file name should be returned.</span></span> <span data-ttu-id="e9e72-111">Indique também se você deseja a função recursiva em subpastas para obter mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="e9e72-111">Also, indicate whether to recurse through subfolders for more files.</span></span>  
  
    -   <span data-ttu-id="e9e72-112">Para usar o enumerador de Item Foreach, clique em **Colunas**e, na caixa de diálogo **Colunas Para Cada Item** , clique em **Adicionar** para adicionar colunas.</span><span class="sxs-lookup"><span data-stu-id="e9e72-112">To use the Foreach Item enumerator, click **Columns**, and, in the **For Each Item Columns** dialog box, click **Add** to add columns.</span></span> <span data-ttu-id="e9e72-113">Selecione um tipo de dados para cada coluna na lista **Tipo de Dados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9e72-113">Select a data type in the **Data Type** list for each column, and click **OK**.</span></span>  
  
         <span data-ttu-id="e9e72-114">Digite os valores nas colunas ou selecione-os nas listas.</span><span class="sxs-lookup"><span data-stu-id="e9e72-114">Type values in the columns or select values from lists.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e9e72-115">Para adicionar uma nova linha, clique em qualquer lugar fora da célula digitada.</span><span class="sxs-lookup"><span data-stu-id="e9e72-115">To add a new row, click anywhere outside the cell in which you typed.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e9e72-116">Se um valor não for compatível com o tipo de dados de coluna, o texto será realçado.</span><span class="sxs-lookup"><span data-stu-id="e9e72-116">If a value is not compatible with the column data type, the text is highlighted.</span></span>  
  
    -   <span data-ttu-id="e9e72-117">Para usar o enumerador ADO Foreach, selecione uma variável existente ou clique em **Nova Variável** na lista **Variável de origem de objeto ADO** para especificar a variável que contém o nome do objeto ADO a ser enumerado e selecione uma opção de modo de enumeração.</span><span class="sxs-lookup"><span data-stu-id="e9e72-117">To use the Foreach ADO enumerator, select an existing variable or click **New variable** in the **ADO object source variable** list to specify the variable that contains the name of the ADO object to enumerate, and select an enumeration mode option.</span></span>  
  
         <span data-ttu-id="e9e72-118">Se você estiver criando uma variável nova, defina as propriedades da variável na caixa de diálogo **Adicionar Variável** .</span><span class="sxs-lookup"><span data-stu-id="e9e72-118">If creating a new variable, set the variable properties in the **Add Variable** dialog box.</span></span>  
  
    -   <span data-ttu-id="e9e72-119">Para usar o enumerador de Conjunto de Linhas de Esquema ADO.NET Foreach, selecione uma conexão ADO.NET existente ou clique em **Nova conexão** na lista **Conexão** e depois selecione um esquema.</span><span class="sxs-lookup"><span data-stu-id="e9e72-119">To use the Foreach ADO.NET Schema Rowset enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then select a schema.</span></span>  
  
         <span data-ttu-id="e9e72-120">Outra opção é clicar em **Definir Restrições** e selecionar restrições de esquema, selecionar a variável que contém o valor de restrição ou digitar o valor da restrição e clicar em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9e72-120">Optionally, click **Set Restrictions** and select schema restrictions, select the variable that contains the restriction value or type the restriction value, and click **OK**.</span></span>  
  
    -   <span data-ttu-id="e9e72-121">Para usar o enumerador Foreach de Variável , selecione uma variável na lista **Variável** .</span><span class="sxs-lookup"><span data-stu-id="e9e72-121">To use the Foreach From Variable enumerator, select a variable in the **Variable** list.</span></span>  
  
    -   <span data-ttu-id="e9e72-122">Para usar o enumerador NodeList Foreach, clique em DocumentSourceType, selecione o tipo de fonte na lista e clique em DocumentSource.</span><span class="sxs-lookup"><span data-stu-id="e9e72-122">To use the Foreach NodeList enumerator, click DocumentSourceType and select the source type from the list, and then click DocumentSource.</span></span> <span data-ttu-id="e9e72-123">Dependendo do valor selecionado para DocumentSourceType, selecione uma variável ou uma conexão de arquivo da lista, crie uma nova variável ou conexão de arquivo ou digite a origem XML no **Editor de Origem de Documento**.</span><span class="sxs-lookup"><span data-stu-id="e9e72-123">Depending on the value selected for DocumentSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the XML source in the **Document Source Editor**.</span></span>  
  
         <span data-ttu-id="e9e72-124">Depois, clique em EnumerationType e selecione um tipo de enumeração na lista.</span><span class="sxs-lookup"><span data-stu-id="e9e72-124">Next, click EnumerationType and select an enumeration type from the list.</span></span> <span data-ttu-id="e9e72-125">Se EnumerationType for **Navegador, Nó ou Texto de Nó**, clique em OuterXPathStringSourceType e selecione o tipo de fonte, clicando em seguida em OuterXPathString.</span><span class="sxs-lookup"><span data-stu-id="e9e72-125">If EnumerationType is **Navigator, Node, or NodeText**, click OuterXPathStringSourceType and select the source type, and then click OuterXPathString.</span></span> <span data-ttu-id="e9e72-126">Dependendo do conjunto de valores de OuterXPathStringSourceType, selecione uma variável ou uma conexão de arquivo da lista, crie uma nova variável ou conexão de arquivo ou digite a cadeia de caracteres da expressão de XML Path Language (XPath) externa.</span><span class="sxs-lookup"><span data-stu-id="e9e72-126">Depending on the value set for OuterXPathStringSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the string for the outer XML Path Language (XPath) expression.</span></span>  
  
         <span data-ttu-id="e9e72-127">Se EnumerationType for **ElementCollection**,defina OuterXPathStringSourceType e OuterXPathString, conforme descrito acima.</span><span class="sxs-lookup"><span data-stu-id="e9e72-127">If EnumerationType is **ElementCollection**,set OuterXPathStringSourceType and OuterXPathString as described above.</span></span> <span data-ttu-id="e9e72-128">Depois, clique em InnerElementType e selecione um tipo de enumeração para os elementos internos e clique em InnerXPathStringSourceType.</span><span class="sxs-lookup"><span data-stu-id="e9e72-128">Then, click InnerElementType and select an enumeration type for the inner elements, and then click InnerXPathStringSourceType.</span></span> <span data-ttu-id="e9e72-129">Dependendo do valor definido para InnerXPathStringSourceType, selecione uma variável ou uma conexão de arquivo, crie uma nova variável ou conexão de arquivo ou digite a cadeia de caracteres da expressão XPath interna.</span><span class="sxs-lookup"><span data-stu-id="e9e72-129">Depending on the value set for InnerXPathStringSourceType, select a variable or a file connection, create a new variable or file connection, or type the string for the inner XPath expression.</span></span>  
  
    -   <span data-ttu-id="e9e72-130">Para usar o enumerador SMO Foreach, selecione uma conexão ADO.NET existente ou clique em **Nova conexão** na lista **Conexão** e então digite a cadeia de caracteres a ser usada ou clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="e9e72-130">To use the Foreach SMO enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then either type the string to use or click **Browse**.</span></span> <span data-ttu-id="e9e72-131">Se você clicar em **Procurar**, na caixa de diálogo **Selecionar Enumeração SMO** , selecione o tipo de objeto a ser enumerado e o tipo de enumeração e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9e72-131">If you click **Browse**, in the **Select SMO Enumeration** dialog box, select the object type to enumerate and the enumeration type, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="e9e72-132">Outra opção é clicar no botão Procurar **(…)** na caixa de texto **Expressões** na página **Coleção** para criar expressões que atualizem os valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="e9e72-132">Optionally, click the browse button **(...)** in the **Expressions** text box on the **Collection** page to create expressions that update property values.</span></span> <span data-ttu-id="e9e72-133">Para obter mais informações, consulte [Adicionar ou alterar uma expressão de propriedade](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e9e72-133">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e9e72-134"> As propriedades relacionadas na lista **Propriedade** variam por enumerador.</span><span class="sxs-lookup"><span data-stu-id="e9e72-134">The properties listed in the **Property** list varies by enumerator.</span></span>  
  
7.  <span data-ttu-id="e9e72-135">Opcionalmente, clique em **Mapeamentos de Variáveis** para mapear propriedades de objeto do valor da coleção e execute um dos procedimentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9e72-135">Optionally, click **Variable Mappings** to map object properties to the collection value, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="e9e72-136">Na lista **Variáveis**, selecione uma variável ou clique em **\<New Variable>** para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="e9e72-136">In the **Variables** list, select a variable or click **\<New Variable>** to create a new variable.</span></span>  
  
    2.  <span data-ttu-id="e9e72-137">Se você adicionar uma variável nova, defina as propriedades da variável na caixa de diálogo **Adicionar Variável** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9e72-137">If you add a new variable, set the variable properties in the **Add Variable** dialog box and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="e9e72-138">Se você usar o enumerador Para Cada Item, você poderá atualizar o valor de índice na lista **Índice** .</span><span class="sxs-lookup"><span data-stu-id="e9e72-138">If you use the For Each Item enumerator, you can update the index value in the **Index** list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e9e72-139">O valor de índice indica qual coluna no item será mapeada para a variável.</span><span class="sxs-lookup"><span data-stu-id="e9e72-139">The index value indicates which column in the item to map to the variable.</span></span> <span data-ttu-id="e9e72-140">Apenas o enumerador Para Cada Item pode usar um valor de índice diferente de 0.</span><span class="sxs-lookup"><span data-stu-id="e9e72-140">Only the For Each Item enumerator can use an index value other than 0.</span></span>  
  
8.  <span data-ttu-id="e9e72-141">Opcionalmente, clique em **Expressões** e, na página **Expressões** , crie expressões de propriedade para as propriedades do contêiner Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="e9e72-141">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the Foreach Loop container.</span></span> <span data-ttu-id="e9e72-142">Para obter mais informações, consulte [Adicionar ou alterar uma expressão de propriedade](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e9e72-142">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
9. <span data-ttu-id="e9e72-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9e72-143">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9e72-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9e72-144">See Also</span></span>  
 [<span data-ttu-id="e9e72-145">Contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="e9e72-145">Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
