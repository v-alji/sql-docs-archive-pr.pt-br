---
title: 'Tarefa 6: adicionando a origem do Excel ao fluxo de dados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0209055e-cb6b-4a07-909e-836596727a2c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ae183dee04619a407655026a49b189f7bb3ac6fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581637"
---
# <a name="task-6-adding-excel-source-to-the-data-flow"></a><span data-ttu-id="79ba7-102">Tarefa 6: Adicionando a origem do Excel ao fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="79ba7-102">Task 6: Adding Excel Source to the Data Flow</span></span>
  <span data-ttu-id="79ba7-103">Nesta tarefa, você adicionará uma Origem do Excel ao fluxo de dados para ler dados do fornecedor do arquivo de origem do Excel.</span><span class="sxs-lookup"><span data-stu-id="79ba7-103">In this task, you add an Excel Source to the data flow to read supplier data from the source Excel file.</span></span> <span data-ttu-id="79ba7-104">A Origem do Excel extrai dados de planilhas ou intervalos em pastas de trabalho do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="79ba7-104">The Excel Source extracts data from worksheets or ranges in Microsoft Excel workbooks.</span></span> <span data-ttu-id="79ba7-105">Consulte o tópico [Origem do Excel](../integration-services/data-flow/excel-source.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="79ba7-105">See [Excel Source](../integration-services/data-flow/excel-source.md) topic for more details.</span></span>

1.  <span data-ttu-id="79ba7-106">Arraste e solte **Origem do Excel** de **Outras Origens** na **Caixa de Ferramentas do SSIS** para a guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="79ba7-106">Drag-drop **Excel Source** from **Other Sources** in **SSIS Toolbox** to the **Data Flow** tab.</span></span>

2.  <span data-ttu-id="79ba7-107">Clique com o botão direito do mouse em **Origem do Excel** na guia **Fluxo de Dados** e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="79ba7-107">Right-click on **Excel Source** in the **Data Flow** tab, and click **Rename**.</span></span>

3.  <span data-ttu-id="79ba7-108">Digite **Ler Dados do Fornecedor de Arquivo do Excel** e pressione **ENTER**.</span><span class="sxs-lookup"><span data-stu-id="79ba7-108">Type **Read Supplier Data from Excel File** and press **ENTER**.</span></span>

4.  <span data-ttu-id="79ba7-109">Clique duas vezes em **Ler Dados do Fornecedor de Arquivo do Excel** para iniciar a caixa de diálogo de **Editor de Origem do Excel** .</span><span class="sxs-lookup"><span data-stu-id="79ba7-109">Double-click **Read Supplier Data from Excel File** to launch the **Excel Source Editor** dialog box.</span></span>

5.  <span data-ttu-id="79ba7-110">Na caixa de diálogo **Editor de Origem do Excel** , clique em **Novo** para criar uma conexão do Excel.</span><span class="sxs-lookup"><span data-stu-id="79ba7-110">In the **Excel Source Editor** dialog box, click **New** to create an Excel connection.</span></span>

6.  <span data-ttu-id="79ba7-111">Na caixa de diálogo **Gerenciador de Conexões do Excel** , clique em **Procurar**e selecione o arquivo **Suppliers.xls** na pasta **Tutorial do EIM** .</span><span class="sxs-lookup"><span data-stu-id="79ba7-111">In the **Excel Connection Manager** dialog box, click **Browse**, and then select the **Suppliers.xls** file in the **EIM Tutorial** folder.</span></span> <span data-ttu-id="79ba7-112">Confirme se a opção **Microsoft Excel 97-2003** está selecionada na caixa **Versão do Excel** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79ba7-112">Confirm that **Microsoft Excel 97-2003** is selected in the **Excel Version** box and then click **OK**.</span></span>

     <span data-ttu-id="79ba7-113">![Caixa de diálogo Gerenciador de Conexões do Excel](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Caixa de diálogo Gerenciador de Conexões do Excel")</span><span class="sxs-lookup"><span data-stu-id="79ba7-113">![Excel Connection Manager Dialog Box](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Excel Connection Manager Dialog Box")</span></span>

7.  <span data-ttu-id="79ba7-114">Na caixa de diálogo **Editor de Origem do Excel** , selecione **IncomingSuppliers$** na caixa de listagem **Nome da planilha do Excel** .</span><span class="sxs-lookup"><span data-stu-id="79ba7-114">In the **Excel Source Editor** dialog box, select **IncomingSuppliers$** in the **Name of the Excel sheet** list box.</span></span>

     <span data-ttu-id="79ba7-115">![Nome da planilha do Excel - Fornecedores de Entrada$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Nome da planilha do Excel - Fornecedores de Entrada$")</span><span class="sxs-lookup"><span data-stu-id="79ba7-115">![Name of Excel Sheet - Incoming Suppliers$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Name of Excel Sheet - Incoming Suppliers$")</span></span>

8.  <span data-ttu-id="79ba7-116">Clique em **Visualizar** para visualizar os dados no arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="79ba7-116">Click **Preview** to preview the data in Excel file.</span></span>

9. <span data-ttu-id="79ba7-117">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="79ba7-117">Click **OK** to close the dialog box.</span></span>

10. <span data-ttu-id="79ba7-118">Arraste e solte a transformação **Limpeza DQS** em **Outras Transformações** na **Caixa de Ferramentas do SSIS** para a guia **Fluxo de Dados** em **Ler Dados do Fornecedor de Arquivo do Excel**.</span><span class="sxs-lookup"><span data-stu-id="79ba7-118">Drag-drop **DQS Cleansing** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Read Supplier Data from Excel File**.</span></span> <span data-ttu-id="79ba7-119">A transformação Limpeza DQS usa o DQS (Data Quality Services) para corrigir dados aplicando regras aprovadas na base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="79ba7-119">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data by applying approved rules in the knowledge base.</span></span> <span data-ttu-id="79ba7-120">Essa transformação, em runtime, cria um projeto de limpeza DQS no servidor DQS.</span><span class="sxs-lookup"><span data-stu-id="79ba7-120">This transform, at runtime, creates a DQS cleansing project on the DQS server.</span></span> <span data-ttu-id="79ba7-121">Consulte o tópico [Transformação Limpeza DQS](https://msdn.microsoft.com/library/ee677619.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="79ba7-121">See [DQS Cleansing Transformation](https://msdn.microsoft.com/library/ee677619.aspx) topic for more details.</span></span>

## <a name="next-step"></a><span data-ttu-id="79ba7-122">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="79ba7-122">Next Step</span></span>

[<span data-ttu-id="79ba7-123">Tarefa 7: Adicionando a Transformação de Limpeza DQS ao fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="79ba7-123">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>](task-7-adding-dqs-cleansing-transform-to-the-data-flow.md)

### <a name="see-also"></a><span data-ttu-id="79ba7-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79ba7-124">See Also</span></span>

[<span data-ttu-id="79ba7-125">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="79ba7-125">Data Flow</span></span>](../integration-services/data-flow/data-flow.md)
