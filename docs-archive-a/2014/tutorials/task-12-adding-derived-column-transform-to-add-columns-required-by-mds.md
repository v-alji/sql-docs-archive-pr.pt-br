---
title: 'Tarefa 12: adicionando a transformação de coluna derivada para adicionar colunas exigidas pelo MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 98ccb271-04da-4126-9729-67e9a479aaef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a4a70dd4d288e425beb2821f6b2aaf440b1d1930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681956"
---
# <a name="task-12-adding-derived-column-transform-to-add-columns-required-by-mds"></a><span data-ttu-id="155f1-102">Tarefa 12: Adicionando a Transformação Coluna Derivada para adicionar as colunas necessárias pelo MDS</span><span class="sxs-lookup"><span data-stu-id="155f1-102">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>
  <span data-ttu-id="155f1-103">Nesta tarefa, você adiciona a Transformação Coluna Derivada ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="155f1-103">In this task, you add the Derive Column Transform to the data flow.</span></span> <span data-ttu-id="155f1-104">Você adiciona duas colunas derivadas, **importType** e **BatchTag**, aos registros passados para essa transformação.</span><span class="sxs-lookup"><span data-stu-id="155f1-104">You add two derived columns, **ImportType** and **BatchTag**, to the records passed to this transform.</span></span> <span data-ttu-id="155f1-105">Você deve adicionar essas colunas antes de carregar os dados nas tabelas de preparo no MDS.</span><span class="sxs-lookup"><span data-stu-id="155f1-105">You should add these columns before uploading the data to staging tables in MDS.</span></span> <span data-ttu-id="155f1-106">Esses duas colunas são necessárias para as tabelas de preparo no MDS.</span><span class="sxs-lookup"><span data-stu-id="155f1-106">These two are required columns for the staging tables in MDS.</span></span> <span data-ttu-id="155f1-107">Consulte [tabelas de preparo de membro folha](../master-data-services/leaf-member-staging-table-master-data-services.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="155f1-107">See [Leaf Member Staging Tables](../master-data-services/leaf-member-staging-table-master-data-services.md) for more details.</span></span>  
  
1.  <span data-ttu-id="155f1-108">Arraste e solte a **coluna derivada Transform** de uma seção **comum** na **caixa de ferramentas do SSIS** para a guia fluxo de **dados** .</span><span class="sxs-lookup"><span data-stu-id="155f1-108">Drag-drop **Derived Column transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="155f1-109">Clique com o botão direito do mouse em transformação de **coluna derivada** na guia **fluxo de dados** e clique em **renomear**.</span><span class="sxs-lookup"><span data-stu-id="155f1-109">Right-click **Derived Column** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="155f1-110">Digite **adicionar colunas exigidas pelo MDS** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="155f1-110">Type **Add Columns Required by MDS** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="155f1-111">Conecte as **duplicatas do filtro** para **adicionar colunas exigidas pelo MDS** usando o conector azul.</span><span class="sxs-lookup"><span data-stu-id="155f1-111">Connect **Filter Duplicates** to **Add Columns Required by MDS** using the blue connector.</span></span> <span data-ttu-id="155f1-112">Você deverá ver a caixa de diálogo **seleção de saída de entrada** .</span><span class="sxs-lookup"><span data-stu-id="155f1-112">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="155f1-113">Na caixa de diálogo **seleção de saída de entrada** , selecione **registros exclusivos**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="155f1-113">In the **Input Output Selection** dialog box, select **Unique Records**, and click **OK**.</span></span>  
  
     <span data-ttu-id="155f1-114">![Caixa de diálogo Seleção de Saída e Entrada](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Caixa de diálogo Seleção de Saída e Entrada")</span><span class="sxs-lookup"><span data-stu-id="155f1-114">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="155f1-115">Clique em **SSIS** na barra de menus e clique em **variáveis**.</span><span class="sxs-lookup"><span data-stu-id="155f1-115">Click **SSIS** on the menu bar and click **Variables**.</span></span>  
  
6.  <span data-ttu-id="155f1-116">Na janela **variáveis** , clique no botão **Adicionar variável** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="155f1-116">In the **Variables** window, click **Add Variable** button on the toolbar.</span></span>  
  
     <span data-ttu-id="155f1-117">![Janela Variáveis do SSIS](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "Janela Variáveis do SSIS")</span><span class="sxs-lookup"><span data-stu-id="155f1-117">![SSIS Variables Window](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "SSIS Variables Window")</span></span>  
  
7.  <span data-ttu-id="155f1-118">Digite **importType** para o **nome** e **2** para o **valor**.</span><span class="sxs-lookup"><span data-stu-id="155f1-118">Type **ImportType** for the **Name** and **2** for the **value**.</span></span> <span data-ttu-id="155f1-119">Você especifica o valor como 2 porque deseja adicionar novos membros a uma entidade no MDS.</span><span class="sxs-lookup"><span data-stu-id="155f1-119">You specify the value as 2 because you want to add new members to an entity in MDS.</span></span> <span data-ttu-id="155f1-120">Para obter detalhes sobre esse parâmetro, consulte [tabela de preparo de membros folha](../master-data-services/leaf-member-staging-table-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="155f1-120">For details about this parameter, see [Leaf Member Staging Table](../master-data-services/leaf-member-staging-table-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="155f1-121">Clique no botão Adicionar barra de ferramentas **variável** novamente.</span><span class="sxs-lookup"><span data-stu-id="155f1-121">Click **Add Variable** toolbar button again.</span></span>  
  
9. <span data-ttu-id="155f1-122">Digite **BatchTag** para o **nome**, selecione **cadeia de caracteres** para o **tipo de dados**e **EIMBatch** para o **valor**.</span><span class="sxs-lookup"><span data-stu-id="155f1-122">Type **BatchTag** for the **Name**, select **String** for the **Data type**, and **EIMBatch** for the **Value**.</span></span> <span data-ttu-id="155f1-123">**BatchTag** é apenas um nome exclusivo para o lote que você enviará para o MDS.</span><span class="sxs-lookup"><span data-stu-id="155f1-123">**BatchTag** is just a unique name for the batch you will be submitting to MDS.</span></span>  
  
10. <span data-ttu-id="155f1-124">Na guia **fluxo de dados** , clique duas vezes em **adicionar colunas exigidas pelo MDS**.</span><span class="sxs-lookup"><span data-stu-id="155f1-124">In the **Data Flow** tab, double-click **Add Columns Required by MDS**.</span></span>  
  
11. <span data-ttu-id="155f1-125">Na caixa de diálogo **Editor de transformação coluna derivada** , na **caixa de listagem no painel inferior**, digite **importType** para o **nome da coluna derivada**.</span><span class="sxs-lookup"><span data-stu-id="155f1-125">In the **Derived Column Transformation Editor** dialog box, in the **list box in the bottom pane**, type **ImportType** for the **Derived Column Name**.</span></span>  
  
12. <span data-ttu-id="155f1-126">Expanda **variáveis e parâmetros** no painel superior esquerdo, arraste e solte **User:: importType** para a coluna **expression** .</span><span class="sxs-lookup"><span data-stu-id="155f1-126">Expand **Variables and Parameters** in the top-left pane, drag-drop **User::ImportType** to the **Expression** column.</span></span>  
  
     <span data-ttu-id="155f1-127">![Editor de Transformação Colunas Derivadas](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Editor de Transformação Colunas Derivadas")</span><span class="sxs-lookup"><span data-stu-id="155f1-127">![Derived Column Transformation Editor](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Derived Column Transformation Editor")</span></span>  
  
13. <span data-ttu-id="155f1-128">Digite **BatchTag** na próxima linha para o **nome da coluna derivada**.</span><span class="sxs-lookup"><span data-stu-id="155f1-128">Type **BatchTag** in the next row for the **Derived Column Name**.</span></span>  
  
14. <span data-ttu-id="155f1-129">Arrastar e soltar **usuário:: BatchTag** de **variáveis e parâmetros** para a coluna de **expressão** .</span><span class="sxs-lookup"><span data-stu-id="155f1-129">Drag-drop **User::BatchTag** from **Variables and Parameters** to the **Expression** column.</span></span>  
  
15. <span data-ttu-id="155f1-130">Clique em **OK** para fechar a caixa de diálogo **transformação coluna derivada** .</span><span class="sxs-lookup"><span data-stu-id="155f1-130">Click **OK** to close the **Derived Column Transformation** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="155f1-131">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="155f1-131">Next Step</span></span>  
 [<span data-ttu-id="155f1-132">Tarefa 13: Adicionando o destino OLE DB para gravar dados na tabela de preparo do MDS</span><span class="sxs-lookup"><span data-stu-id="155f1-132">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>](../../2014/tutorials/task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table.md)  
  
  
