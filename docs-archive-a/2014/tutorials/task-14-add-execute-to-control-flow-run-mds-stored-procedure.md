---
title: 'Tarefa 14: adicionando a tarefa Executar SQL ao fluxo de controle para executar o procedimento armazenado para o MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9a5d1b52-d505-4e6f-8a89-569329c094e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da8e80b25706c40e749fc364baeb578681e76b42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680196"
---
# <a name="task-14-adding-execute-sql-task-to-control-flow-to-run-the-stored-procedure-for-mds"></a><span data-ttu-id="77e95-102">Tarefa 14: Adicionando a tarefa Executar SQL ao fluxo de controle para executar o procedimento armazenado para MDS</span><span class="sxs-lookup"><span data-stu-id="77e95-102">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>
  <span data-ttu-id="77e95-103">Depois de carregar dados nas tabelas de preparo do MDS, você executará um procedimento armazenado associado a essa tabela para carregar os dados de preparo nas tabelas adequadas no banco de dados MDS.</span><span class="sxs-lookup"><span data-stu-id="77e95-103">After loading data into the staging tables of MDS, you run a stored procedure associated with that table to load the data from staging into the appropriate tables in the MDS database.</span></span> <span data-ttu-id="77e95-104">Esse procedimento armazenado tem dois parâmetros necessários que você precisa passar: LogFlag e VersionName.</span><span class="sxs-lookup"><span data-stu-id="77e95-104">This stored procedure has two required parameters that you need to pass: LogFlag and VersionName.</span></span> <span data-ttu-id="77e95-105">LogFlag especifica se as transações serão registradas em log durante o processo de preparo e VersionName representa a versão do modelo.</span><span class="sxs-lookup"><span data-stu-id="77e95-105">LogFlag specifies whether transactions are logged during the staging process and VersionName represents the version of the model.</span></span> <span data-ttu-id="77e95-106">Consulte o tópico de [procedimento armazenado em etapas](https://msdn.microsoft.com/library/hh231028.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="77e95-106">See [Staged Stored Procedure](https://msdn.microsoft.com/library/hh231028.aspx) topic for more details.</span></span>

 <span data-ttu-id="77e95-107">Nesta tarefa, você adicionará a Tarefa Executar SQL ao fluxo de controle para invocar o procedimento armazenado para carregar os dados preparados nas tabelas adequadas do MDS.</span><span class="sxs-lookup"><span data-stu-id="77e95-107">In this task, you add the Execute SQL Task to the control flow to invoke the stored procedure to load the staged data into appropriate MDS tables.</span></span>

1.  <span data-ttu-id="77e95-108">Agora, alterne para a guia **fluxo de controle** .</span><span class="sxs-lookup"><span data-stu-id="77e95-108">Now, switch to the **Control Flow** tab.</span></span>

2.  <span data-ttu-id="77e95-109">Arraste e solte a **tarefa Executar SQL** da **caixa de ferramentas do SSIS** para a guia fluxo de **controle** .</span><span class="sxs-lookup"><span data-stu-id="77e95-109">Drag-drop **Execute SQL Task** from the **SSIS Toolbox** to the **Control Flow** tab.</span></span>

3.  <span data-ttu-id="77e95-110">Clique com o botão direito do mouse em **Executar tarefa SQL** na guia **fluxo de controle** e clique em **renomear**.</span><span class="sxs-lookup"><span data-stu-id="77e95-110">Right-click **Execute SQL Task** in the **Control Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="77e95-111">Digite **acionar procedimento armazenado para carregar dados no MDS** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="77e95-111">Type **Trigger Stored Procedure to Load Data into MDS** and press **ENTER**.</span></span>

4.  <span data-ttu-id="77e95-112">Conecte os **dados de fornecedor de recebimento, limpeza, correspondência e** organização para **disparar o procedimento armazenado para carregar dados** usando o conector verde.</span><span class="sxs-lookup"><span data-stu-id="77e95-112">Connect **Receive, Cleanse, Match, and Curate Supplier Data** to **Trigger Stored Procedure to Load Data** using the green connector.</span></span>

     <span data-ttu-id="77e95-113">![Conectar à tarefa Executar SQL.](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Conectar à tarefa Executar SQL.")</span><span class="sxs-lookup"><span data-stu-id="77e95-113">![Connect to Execute SQL Task](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Connect to Execute SQL Task")</span></span>

5.  <span data-ttu-id="77e95-114">Usando a janela **variáveis** , adicione duas novas variáveis com as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="77e95-114">Using the **Variables** window, add two new variables with the following settings.</span></span> <span data-ttu-id="77e95-115">Se você não vir a janela **variáveis** , clique em **SSIS** na barra de menus e clique em **variáveis**.</span><span class="sxs-lookup"><span data-stu-id="77e95-115">If you do not see the **Variables** window, click **SSIS** on the menu bar and click **Variables**.</span></span>

    |<span data-ttu-id="77e95-116">Nome</span><span class="sxs-lookup"><span data-stu-id="77e95-116">Name</span></span>|<span data-ttu-id="77e95-117">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="77e95-117">Data Type</span></span>|<span data-ttu-id="77e95-118">Valor</span><span class="sxs-lookup"><span data-stu-id="77e95-118">Value</span></span>|
    |----------|---------------|-----------|
    |<span data-ttu-id="77e95-119">LogFlag</span><span class="sxs-lookup"><span data-stu-id="77e95-119">LogFlag</span></span>|<span data-ttu-id="77e95-120">Int32</span><span class="sxs-lookup"><span data-stu-id="77e95-120">Int32</span></span>|<span data-ttu-id="77e95-121">1</span><span class="sxs-lookup"><span data-stu-id="77e95-121">1</span></span>|
    |<span data-ttu-id="77e95-122">VersionName</span><span class="sxs-lookup"><span data-stu-id="77e95-122">VersionName</span></span>|<span data-ttu-id="77e95-123">String</span><span class="sxs-lookup"><span data-stu-id="77e95-123">String</span></span>|<span data-ttu-id="77e95-124">VERSION_1</span><span class="sxs-lookup"><span data-stu-id="77e95-124">VERSION_1</span></span>|

     <span data-ttu-id="77e95-125">![Janela Variáveis do SSIS](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "Janela Variáveis do SSIS")</span><span class="sxs-lookup"><span data-stu-id="77e95-125">![SSIS Variables Window](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "SSIS Variables Window")</span></span>

6.  <span data-ttu-id="77e95-126">Clique duas vezes em **disparar procedimento armazenado para carregar dados no MDS**.</span><span class="sxs-lookup"><span data-stu-id="77e95-126">Double-click **Trigger Stored Procedure to Load Data into MDS**.</span></span>

7.  <span data-ttu-id="77e95-127">Na caixa de diálogo **Editor da tarefa Executar SQL** , selecione **(local). MDS** (ou **localhost. MDS**) para **conexão**.</span><span class="sxs-lookup"><span data-stu-id="77e95-127">In the **Execute SQL Task Editor** dialog box, select **(local).MDS** (or **localhost.MDS**) for **Connection**.</span></span>

8.  <span data-ttu-id="77e95-128">Digite **exec [STG]. [ udp_Supplier_Leaf]?,?,?**</span><span class="sxs-lookup"><span data-stu-id="77e95-128">Type **EXEC [stg].[udp_Supplier_Leaf] ?, ?, ?**</span></span> <span data-ttu-id="77e95-129">**instrução for SQL**.</span><span class="sxs-lookup"><span data-stu-id="77e95-129">for **SQL Statement**.</span></span> <span data-ttu-id="77e95-130">Você pode verificar o nome usando o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="77e95-130">You can verify the name by using SQL Server Management Studio.</span></span>

     <span data-ttu-id="77e95-131">![Caixa de diálogo Editor de Tarefa Executar SQL - Configurações Gerais](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Caixa de diálogo Editor de Tarefa Executar SQL - Configurações Gerais")</span><span class="sxs-lookup"><span data-stu-id="77e95-131">![Execute SQL Editor Dialog Box - General Settings](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Execute SQL Editor Dialog Box - General Settings")</span></span>

9. <span data-ttu-id="77e95-132">Clique em **mapeamento de parâmetro** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="77e95-132">Click **Parameter Mapping** from the menu on left.</span></span>

10. <span data-ttu-id="77e95-133">Na página **mapeamento de parâmetros** , clique em **Adicionar** para adicionar um mapeamento.</span><span class="sxs-lookup"><span data-stu-id="77e95-133">In the **Parameter Mapping** page, click **Add** to add a mapping.</span></span> <span data-ttu-id="77e95-134">Maximize a janela e redimensione as colunas para que você possa visualizar os valores nas listas suspensas corretamente.</span><span class="sxs-lookup"><span data-stu-id="77e95-134">Maximize the window and resize columns so that you can see values in drop-down lists properly.</span></span>

11. <span data-ttu-id="77e95-135">Selecione **User:: VersionName** na lista suspensa para o **nome da variável**.</span><span class="sxs-lookup"><span data-stu-id="77e95-135">Select **User::VersionName** from the drop-down list for the **Variable Name**.</span></span>

12. <span data-ttu-id="77e95-136">Selecione **nvarchar** para **tipo de dados**.</span><span class="sxs-lookup"><span data-stu-id="77e95-136">Select **NVARCHAR** for **Data Type**.</span></span>

13. <span data-ttu-id="77e95-137">Digite **0** (zero) para o **nome do parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="77e95-137">Type **0** (zero) for **Parameter Name**.</span></span>

14. <span data-ttu-id="77e95-138">Repita as quatro etapas anteriores para adicionar mais duas variáveis.</span><span class="sxs-lookup"><span data-stu-id="77e95-138">Repeat the previous four steps to add two more variables.</span></span>

    |<span data-ttu-id="77e95-139">Nome da variável</span><span class="sxs-lookup"><span data-stu-id="77e95-139">Variable Name</span></span>|<span data-ttu-id="77e95-140">Tipo de Dados (importante)</span><span class="sxs-lookup"><span data-stu-id="77e95-140">Data Type (important)</span></span>|<span data-ttu-id="77e95-141">Nome do Parâmetro</span><span class="sxs-lookup"><span data-stu-id="77e95-141">Parameter Name</span></span>|
    |-------------------|-----------------------------|--------------------|
    |<span data-ttu-id="77e95-142">User::LogFlag</span><span class="sxs-lookup"><span data-stu-id="77e95-142">User::LogFlag</span></span>|<span data-ttu-id="77e95-143">LONG</span><span class="sxs-lookup"><span data-stu-id="77e95-143">LONG</span></span>|<span data-ttu-id="77e95-144">1</span><span class="sxs-lookup"><span data-stu-id="77e95-144">1</span></span>|
    |<span data-ttu-id="77e95-145">User::BatchTag</span><span class="sxs-lookup"><span data-stu-id="77e95-145">User::BatchTag</span></span>|<span data-ttu-id="77e95-146">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="77e95-146">NVARCHAR</span></span>|<span data-ttu-id="77e95-147">2</span><span class="sxs-lookup"><span data-stu-id="77e95-147">2</span></span>|

     <span data-ttu-id="77e95-148">![Editor de Tarefa Executar SQL - Mapeamento de Parâmetros](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Editor de Tarefa Executar SQL - Mapeamento de Parâmetros")</span><span class="sxs-lookup"><span data-stu-id="77e95-148">![Execute SQL Task Editor - Parameter Mapping](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Execute SQL Task Editor - Parameter Mapping")</span></span>

15. <span data-ttu-id="77e95-149">Clique em **OK** para fechar a caixa de diálogo **Executar editor SQL** .</span><span class="sxs-lookup"><span data-stu-id="77e95-149">Click **OK** to close the **Execute SQL Editor** dialog box.</span></span>

## <a name="next-step"></a><span data-ttu-id="77e95-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="77e95-150">Next Step</span></span>
 [<span data-ttu-id="77e95-151">Tarefa 15: Criando e executando o projeto SSIS</span><span class="sxs-lookup"><span data-stu-id="77e95-151">Task 15: Building and Running the SSIS Project</span></span>](../../2014/tutorials/task-15-building-and-running-the-ssis-project.md)


