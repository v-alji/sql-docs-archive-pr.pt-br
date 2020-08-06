---
title: Definir as propriedades de um componente de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], properties
ms.assetid: 73000ef6-52a2-4dec-8320-0e79acf0c2c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1fd045ba076eed2d65d801015b881a477976f5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582063"
---
# <a name="set-the-properties-of-a-data-flow-component"></a><span data-ttu-id="3e0e2-102">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="3e0e2-102">Set the Properties of a Data Flow Component</span></span>
  <span data-ttu-id="3e0e2-103">Para definir as propriedades de componentes de fluxo de dados, que incluem origens, destinos e transformações, use um dos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="3e0e2-103">To set the properties of data flow components, which include sources, destinations, and transformations, use one of the following features:</span></span>  
  
-   <span data-ttu-id="3e0e2-104">Os editores de componente fornecidos pelo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e0e2-104">The component editors that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides.</span></span> <span data-ttu-id="3e0e2-105">Esses editores incluem somente as propriedades personalizadas de cada componente de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-105">These editors include only the custom properties of each data flow component.</span></span>  
  
-   <span data-ttu-id="3e0e2-106">A janela **Propriedades** lista as propriedades personalizadas no nível do componente de cada elemento, bem como as propriedades comuns a todos os elementos do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-106">The **Properties** window lists the component-level custom properties of each element, as well as the properties common to all data flow elements.</span></span>  
  
-   <span data-ttu-id="3e0e2-107">A caixa de diálogo **Editor Avançado** fornece acesso a propriedades personalizadas para cada componente.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-107">The **Advanced Editor** dialog box provides access to custom properties for each component.</span></span> <span data-ttu-id="3e0e2-108">A caixa de diálogo **Editor Avançado** também fornece acesso a propriedades comuns a todos os componentes de fluxo de dados: as propriedades de entradas, saídas, saídas de erro, colunas e colunas externas.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-108">The **Advanced Editor** dialog box also provides access to the properties common to all data flow components-the properties of inputs, outputs, error outputs, columns, and external columns.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-a-component-editor"></a><span data-ttu-id="3e0e2-109">Para definir as propriedades de um componente de fluxo de dados usando um editor de componente</span><span class="sxs-lookup"><span data-stu-id="3e0e2-109">To set the properties of a data flow component by using a component editor</span></span>  
  
1.  <span data-ttu-id="3e0e2-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3e0e2-111">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3e0e2-112">Clique na guia **Fluxo de Controle** e clique duas vezes na tarefa Fluxo de Dados que contém o fluxo de dados com os componentes cujas propriedades você deseja exibir e modificar.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-112">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow with the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="3e0e2-113">Clique duas vezes no componente de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-113">Double-click the data flow component.</span></span>  
  
5.  <span data-ttu-id="3e0e2-114">No editor de componente, exiba ou modifique os valores de propriedade e feche o editor.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-114">In the component editor, view or modify the property values, and then close the editor.</span></span>  
  
6.  <span data-ttu-id="3e0e2-115">Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Itens Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-115">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-properties-window"></a><span data-ttu-id="3e0e2-116">Para definir as propriedades de um componente de fluxo de dados usando a janela Propriedades</span><span class="sxs-lookup"><span data-stu-id="3e0e2-116">To set the properties of a data flow component by using the Properties window</span></span>  
  
1.  <span data-ttu-id="3e0e2-117">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3e0e2-118">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3e0e2-119">Clique na guia **Fluxo de Controle** e clique duas vezes na tarefa Fluxo de Dados que contém os componentes cujas propriedades você deseja exibir e modificar.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-119">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="3e0e2-120">Clique com o botão direito do mouse no componente do fluxo de dados e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-120">Right-click the data flow component, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3e0e2-121">Exiba ou modifique os valores de propriedade e então feche a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="3e0e2-121">View or modify the property values, and then close the **Properties** window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e0e2-122">Muitas propriedades são somente leitura e não podem ser modificadas.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-122">Many properties are read-only, and cannot be modified.</span></span>  
  
6.  <span data-ttu-id="3e0e2-123">Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Itens Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-123">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-advanced-editor"></a><span data-ttu-id="3e0e2-124">Para definir as propriedades de um componente de fluxo de dados usando o Editor Avançado</span><span class="sxs-lookup"><span data-stu-id="3e0e2-124">To set the properties of a data flow component by using the Advanced Editor</span></span>  
  
1.  <span data-ttu-id="3e0e2-125">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-125">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3e0e2-126">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3e0e2-127">Clique na guia **Fluxo de Controle** e clique duas vezes na tarefa Fluxo de Dados que contém o componente que deseja exibir ou modificar.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-127">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component you want to view or modify.</span></span>  
  
4.  <span data-ttu-id="3e0e2-128">No designer de fluxo de dados, clique com o botão direito do mouse no componente de fluxo de dados e clique em **Mostrar Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-128">In the data flow designer, right-click the data flow component, and then click **Show Advanced Editor**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e0e2-129">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], os componentes de fluxo de dados que dão suporte a diversas entradas não podem usar o **Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-129">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data flow components that support multiple inputs cannot use the **Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="3e0e2-130">Na caixa de diálogo **Editor Avançado** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3e0e2-130">In the **Advanced Editor** dialog box, do any of the following steps:</span></span>  
  
    -   <span data-ttu-id="3e0e2-131">Para exibir e especificar a conexão usada pelo componente, clique na guia **Gerenciadores de Conexões** .</span><span class="sxs-lookup"><span data-stu-id="3e0e2-131">To view and specify the connection that the component uses, click the **Connection Managers** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3e0e2-132">A guia **Gerenciadores de Conexões** está disponível apenas para componentes de fluxo de dados que usam gerenciadores de conexões para se conectar com fontes de dados como arquivos e bancos de dados</span><span class="sxs-lookup"><span data-stu-id="3e0e2-132">The **Connection Managers** tab is available only to data flow components that use connection managers to connect to data sources such as files and databases</span></span>  
  
    -   <span data-ttu-id="3e0e2-133">Para exibir e modificar propriedades no nível do componente, clique na guia **Propriedades do Componente** .</span><span class="sxs-lookup"><span data-stu-id="3e0e2-133">To view and modify component-level properties, click the **Component Properties** tab.</span></span>  
  
    -   <span data-ttu-id="3e0e2-134">Para exibir ou modificar mapeamentos entre colunas externas e a saída disponível, clique na guia **Mapeamentos de Coluna** .</span><span class="sxs-lookup"><span data-stu-id="3e0e2-134">To view and modify mappings between external columns and the available output, click the **Column Mappings** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3e0e2-135">A guia **Mapeamentos de Coluna** está disponível apenas ao exibir ou editar origens ou destinos.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-135">The **Column Mappings** tab is available only when viewing or editing sources or destinations.</span></span>  
  
    -   <span data-ttu-id="3e0e2-136">Para exibir uma lista das colunas de entrada disponíveis e atualizar os nomes das colunas de saída, clique na guia **Colunas de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="3e0e2-136">To view a list of the available input columns and to update the names of output columns, click the **Input Columns** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3e0e2-137">A guia Colunas de Entrada só fica disponível ao trabalhar com transformações ou destinos.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-137">The Input Columns tab is available only when working with transformations or destinations.</span></span> <span data-ttu-id="3e0e2-138">Para obter mais informações, consulte [Integration Services Transformations](transformations/integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="3e0e2-138">For more information, see [Integration Services Transformations](transformations/integration-services-transformations.md).</span></span>  
  
    -   <span data-ttu-id="3e0e2-139">Para exibir e modificar as propriedades de entradas, saídas e saídas de erro e as propriedades das colunas que elas contêm, clique na guia **Propriedades de Entrada e Saída** .</span><span class="sxs-lookup"><span data-stu-id="3e0e2-139">To view and modify the properties of inputs, outputs, and error outputs, and the properties of the columns they contain, click the **Input and Output Properties** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3e0e2-140">Origens não têm entradas.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-140">Sources have no inputs.</span></span> <span data-ttu-id="3e0e2-141">Destinos não têm saídas, exceto uma saída de erro opcional.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-141">Destinations have no outputs, except for an optional error output.</span></span>  
  
6.  <span data-ttu-id="3e0e2-142">Exiba ou modifique os valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-142">View or modify the property values.</span></span>  
  
7.  <span data-ttu-id="3e0e2-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-143">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="3e0e2-144">Para salvar o pacote atualizado, no menu **Arquivo** , clique em **Salvar Itens Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="3e0e2-144">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e0e2-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3e0e2-145">See Also</span></span>  
 [<span data-ttu-id="3e0e2-146">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="3e0e2-146">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
