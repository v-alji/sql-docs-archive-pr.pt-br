---
title: 'Tarefa 10: adicionando a transformação de grupo difuso para identificar duplicatas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 90b2b323-babd-464a-8914-9dc5e66aca74
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 086625197850fdfd6381e9c0a4a7deac8ce3ae45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680220"
---
# <a name="task-10-adding-fuzzy-group-transform-to-identify-duplicates"></a><span data-ttu-id="26da6-102">Tarefa 10: Adicionando a Transformação Grupo Difuso para identificar duplicatas</span><span class="sxs-lookup"><span data-stu-id="26da6-102">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>
  <span data-ttu-id="26da6-103">Nesta tarefa, você adiciona uma Transformação Grupo Difuso ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="26da6-103">In this task, you add a Fuzzy Group Transform to the data flow.</span></span> <span data-ttu-id="26da6-104">A transformação Grupo Difuso pode ajudar a identificar duplicatas nos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="26da6-104">The Fuzzy Group transformation can help identify duplicates in the source data.</span></span> <span data-ttu-id="26da6-105">Consulte [transformação Agrupamento Difuso](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="26da6-105">See [Fuzzy Grouping Transformation](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) for more details.</span></span>  
  
1.  <span data-ttu-id="26da6-106">Arraste e solte a transformação de **grupo difuso** em **outras transformações** na **caixa de ferramentas do SSIS** para a guia **fluxo de dados** em **combinar registros corretos e corrigidos**.</span><span class="sxs-lookup"><span data-stu-id="26da6-106">Drag-drop **Fuzzy Group** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Combine Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="26da6-107">Clique com o botão direito do mouse em transformação de **grupo difuso** na guia **fluxo de dados** e clique em **renomear**.</span><span class="sxs-lookup"><span data-stu-id="26da6-107">Right-click **Fuzzy Group** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="26da6-108">Digite **Agrupar fornecedores com IDs correspondentes** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="26da6-108">Type **Group Suppliers with matching IDs** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="26da6-109">Conectar **Combine registros corretos e corrigidos** para **Agrupar fornecedores com IDs correspondentes** usando o conector azul.</span><span class="sxs-lookup"><span data-stu-id="26da6-109">Connect **Combine Correct and Corrected Records** to **Group Suppliers with matching IDs** using the blue connector.</span></span>  
  
     <span data-ttu-id="26da6-110">![Conexão ao grupo Fornecedores com IDs correspondentes](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Conexão ao grupo Fornecedores com IDs correspondentes")</span><span class="sxs-lookup"><span data-stu-id="26da6-110">![Connection to Group Suppliers with Matching IDs](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Connection to Group Suppliers with Matching IDs")</span></span>  
  
4.  <span data-ttu-id="26da6-111">Clique duas vezes em **Agrupar fornecedores com IDs correspondentes**.</span><span class="sxs-lookup"><span data-stu-id="26da6-111">Double-click **Group Suppliers with matching IDs**.</span></span>  
  
5.  <span data-ttu-id="26da6-112">No **Editor de transformação grupo difuso**, clique em **novo** ao lado de **OLE DB lista suspensa Gerenciador de conexões** para iniciar a caixa de diálogo **Configurar OLE DB Gerenciador de conexões** .</span><span class="sxs-lookup"><span data-stu-id="26da6-112">In the **Fuzzy Group Transformation Editor**, click **New** next to **OLE DB Connection Manager drop-down list** to launch **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
6.  <span data-ttu-id="26da6-113">Na caixa de diálogo, clique em **novo** para iniciar a caixa de diálogo **Gerenciador de conexões** .</span><span class="sxs-lookup"><span data-stu-id="26da6-113">In the dialog box, click **New** to launch **Connection Manager** dialog box.</span></span>  
  
7.  <span data-ttu-id="26da6-114">Digite **(local)** ou **ponto** (.) para o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="26da6-114">Type **(local)** or **period** (.) for the Server name.</span></span>  
  
8.  <span data-ttu-id="26da6-115">Selecione **MDS** para **selecionar ou insira um campo nome do banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="26da6-115">Select **MDS** for **Select or enter a database name** field.</span></span> <span data-ttu-id="26da6-116">Você usará o banco de dados do MDS como o armazenamento temporário para a **transformação do grupo difuso**.</span><span class="sxs-lookup"><span data-stu-id="26da6-116">You will use the MDS database as the temporary storage for the **Fuzzy Group Transform**.</span></span> <span data-ttu-id="26da6-117">A transformação **Agrupamento Difuso** requer uma conexão com uma instância do SQL Server para criar as tabelas de SQL Server temporárias que o algoritmo de transformação requer para realizar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="26da6-117">The **Fuzzy Grouping** transformation requires a connection to an instance of SQL Server to create the temporary SQL Server tables that the transformation algorithm requires to do its work.</span></span> <span data-ttu-id="26da6-118">Você pode criar um banco de dados ou usar outro banco de dados existente para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="26da6-118">You can create a database or use another existing database for this purpose.</span></span>  
  
9. <span data-ttu-id="26da6-119">Clique em **testar conexão** para testar a conexão e clique em **OK** na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="26da6-119">Click **Test Connection** to test the connection and click **OK** on the message box.</span></span>  
  
10. <span data-ttu-id="26da6-120">Na caixa de diálogo **Gerenciador de conexões** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="26da6-120">In the **Connection Manager** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="26da6-121">Selecione **(local). MDS** (ou **localhost. MDS**) na **lista de conexões de dados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="26da6-121">Select **(local).MDS** (or **localhost.MDS**) from the **list of Data Connections** and click **OK**.</span></span>  
  
12. <span data-ttu-id="26da6-122">No **Editor de transformação Agrupamento Difuso**, confirme se **(local). MDS** ou **localhost. O MDS** é selecionado para o **Gerenciador de conexões OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="26da6-122">In the **Fuzzy Grouping Transformation Editor**, confirm that **(local).MDS** or **localhost.MDS** is selected for the **OLE DB Connection Manager**.</span></span>  
  
13. <span data-ttu-id="26da6-123">Alterne para a guia **colunas** .</span><span class="sxs-lookup"><span data-stu-id="26da6-123">Switch to the **Columns** tab.</span></span>  
  
14. <span data-ttu-id="26da6-124">Selecione (caixa de seleção) **SupplierID_Output** na lista de **colunas de entrada disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="26da6-124">Select (check box) **SupplierID_Output** from the list of **Available Input Columns**.</span></span> <span data-ttu-id="26da6-125">Para configurar a transformação, selecione as colunas de entrada a serem usadas ao identificar duplicatas.</span><span class="sxs-lookup"><span data-stu-id="26da6-125">To configure the transformation, select the input columns to use when identifying duplicates.</span></span> <span data-ttu-id="26da6-126">Para manter a simplicidade, use apenas SupplierID nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="26da6-126">To keep it simple, you only use the SupplierID in this step.</span></span>  
  
     <span data-ttu-id="26da6-127">![Editor de Transformação Agrupamento Difuso](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Editor de Transformação Agrupamento Difuso")</span><span class="sxs-lookup"><span data-stu-id="26da6-127">![Fuzzy Grouping Transformation Editor](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Fuzzy Grouping Transformation Editor")</span></span>  
  
15. <span data-ttu-id="26da6-128">Clique em **OK** para fechar o **Editor de transformação grupo difuso**.</span><span class="sxs-lookup"><span data-stu-id="26da6-128">Click **OK** to close the **Fuzzy Group Transformation Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="26da6-129">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="26da6-129">Next Step</span></span>  
 [<span data-ttu-id="26da6-130">Tarefa 11: Adicionando a Transformação Divisão Condicional para filtrar duplicatas</span><span class="sxs-lookup"><span data-stu-id="26da6-130">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>](../../2014/tutorials/task-11-adding-conditional-split-transform-to-filter-duplicates.md)  
  
  
