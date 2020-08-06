---
title: 'Lição 2: Especificando informações de conexão (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 54405a3a-d7fa-4d95-8963-9aa224e5901e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c187f0abdc4b277a5f1428407b5c42ca4fd6fee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680329"
---
# <a name="lesson-2-specifying-connection-information-reporting-services"></a><span data-ttu-id="ea9f6-102">Lição 2: Especificando informações sobre conexão (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="ea9f6-102">Lesson 2: Specifying Connection Information (Reporting Services)</span></span>
  <span data-ttu-id="ea9f6-103">Depois de adicionar um relatório ao projeto Tutorial, é necessário definir uma *fonte de dados*, que são informações de conexão usadas pelo relatório para acessar dados de um banco de dados relacional, banco de dados multidimensional ou outro recurso.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-103">After you add a report to the Tutorial project, you need to define a *data source*, which is connection information the report uses to access data from either a relational database, multidimensional database, or other resource.</span></span>  
  
 <span data-ttu-id="ea9f6-104">Nesta lição, você usará o banco de dados de exemplo do [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] como a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-104">In this lesson, you will use the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database as your data source.</span></span> <span data-ttu-id="ea9f6-105">Este tutorial pressupõe que esse banco de dados está localizado em uma instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] que está instalada no computador local.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-105">This tutorial assumes that this database is located in a default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed on your local computer.</span></span>  
  
### <a name="to-set-up-a-connection"></a><span data-ttu-id="ea9f6-106">Para configurar uma conexão</span><span class="sxs-lookup"><span data-stu-id="ea9f6-106">To set up a connection</span></span>  
  
1.  <span data-ttu-id="ea9f6-107">No painel **dados do relatório** , clique em **novo** e em **fonte de dados...**.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-107">In the **Report Data** pane, click **New** and then click **Data Source...**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea9f6-108">Se o painel **Dados do Relatório** não estiver visível, no menu **Exibir** , clique em **Dados do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-108">If the **Report Data** pane is not visible, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="ea9f6-109">Em **Nome**, digite [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9f6-109">In **Name**, type [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span></span>  
  
3.  <span data-ttu-id="ea9f6-110">Garanta que a opção **Conexão inserida** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-110">Make sure **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="ea9f6-111">Em **Tipo**, selecione **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-111">In **Type**, select **Microsoft SQL Server**.</span></span>  
  
5.  <span data-ttu-id="ea9f6-112">Em **Cadeia de conexão**, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ea9f6-112">In **Connection string**, type the following:</span></span>  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2012  
    ```  
  
     <span data-ttu-id="ea9f6-113">Esta cadeia de conexão assume que o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], o servidor de relatório e o banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] estão instalados no computador local e que você tem permissão para fazer logon no banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea9f6-113">This connection string assumes that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the report server, and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database are all installed on the local computer and that you have permission to log on to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea9f6-114">Se estiver usando o [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] com Serviços Avançados ou uma instância nomeada, a cadeia de conexão deverá incluir informações da instância:</span><span class="sxs-lookup"><span data-stu-id="ea9f6-114">If you are using [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services or a named instance, the connection string must include instance information:</span></span>  
    >   
    >  `Data source=localhost\SQLEXPRESS; initial catalog=AdventureWorks2012`  
    >   
    >  <span data-ttu-id="ea9f6-115">Para obter mais informações sobre cadeias de conexão, consulte [conexões de dados, fontes de dados e cadeias de conexão no Reporting Services e na](data-connections-data-sources-and-connection-strings-in-reporting-services.md) [caixa de diálogo Propriedades da fonte de dados, geral](data-source-properties-dialog-box-general.md).</span><span class="sxs-lookup"><span data-stu-id="ea9f6-115">For more information about connection strings, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) and [Data Source Properties Dialog Box, General](data-source-properties-dialog-box-general.md).</span></span>  
  
6.  <span data-ttu-id="ea9f6-116">Clique em **Credenciais** no painel esquerdo e clique em **Usar Autenticação do Windows (segurança integrada)**.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-116">Click **Credentials** in the left pane and click **Use Windows Authentication (integrated security)**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="ea9f6-117">a fonte de dados [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] é adicionada ao painel de **dados do relatório** .</span><span class="sxs-lookup"><span data-stu-id="ea9f6-117">data source [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] is added to the **Report Data** pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="ea9f6-118">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="ea9f6-118">Next Task</span></span>  
 <span data-ttu-id="ea9f6-119">Você definiu uma conexão com o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] com êxito.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-119">You have successfully defined a connection to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="ea9f6-120">Em seguida, você criará o relatório.</span><span class="sxs-lookup"><span data-stu-id="ea9f6-120">Next, you will create the report.</span></span> <span data-ttu-id="ea9f6-121">Consulte [Lição 3: Definindo um conjunto de dados para o relatório de tabela &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ea9f6-121">See [Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea9f6-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea9f6-122">See Also</span></span>  
 [<span data-ttu-id="ea9f6-123">Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ea9f6-123">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
