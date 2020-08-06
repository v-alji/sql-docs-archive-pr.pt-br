---
title: Definindo uma fonte de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5a3e83c9-8788-431e-85b0-a68c79377ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdf00b47360341e2b9a99654482d65be83b86503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568860"
---
# <a name="defining-a-data-source"></a><span data-ttu-id="24ac5-102">Definindo uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="24ac5-102">Defining a Data Source</span></span>
  <span data-ttu-id="24ac5-103">Depois de criar um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , normalmente, você começa a trabalhar com esse projeto definindo uma ou mais fontes de dados que serão usadas pelo projeto.</span><span class="sxs-lookup"><span data-stu-id="24ac5-103">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you generally start working with the project by defining one or more data sources that the project will use.</span></span> <span data-ttu-id="24ac5-104">Ao definir uma fonte de dados, você está definindo as informações da cadeia de conexão que será usada para conectar-se à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="24ac5-104">When you define a data source, you are defining the connection string information that will be used to connect to the data source.</span></span> <span data-ttu-id="24ac5-105">Para obter mais informações, veja [Criar uma fonte de dados &#40;SSAS multidimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="24ac5-105">For more information, see [Create a Data Source &#40;SSAS Multidimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span></span>  
  
 <span data-ttu-id="24ac5-106">Na tarefa a seguir, você definirá o banco de dados de exemplo do AdventureWorksDWSQLServer2012 como a fonte de dados do projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24ac5-106">In the following task, you define the AdventureWorksDWSQLServer2012 sample database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="24ac5-107">Apesar de esse banco de dados estar hospedado no seu computador local por causa deste tutorial, os bancos de dados de origem são frequentemente hospedados em um ou mais computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="24ac5-107">While this database is located on your local computer for the purposes of this tutorial, source databases are frequently hosted on one or more remote computers.</span></span>  
  
### <a name="to-define-a-new-data-source"></a><span data-ttu-id="24ac5-108">Para definir uma nova fonte de dados</span><span class="sxs-lookup"><span data-stu-id="24ac5-108">To define a new data source</span></span>  
  
1.  <span data-ttu-id="24ac5-109">No Gerenciador de Soluções (à direita da janela Microsoft Visual Studio), clique com o botão direito do mouse em **Fontes de Dados**e clique em **Nova Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="24ac5-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Sources**, and then click **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="24ac5-110">Na página **Bem-vindo ao Assistente para Fontes de Dados** do **Assistente para Fontes de Dados**, clique em **Avançar** para abrir a página **Selecionar como definir a conexão** .</span><span class="sxs-lookup"><span data-stu-id="24ac5-110">On the **Welcome to the Data Source Wizard** page of the **Data Source Wizard**, click **Next** to open the **Select how to define the connection** page.</span></span>  
  
3.  <span data-ttu-id="24ac5-111">Na página **Selecionar como definir a conexão** , você pode definir uma fonte de dados com base em uma nova conexão, em uma conexão existente ou em um objeto de fonte de dados definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="24ac5-111">On the **Select how to define the connection** page, you can define a data source based on a new connection, based on an existing connection, or based on a previously defined data source object.</span></span> <span data-ttu-id="24ac5-112">Neste tutorial, você define uma fonte de dados com base em uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="24ac5-112">In this tutorial, you define a data source based on a new connection.</span></span> <span data-ttu-id="24ac5-113">Verifique se a opção **Criar uma fonte de dados com base em uma conexão nova ou existente** está selecionada e clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="24ac5-113">Verify that **Create a data source based on an existing or new connection** is selected, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="24ac5-114">Na caixa de diálogo **Gerenciador de Conexões** , você define as propriedades de conexão da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="24ac5-114">In the **Connection Manager** dialog box, you define connection properties for the data source.</span></span> <span data-ttu-id="24ac5-115">Na caixa de listagem **Provedor** , verifique se a opção **OLE DB Nativo\SQL Server Native Client 11.0** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="24ac5-115">In the **Provider** list box, verify that **Native OLE DB\SQL Server Native Client 11.0** is selected.</span></span>  
  
     [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="24ac5-116">também dá suporte a outros provedores que são exibidos na lista **Provedor** .</span><span class="sxs-lookup"><span data-stu-id="24ac5-116">also supports other providers, which are displayed in the **Provider** list.</span></span>  
  
5.  <span data-ttu-id="24ac5-117">Na caixa de texto **nome do servidor** , digite `localhost` .</span><span class="sxs-lookup"><span data-stu-id="24ac5-117">In the **Server name** text box, type `localhost`.</span></span>  
  
     <span data-ttu-id="24ac5-118">Para se conectar a uma instância nomeada no computador local, digite **localhost \\<\> nome da instância**.</span><span class="sxs-lookup"><span data-stu-id="24ac5-118">To connect to a named instance on your local computer, type **localhost\\<instance name\>**.</span></span> <span data-ttu-id="24ac5-119">Para conectar-se ao computador específico em vez do computador local, digite o nome do computador ou o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="24ac5-119">To connect to the specific computer instead of the local computer, type the computer name or IP address.</span></span>  
  
6.  <span data-ttu-id="24ac5-120">Verifique se a opção **Usar Autenticação do Windows** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="24ac5-120">Verify that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="24ac5-121">Na lista **Selecionar ou inserir um nome de banco de dados** , selecione **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="24ac5-121">In the **Select or enter a database name** list, select **AdventureWorksDW2012**.</span></span>  
  
7.  <span data-ttu-id="24ac5-122">Clique em **Testar Conexão** para testar a conexão com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="24ac5-122">Click **Test Connection** to test the connection to the database.</span></span>  
  
8.  <span data-ttu-id="24ac5-123">Clique em **OK** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="24ac5-123">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="24ac5-124">Na página **Informações sobre Representação** do assistente, você define as credenciais de segurança que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usará para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="24ac5-124">On the **Impersonation Information** page of the wizard, you define the security credentials for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to use to connect to the data source.</span></span> <span data-ttu-id="24ac5-125">A representação afeta a conta do Windows usada para conexão à fonte de dados quando a Autenticação do Windows é selecionada.</span><span class="sxs-lookup"><span data-stu-id="24ac5-125">Impersonation affects the Windows account used to connect to the data source when Windows Authentication is selected.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="24ac5-126">não dá suporte à representação para o processamento de objetos OLAP.</span><span class="sxs-lookup"><span data-stu-id="24ac5-126">does not support impersonation for processing OLAP objects.</span></span> <span data-ttu-id="24ac5-127">Selecione **Usar a conta de serviço**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="24ac5-127">Select **Use the service account**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="24ac5-128">Na página **Concluindo o Assistente** , aceite o nome padrão, **Adventure Works DW 2012**, e clique em **Concluir** para criar a nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="24ac5-128">On the **Completing the Wizard** page, accept the default name, **Adventure Works DW 2012**, and then click **Finish** to create the new data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24ac5-129">Para modificar as propriedades da fonte de dados depois de criá-la, clique duas vezes na fonte de dados na pasta **Fontes de Dados** para exibir as propriedades dessa fonte de dados no **Designer de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="24ac5-129">To modify the properties of the data source after it has been created, double-click the data source in the **Data Sources** folder to display the data source properties in **Data Source Designer**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="24ac5-130">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="24ac5-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="24ac5-131">Definindo uma exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="24ac5-131">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="24ac5-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24ac5-132">See Also</span></span>  
 [<span data-ttu-id="24ac5-133">Criar uma fonte de dados &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="24ac5-133">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/create-a-data-source-ssas-multidimensional.md)  
  
  
