---
title: 'Etapa 2: adicionar e configurar um gerenciador de conexões de arquivo simples | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9a77dd32-d8c2-4961-ad37-2a971f9d6043
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3ba3adee2422af8b2df027f55ec84366b90ddd7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574149"
---
# <a name="step-2-adding-and-configuring-a-flat-file-connection-manager"></a><span data-ttu-id="f3b10-102">Etapa 2: Adicionar e configurar um gerenciador de conexões de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="f3b10-102">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>
  <span data-ttu-id="f3b10-103">Nesta tarefa, você adiciona um gerenciador de conexões de Arquivos Simples ao pacote que acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="f3b10-103">In this task, you add a Flat File connection manager to the package that you just created.</span></span> <span data-ttu-id="f3b10-104">Um gerenciador de conexões de Arquivos Simples habilita um pacote para extrair dados de um arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="f3b10-104">A Flat File connection manager enables a package to extract data from a flat file.</span></span> <span data-ttu-id="f3b10-105">Com o gerenciador de conexões de Arquivos Simples, você pode especificar o nome e o local do arquivo, a localidade e a página de códigos e o formato do arquivo, incluindo os delimitadores de coluna, a serem aplicados quando o pacote extrai os dados do arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="f3b10-105">Using the Flat File connection manager, you can specify the file name and location, the locale and code page, and the file format, including column delimiters, to apply when the package extracts data from the flat file.</span></span> <span data-ttu-id="f3b10-106">Além disso, é possível especificar manualmente o tipo de dados das colunas individuais ou usar a caixa de diálogo **Sugerir Tipos de Coluna** para mapear automaticamente as colunas de dados extraídos para os tipos de dados [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f3b10-106">In addition, you can manually specify the data type for the individual columns, or use the **Suggest Column Types** dialog box to automatically map the columns of extracted data to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] data types.</span></span>  
  
 <span data-ttu-id="f3b10-107">Você deve criar um novo gerenciador de conexões de Arquivos Simples para cada formato de arquivo com os quais você trabalha.</span><span class="sxs-lookup"><span data-stu-id="f3b10-107">You must create a new Flat File connection manager for each file format that you work with.</span></span> <span data-ttu-id="f3b10-108">Como este tutorial extrai dados de vários arquivos simples que apresentam exatamente o mesmo formato de dados, será preciso adicionar e configurar apenas um gerenciador de conexões de Arquivos Simples para seu pacote.</span><span class="sxs-lookup"><span data-stu-id="f3b10-108">Because this tutorial extracts data from multiple flat files that have exactly the same data format, you will need to add and configure only one Flat File connection manager for your package.</span></span>  
  
 <span data-ttu-id="f3b10-109">Neste tutorial, serão configuradas as seguintes propriedades em seu gerenciador de conexões de Arquivos Simples:</span><span class="sxs-lookup"><span data-stu-id="f3b10-109">For this tutorial, you will configure the following properties in your Flat File connection manager:</span></span>  
  
-   <span data-ttu-id="f3b10-110">**Nomes de coluna:** como o arquivo simples não tem nomes de colunas, o gerenciador de conexões de Arquivos Simples cria nomes de colunas padrão.</span><span class="sxs-lookup"><span data-stu-id="f3b10-110">**Column names:** Because the flat file does not have column names, the Flat File connection manager creates default column names.</span></span> <span data-ttu-id="f3b10-111">Estes nomes padrões não são úteis para identificar o que cada coluna representa.</span><span class="sxs-lookup"><span data-stu-id="f3b10-111">These default names are not useful for identifying what each column represents.</span></span> <span data-ttu-id="f3b10-112">Para tornar esses nomes mais úteis, altere os nomes padrão para nomes que correspondam à tabela de fatos à qual os dados do arquivo simples serão carregados.</span><span class="sxs-lookup"><span data-stu-id="f3b10-112">To make these default names more useful, you need to change the default names to names that match the fact table into which the flat file data is to be loaded.</span></span>  
  
-   <span data-ttu-id="f3b10-113">**Mapeamentos de dados:** os mapeamentos de tipo de dados especificados no gerenciador de conexões de Arquivos Simples serão usados por todos os componentes de fonte de dados de arquivos simples que fazem referência ao gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="f3b10-113">**Data mappings:** The data type mappings that you specify for the Flat File connection manager will be used by all flat file data source components that reference the connection manager.</span></span> <span data-ttu-id="f3b10-114">Os tipos de dados podem ser mapeados manualmente usando o gerenciador de conexões de Arquivos Simples ou a caixa de diálogo **Sugerir Tipos de Coluna** .</span><span class="sxs-lookup"><span data-stu-id="f3b10-114">You can either manually map the data types by using the Flat File connection manager, or you can use the **Suggest Column Types** dialog box.</span></span> <span data-ttu-id="f3b10-115">Neste tutorial, você exibirá os mapeamentos sugeridos na caixa de diálogo **Sugerir Tipos de Coluna** e fará manualmente os mapeamentos necessários na caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos Simples** .</span><span class="sxs-lookup"><span data-stu-id="f3b10-115">In this tutorial, you will view the mappings suggested in the **Suggest Column Types** dialog box and then manually make the necessary mappings in the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="f3b10-116">O gerenciador de conexões de Arquivos Simples fornece informações de localidade sobre o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="f3b10-116">The Flat File connection manager provides locale information about the data file.</span></span> <span data-ttu-id="f3b10-117">Se o computador não estiver configurado para usar a opção regional inglês (Estados Unidos), você deverá definir propriedades adicionais na caixa de diálogo **Editor do Gerenciador de conexões de arquivos simples** .</span><span class="sxs-lookup"><span data-stu-id="f3b10-117">If your computer is not configured to use the regional option English (United States), you must set additional properties in the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
### <a name="to-add-a-flat-file-connection-manager-to-the-ssis-package"></a><span data-ttu-id="f3b10-118">Para adicionar um gerenciador de conexões de arquivos simples ao pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="f3b10-118">To add a Flat File connection manager to the SSIS package</span></span>  
  
1.  <span data-ttu-id="f3b10-119">Clique com o botão direito do mouse em qualquer lugar da área **Gerenciadores de Conexões** e clique em **Nova Conexão de Arquivos Simples**.</span><span class="sxs-lookup"><span data-stu-id="f3b10-119">Right-click anywhere in the **Connection Managers** area, and then click **New Flat File Connection**.</span></span>  
  
2.  <span data-ttu-id="f3b10-120">Na caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos Simples** , em **Nome do gerenciador de conexões**, digite **Dados de Origem de Arquivos Simples de Exemplo**.</span><span class="sxs-lookup"><span data-stu-id="f3b10-120">In the **Flat File Connection Manager Editor** dialog box, for **Connection manager name**, type **Sample Flat File Source Data**.</span></span>  
  
3.  <span data-ttu-id="f3b10-121">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="f3b10-121">Click **Browse**.</span></span>  
  
4.  <span data-ttu-id="f3b10-122">Na caixa de diálogo **Abrir** , localize o arquivo SampleCurrencyData.txt no computador.</span><span class="sxs-lookup"><span data-stu-id="f3b10-122">In the **Open** dialog box, locate the SampleCurrencyData.txt file on your machine.</span></span>  
  
     <span data-ttu-id="f3b10-123">Os dados de exemplo estão incluídos com os pacotes de lição do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f3b10-123">The sample data is included with the [!INCLUDE[ssIS](../includes/ssis-md.md)] lesson packages.</span></span> <span data-ttu-id="f3b10-124">Para baixar os dados de exemplo e os pacotes de lição, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="f3b10-124">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="f3b10-125">Navegue para os [Exemplos de Produtos do Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="f3b10-125">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="f3b10-126">Clique na guia **downloads** .</span><span class="sxs-lookup"><span data-stu-id="f3b10-126">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="f3b10-127">Clique no arquivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="f3b10-127">Click the  SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="f3b10-128">Desmarque os nomes de coluna na caixa de seleção da primeira linha de dados.</span><span class="sxs-lookup"><span data-stu-id="f3b10-128">Clear the Column names in the first data row checkbox.</span></span>  
  
### <a name="to-set-locale-sensitive-properties"></a><span data-ttu-id="f3b10-129">Definir propriedades com distinção de localidade</span><span class="sxs-lookup"><span data-stu-id="f3b10-129">To set locale sensitive properties</span></span>  
  
1.  <span data-ttu-id="f3b10-130">Na caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos Simples** , clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="f3b10-130">In the **Flat File Connection Manager Editor** dialog box, click **General**.</span></span>  
  
2.  <span data-ttu-id="f3b10-131">Defina a **localidade** como inglês (Estados Unidos) e a **página de código** como 1252.</span><span class="sxs-lookup"><span data-stu-id="f3b10-131">Set **Locale** to English (United States) and **Code page** to 1252.</span></span>  
  
### <a name="to-rename-columns-in-the-flat-file-connection-manager"></a><span data-ttu-id="f3b10-132">Renomear colunas no gerenciador de conexões de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="f3b10-132">To rename columns in the Flat File connection manager</span></span>  
  
1.  <span data-ttu-id="f3b10-133">Na caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos Simples** , clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="f3b10-133">In the **Flat File Connection Manager Editor** dialog box, click **Advanced**.</span></span>  
  
2.  <span data-ttu-id="f3b10-134">No painel de propriedade, faça as seguintes alterações:</span><span class="sxs-lookup"><span data-stu-id="f3b10-134">In the property pane, make the following changes:</span></span>  
  
    -   <span data-ttu-id="f3b10-135">Altere a propriedade de nome da **coluna 0** para `AverageRate` .</span><span class="sxs-lookup"><span data-stu-id="f3b10-135">Change the **Column 0** name property to `AverageRate`.</span></span>  
  
    -   <span data-ttu-id="f3b10-136">Altere a propriedade de nome da **coluna 1** para `CurrencyID` .</span><span class="sxs-lookup"><span data-stu-id="f3b10-136">Change the **Column 1** name property to `CurrencyID`.</span></span>  
  
    -   <span data-ttu-id="f3b10-137">Altere a propriedade de nome da **coluna 2** para `CurrencyDate` .</span><span class="sxs-lookup"><span data-stu-id="f3b10-137">Change the **Column 2** name property to `CurrencyDate`.</span></span>  
  
    -   <span data-ttu-id="f3b10-138">Altere a propriedade de nome da **coluna 3** para `EndOfDayRate` .</span><span class="sxs-lookup"><span data-stu-id="f3b10-138">Change the **Column 3** name property to `EndOfDayRate`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f3b10-139">Por padrão, as quatro colunas são definidas inicialmente como um tipo de dados de cadeia de caracteres [DT_STR] com uma `OutputColumnWidth` de 50.</span><span class="sxs-lookup"><span data-stu-id="f3b10-139">By default, all four of the columns are initially set to a string data type [DT_STR] with an `OutputColumnWidth` of 50.</span></span>  
  
### <a name="to-remap-column-data-types"></a><span data-ttu-id="f3b10-140">Remapear tipos de dados de coluna</span><span class="sxs-lookup"><span data-stu-id="f3b10-140">To remap column data types</span></span>  
  
1.  <span data-ttu-id="f3b10-141">Na caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos Simples** , clique em **Sugerir Tipos**.</span><span class="sxs-lookup"><span data-stu-id="f3b10-141">In the **Flat File Connection Manager Editor** dialog box, click **Suggest Types**.</span></span>  
  
     [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f3b10-142">sugere automaticamente os tipos de dados mais apropriados com base nas primeiras 200 linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="f3b10-142">automatically suggests the most appropriate data types based on the first 200 rows of data.</span></span> <span data-ttu-id="f3b10-143">Também é possível alterar essas opções de sugestão para mostrar mais ou menos dados, para especificar o tipo de dados padrão para dados inteiro ou booliano, ou para adicionar espaços como preenchimento das colunas de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f3b10-143">You can also change these suggestion options to sample more or less data, to specify the default data type for integer or Boolean data, or to add spaces as padding to string columns.</span></span>  
  
     <span data-ttu-id="f3b10-144">Por enquanto, não faça alterações nas opções na caixa de diálogo **Sugerir Tipos de Coluna** e clique em **OK** para que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sugira os tipos de dados para as colunas.</span><span class="sxs-lookup"><span data-stu-id="f3b10-144">For now, make no changes to the options in the **Suggest Column Types** dialog box, and click **OK** to have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] suggest data types for columns.</span></span> <span data-ttu-id="f3b10-145">Esse procedimento retornará o painel **Avançado** da caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos Simples** , em que é possível exibir os tipos de dados de coluna sugeridos pelo [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3b10-145">This returns you to the **Advanced** pane of the **Flat File Connection Manager Editor** dialog box, where you can view the column data types suggested by [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f3b10-146">(Se você clicar em **Cancelar**, nenhuma sugestão será indicada para os metadados da coluna e o tipo de dados da cadeia de caracteres padrão [DT_STR] será usado.)</span><span class="sxs-lookup"><span data-stu-id="f3b10-146">(If you click **Cancel**, no suggestions are made to column metadata and the default string (DT_STR) data type is used.)</span></span>  
  
     <span data-ttu-id="f3b10-147">Neste tutorial, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sugere os tipos de dados mostrados na segunda coluna da tabela a seguir referentes aos dados do arquivo SampleCurrencyData.txt.</span><span class="sxs-lookup"><span data-stu-id="f3b10-147">In this tutorial, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] suggests the data types shown in the second column of the following table for the data from the SampleCurrencyData.txt file.</span></span> <span data-ttu-id="f3b10-148">Entretanto, os tipos de dados que forem necessários para as colunas no destino, que serão definidos em uma etapa futura, serão mostrados na última coluna da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f3b10-148">However, the data types that are required for the columns in the destination, which will be defined in a later step, are shown in the last column of the following table.</span></span>  
  
    |<span data-ttu-id="f3b10-149">Coluna de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="f3b10-149">Flat File Column</span></span>|<span data-ttu-id="f3b10-150">Tipo Sugerido</span><span class="sxs-lookup"><span data-stu-id="f3b10-150">Suggested Type</span></span>|<span data-ttu-id="f3b10-151">Coluna de Destino</span><span class="sxs-lookup"><span data-stu-id="f3b10-151">Destination Column</span></span>|<span data-ttu-id="f3b10-152">Tipo de Destino</span><span class="sxs-lookup"><span data-stu-id="f3b10-152">Destination Type</span></span>|  
    |----------------------|--------------------|------------------------|----------------------|  
    |<span data-ttu-id="f3b10-153">AverageRate</span><span class="sxs-lookup"><span data-stu-id="f3b10-153">AverageRate</span></span>|<span data-ttu-id="f3b10-154">float [DT_R4]</span><span class="sxs-lookup"><span data-stu-id="f3b10-154">float [DT_R4]</span></span>|<span data-ttu-id="f3b10-155">FactCurrency.AverageRate</span><span class="sxs-lookup"><span data-stu-id="f3b10-155">FactCurrency.AverageRate</span></span>|<span data-ttu-id="f3b10-156">FLOAT</span><span class="sxs-lookup"><span data-stu-id="f3b10-156">float</span></span>|  
    |<span data-ttu-id="f3b10-157">CurrencyID</span><span class="sxs-lookup"><span data-stu-id="f3b10-157">CurrencyID</span></span>|<span data-ttu-id="f3b10-158">string [DT_STR]</span><span class="sxs-lookup"><span data-stu-id="f3b10-158">string [DT_STR]</span></span>|<span data-ttu-id="f3b10-159">DimCurrency.CurrencyAlternateKey</span><span class="sxs-lookup"><span data-stu-id="f3b10-159">DimCurrency.CurrencyAlternateKey</span></span>|<span data-ttu-id="f3b10-160">nchar(3)</span><span class="sxs-lookup"><span data-stu-id="f3b10-160">nchar(3)</span></span>|  
    |<span data-ttu-id="f3b10-161">CurrencyDate</span><span class="sxs-lookup"><span data-stu-id="f3b10-161">CurrencyDate</span></span>|<span data-ttu-id="f3b10-162">date [DT_DATE]</span><span class="sxs-lookup"><span data-stu-id="f3b10-162">date [DT_DATE]</span></span>|<span data-ttu-id="f3b10-163">DimDate.FullDateAlternateKey</span><span class="sxs-lookup"><span data-stu-id="f3b10-163">DimDate.FullDateAlternateKey</span></span>|<span data-ttu-id="f3b10-164">date</span><span class="sxs-lookup"><span data-stu-id="f3b10-164">date</span></span>|  
    |<span data-ttu-id="f3b10-165">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="f3b10-165">EndOfDayRate</span></span>|<span data-ttu-id="f3b10-166">float [DT_R4]</span><span class="sxs-lookup"><span data-stu-id="f3b10-166">float [DT_R4]</span></span>|<span data-ttu-id="f3b10-167">FactCurrency.EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="f3b10-167">FactCurrency.EndOfDayRate</span></span>|<span data-ttu-id="f3b10-168">FLOAT</span><span class="sxs-lookup"><span data-stu-id="f3b10-168">float</span></span>|  
  
     <span data-ttu-id="f3b10-169">O tipo de dados sugerido para a `CurrencyID` coluna é incompatível com o tipo de dados do campo na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="f3b10-169">The data type suggested for the `CurrencyID` column is incompatible with the data type of the field in the destination table.</span></span> <span data-ttu-id="f3b10-170">Como o tipo de dados de `DimCurrency.CurrencyAlternateKey` é nchar (3), `CurrencyID` deve ser alterado de cadeia de caracteres [DT_STR] para cadeia de caracteres [DT_WSTR].</span><span class="sxs-lookup"><span data-stu-id="f3b10-170">Because the data type of `DimCurrency.CurrencyAlternateKey` is nchar (3), `CurrencyID` must be changed from string [DT_STR] to string [DT_WSTR].</span></span> <span data-ttu-id="f3b10-171">Além disso, o campo `DimDate.FullDateAlternateKey` é definido como um tipo de dados de data; portanto, é necessário alterá-lo `CurrencyDate` da data [DT_DATE] para a data do banco de dado [DT_DBDATE].</span><span class="sxs-lookup"><span data-stu-id="f3b10-171">Additionally, the field `DimDate.FullDateAlternateKey` is defined as a date data type; therefore, `CurrencyDate` needs to be changed from date [DT_Date] to database date [DT_DBDATE].</span></span>  
  
2.  <span data-ttu-id="f3b10-172">Na lista, selecione a coluna CurrencyID e, no painel Propriedade, altere o tipo de dados da coluna `CurrencyID` da cadeia de caracteres [DT_STR] para cadeia de caracteres Unicode [DT_WSTR].</span><span class="sxs-lookup"><span data-stu-id="f3b10-172">In the list, select the CurrencyID column and in the property pane, change the Data Type of column `CurrencyID` from string [DT_STR] to Unicode string [DT_WSTR].</span></span>  
  
3.  <span data-ttu-id="f3b10-173">No painel Propriedade, altere o tipo de dados da coluna `CurrencyDate` de data [DT_DATE] para data do banco de dado [DT_DBDATE].</span><span class="sxs-lookup"><span data-stu-id="f3b10-173">In the property pane, change the data type of column `CurrencyDate` from date [DT_DATE] to database date [DT_DBDATE].</span></span>  
  
4.  <span data-ttu-id="f3b10-174">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b10-174">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f3b10-175">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="f3b10-175">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f3b10-176">Etapa 3: Adicionar e configurar um gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="f3b10-176">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>](lesson-1-3-adding-and-configuring-an-ole-db-connection-manager.md)  
  
## <a name="see-also"></a><span data-ttu-id="f3b10-177">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f3b10-177">See Also</span></span>  
 <span data-ttu-id="f3b10-178">[Gerenciador de conexões de arquivos simples](connection-manager/file-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f3b10-178">[Flat File Connection Manager](connection-manager/file-connection-manager.md) </span></span>  
 [<span data-ttu-id="f3b10-179">Tipos de dados do Integration Services</span><span class="sxs-lookup"><span data-stu-id="f3b10-179">Integration Services Data Types</span></span>](data-flow/integration-services-data-types.md)  
  
  