---
title: 'Etapa 6: Adicionando e configurando a transformação Pesquisa | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c59f723-9707-4407-80ae-f05f483cf65f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96b0a848508c19eb24cf1538244a39fcec57361a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574130"
---
# <a name="step-6-adding-and-configuring-the-lookup-transformations"></a><span data-ttu-id="34146-102">Etapa 6: Adicionar e configurar a transformação Pesquisa</span><span class="sxs-lookup"><span data-stu-id="34146-102">Step 6: Adding and Configuring the Lookup Transformations</span></span>
  <span data-ttu-id="34146-103">Depois de configurar a fonte de Arquivo Simples para extrair dados do arquivo de origem, a próxima tarefa será definir as transformações Pesquisa necessárias para obter os valores de **CurrencyKey** e **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="34146-103">After you have configured the Flat File source to extract data from the source file, the next task is to define the Lookup transformations needed to obtain the values for the **CurrencyKey** and **DateKey**.</span></span> <span data-ttu-id="34146-104">Uma transformação Pesquisa executa uma pesquisa ao unir dados na entrada coluna para uma coluna especificada em um conjunto de dados referenciado.</span><span class="sxs-lookup"><span data-stu-id="34146-104">A Lookup transformation performs a lookup by joining data in the specified input column to a column in a reference dataset.</span></span> <span data-ttu-id="34146-105">O conjunto de dados de referência pode ser uma tabela existente ou visualização, uma nova tabela ou o resultado de uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="34146-105">The reference dataset can be an existing table or view, a new table, or the result of an SQL statement.</span></span> <span data-ttu-id="34146-106">Neste tutorial, a transformação Pesquisa usa um gerenciador de conexões OLE DB para conectar-se ao banco de dados que contém os dados que é a fonte do conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="34146-106">In this tutorial, the Lookup transformation uses an OLE DB connection manager to connect to the database that contains the data that is the source of the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34146-107">Você também pode configurar a transformação Pesquisa para conectar-se a um cache que contém o conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="34146-107">You can also configure the Lookup transformation to connect to a cache that contains the reference dataset.</span></span> <span data-ttu-id="34146-108">Para obter mais informações, consulte [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="34146-108">For more information, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="34146-109">Para este tutorial, você irá adicionar e configurar os dois componentes de transformações Pesquisa a seguir para o pacote:</span><span class="sxs-lookup"><span data-stu-id="34146-109">For this tutorial, you will add and configure the following two Lookup transformation components to the package:</span></span>  
  
-   <span data-ttu-id="34146-110">Uma transformação para executar uma pesquisa de valores na coluna **CurrencyKey** da tabela de dimensões **DimCurrency** baseada nos valores da coluna **CurrencyID** correspondentes do arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="34146-110">One transformation to perform a lookup of values from the **CurrencyKey** column of the **DimCurrency** dimension table based on matching **CurrencyID** column values from the flat file.</span></span>  
  
-   <span data-ttu-id="34146-111">Uma transformação para executar uma pesquisa de valores na coluna **DateKey** da tabela de dimensões **DimDate** baseada nos valores da coluna **CurrencyDate** correspondentes do arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="34146-111">One transformation to perform a lookup of values from the **DateKey** column of the **DimDate** dimension table based on matching **CurrencyDate** column values from the flat file.</span></span>  
  
 <span data-ttu-id="34146-112">Em ambos os casos, a transformação Pesquisa utilizará o gerenciador de conexões OLE DB que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="34146-112">In both cases, the Lookup transformation will utilize the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-lookup-currency-key-transformation"></a><span data-ttu-id="34146-113">Para adicionar e configurar a transformação Código de Moeda da Pesquisa</span><span class="sxs-lookup"><span data-stu-id="34146-113">To add and configure the Lookup Currency Key transformation</span></span>  
  
1.  <span data-ttu-id="34146-114">Na **caixa de ferramentas do SSIS**, expanda **comum**e, em seguida, arraste **pesquisa** para a superfície de design da guia **fluxo de dados** . Coloque a pesquisa diretamente abaixo da fonte de **dados extrair exemplo de moeda** .</span><span class="sxs-lookup"><span data-stu-id="34146-114">In the **SSIS Toolbox**, expand **Common**, and then drag **Lookup** onto the design surface of the **Data Flow** tab. Place Lookup directly below the **Extract Sample Currency Data** source.</span></span>  
  
2.  <span data-ttu-id="34146-115">Clique na fonte de arquivo simples **Extrair Dados de Exemplo de Moeda** e arraste a seta verde para a transformação **Pesquisa** recém-adicionada, para poder conectar assim os dois componentes.</span><span class="sxs-lookup"><span data-stu-id="34146-115">Click the **Extract Sample Currency Data** flat file source and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="34146-116">Na superfície de design de **Fluxo de Dados** , clique em **Pesquisa** na transformação **Pesquisa** e altere o nome para **Pesquisa de Código de Moeda**.</span><span class="sxs-lookup"><span data-stu-id="34146-116">On the **Data Flow** design surface, click **Lookup** in the **Lookup** transformation, and change the name to **Lookup Currency Key**.</span></span>  
  
4.  <span data-ttu-id="34146-117">Clique duas vezes na transformação **Chave de Moeda de Pesquisa** para exibir o Editor de Transformação Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="34146-117">Double-click the **Lookup CurrencyKey** transformation to display the Lookup Transformation Editor.</span></span>  
  
5.  <span data-ttu-id="34146-118">Na página **Geral** , faça as seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="34146-118">On the **General** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="34146-119">Selecione **Cache cheio**.</span><span class="sxs-lookup"><span data-stu-id="34146-119">Select **Full cache**.</span></span>  
  
    2.  <span data-ttu-id="34146-120">Na área **Tipo de conexão** , selecione **Gerenciador de conexões OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="34146-120">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
6.  <span data-ttu-id="34146-121">Na página **Conexão** , faça as seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="34146-121">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="34146-122">Na caixa de diálogo **Gerenciador de Conexões OLE DB** , verifique se **localhost.AdventureWorksDW2012** está exibido.</span><span class="sxs-lookup"><span data-stu-id="34146-122">In the **OLE DB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="34146-123">Selecione **Usar os resultados de uma consulta SQL**e digite ou copie a seguinte instrução SQL:</span><span class="sxs-lookup"><span data-stu-id="34146-123">Select **Use results of an SQL query**, and then type or copy the following SQL statement:</span></span>  
  
        ```  
        select * from (select * from [dbo].[DimCurrency]) as refTable  
        where [refTable].[CurrencyAlternateKey] = 'ARS'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'AUD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'BRL'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CAD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CNY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'DEM'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'EUR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'FRF'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'GBP'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'JPY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'MXN'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'SAR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'USD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'VEB'  
        ```  
  
7.  <span data-ttu-id="34146-124">Na página **Colunas** , faça as seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="34146-124">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="34146-125">No painel **Colunas de Entrada Disponíveis** , arraste **CurrencyID** para o painel **Colunas de Pesquisa Disponíveis** e solte em **CurrencyAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="34146-125">In the **Available Input Columns** panel, drag **CurrencyID** to the **Available Lookup Columns** panel and drop it on **CurrencyAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="34146-126">Na lista **Colunas de Pesquisa Disponíveis** , marque a caixa de seleção à esquerda de **CurrencyKey**.</span><span class="sxs-lookup"><span data-stu-id="34146-126">In the **Available Lookup Columns** list, select the check box to the left of **CurrencyKey**.</span></span>  
  
8.  <span data-ttu-id="34146-127">Clique em **OK** para retornar à superfície de design **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="34146-127">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
9. <span data-ttu-id="34146-128">Clique com o botão direito do mouse na transformação Chave de Moeda de Pesquisa e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="34146-128">Right-click the Lookup Currency Key transformation, click **Properties**.</span></span>  
  
10. <span data-ttu-id="34146-129">No janela Propriedades, verifique se a `LocaleID` propriedade está definida como **inglês (Estados Unidos)** e se a propriedade **DefaultCodePage** está definida como **1252**.</span><span class="sxs-lookup"><span data-stu-id="34146-129">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
### <a name="to-add-and-configure-the--lookup-datekey-transformation"></a><span data-ttu-id="34146-130">Para adicionar e configurar a transformação Pesquisa de Chave de Data</span><span class="sxs-lookup"><span data-stu-id="34146-130">To add and configure the  Lookup DateKey transformation</span></span>  
  
1.  <span data-ttu-id="34146-131">Na **Caixa de Ferramentas do SSIS**, arraste **Pesquisa** até a superfície de design **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="34146-131">In the **SSIS Toolbox**, drag **Lookup** onto the **Data Flow** design surface.</span></span> <span data-ttu-id="34146-132">Coloque Pesquisa diretamente abaixo da transformação **Pesquisa de Códigos de Moeda** .</span><span class="sxs-lookup"><span data-stu-id="34146-132">Place Lookup directly below the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="34146-133">Clique na transformação **Pesquisa de Código de Moeda** e depois arraste a seta verde para a transformação **Pesquisa** recém-adicionada para conectar os dois componentes.</span><span class="sxs-lookup"><span data-stu-id="34146-133">Click the **Lookup Currency Key** transformation and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="34146-134">Na caixa de diálogo **Seleção de Saída e Entrada** , clique em **Saída de Correspondência de Pesquisa** na caixa de listagem **Saída** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="34146-134">In the **Input Output Selection** dialog box, click **Lookup Match Output** in the **Output** list box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="34146-135">Na superfície de design **Fluxo de Dados** , clique em **Pesquisa** na transformação **Pesquisa** recém-adicionada e altere o nome para **Pesquisa de Códigos de Data**.</span><span class="sxs-lookup"><span data-stu-id="34146-135">On the **Data Flow** design surface, click **Lookup** in the newly added **Lookup** transformation, and change the name to **Lookup Date Key**.</span></span>  
  
5.  <span data-ttu-id="34146-136">Clique duas vezes na transformação **Chave de Data de Pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="34146-136">Double-click the **Lookup Date Key** transformation.</span></span>  
  
6.  <span data-ttu-id="34146-137">Na página **Geral** , selecione **Cache parcial**.</span><span class="sxs-lookup"><span data-stu-id="34146-137">On the **General** page, select **Partial cache**.</span></span>  
  
7.  <span data-ttu-id="34146-138">Na página **Conexão** , faça as seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="34146-138">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="34146-139">Na caixa de diálogo **Gerenciador de conexões OLE DB** , verifique se **localhost.AdventureWorksDW2012** é exibido.</span><span class="sxs-lookup"><span data-stu-id="34146-139">In the **OLEDB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="34146-140">Na caixa **Usar uma tabela ou exibição** , digite ou selecione **[dbo].[DimDate]**.</span><span class="sxs-lookup"><span data-stu-id="34146-140">In the **Use a table or view** box, type or select **[dbo].[DimDate]**.</span></span>  
  
8.  <span data-ttu-id="34146-141">Na página **Colunas** , faça as seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="34146-141">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="34146-142">No painel **Colunas de Entrada Disponíveis** , arraste **CurrencyDate** para o painel **Colunas de Pesquisa Disponíveis** e solte em **FullDateAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="34146-142">In the **Available Input Columns** panel, drag **CurrencyDate** to the **Available Lookup Columns** panel and drop it on **FullDateAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="34146-143">Na lista **Colunas de Pesquisa Disponíveis** , marque a caixa de seleção à esquerda de **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="34146-143">In the **Available Lookup Columns** list, select the check box to the left of **DateKey**.</span></span>  
  
9. <span data-ttu-id="34146-144">Na página **Avançado** , examine as opções de cache.</span><span class="sxs-lookup"><span data-stu-id="34146-144">On the **Advanced** page, review the caching options.</span></span>  
  
10. <span data-ttu-id="34146-145">Clique em **OK** para retornar à superfície de design **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="34146-145">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
11. <span data-ttu-id="34146-146">Clique com o botão direito do mouse na transformação Chave de Data de Pesquisa e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="34146-146">Right-click the Lookup Date Key transformation and click **Properties.**</span></span>  
  
12. <span data-ttu-id="34146-147">No janela Propriedades, verifique se a `LocaleID` propriedade está definida como **inglês (Estados Unidos)** e se a propriedade **DefaultCodePage** está definida como **1252**.</span><span class="sxs-lookup"><span data-stu-id="34146-147">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="34146-148">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="34146-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="34146-149">Etapa 7: Adicionar e configurar o destino OLE DB</span><span class="sxs-lookup"><span data-stu-id="34146-149">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
## <a name="see-also"></a><span data-ttu-id="34146-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34146-150">See Also</span></span>  
 [<span data-ttu-id="34146-151">Transformação Pesquisa</span><span class="sxs-lookup"><span data-stu-id="34146-151">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
