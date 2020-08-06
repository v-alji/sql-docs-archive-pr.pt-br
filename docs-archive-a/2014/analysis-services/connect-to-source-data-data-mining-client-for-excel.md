---
title: Conectar-se a dados de origem (cliente de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- connections
ms.assetid: 548672ce-e403-4aca-b67a-c2c797f053dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4b4759d94043fdccacdf5b285de50697a18965e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571001"
---
# <a name="connect-to-source-data-data-mining-client-for-excel"></a><span data-ttu-id="df3ed-102">Conectar a dados de origem (Cliente de Mineração de Dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="df3ed-102">Connect to Source Data (Data Mining Client for Excel)</span></span>
  <span data-ttu-id="df3ed-103">Este tópico descreve como criar e usar as conexões usadas para armazenar modelos de mineração de dados e para acessar os dados externos armazenados no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df3ed-103">This topic describes how to create and use connections used for storing data mining models, and for accessing external data stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="df3ed-104">**Conexões de mineração de dados.**</span><span class="sxs-lookup"><span data-stu-id="df3ed-104">**Data mining connections.**</span></span> <span data-ttu-id="df3ed-105">A conexão inicial criada quando você inicia os suplementos é usada para acessar algoritmos, analisar dados e armazenar a estrutura e os modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="df3ed-105">The initial connection that you create when you start the add-ins is used to access algorithms, analyze data, and store mining structure and models.</span></span>  
  
 <span data-ttu-id="df3ed-106">Uma conexão para uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] é necessária para usar as ferramentas de modelagem e visualização, porque os suplementos dependem de algoritmos e estruturas de dados fornecidos pelo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df3ed-106">A connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is required to use the modeling and visualization tools in the add-ins, because the add-ins depend on algorithms and data structures that are provided by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="df3ed-107">**Conexões para fontes de dados externas.**</span><span class="sxs-lookup"><span data-stu-id="df3ed-107">**Connections to external data sources.**</span></span> <span data-ttu-id="df3ed-108">Você também pode criar conexões com dados externos quando estiver criando modelos ou salvando os resultados.</span><span class="sxs-lookup"><span data-stu-id="df3ed-108">You can also create connections to external data as you are building models or saving the results.</span></span> <span data-ttu-id="df3ed-109">Por exemplo, você pode criar um modelo de mineração de dados em um servidor e, em seguida, executar uma consulta de previsão em relação ao modelo de mineração de dados usando dados armazenados em outra instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], em uma tabela de dados do Excel ou em uma fonte de dados externa, como o [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span><span class="sxs-lookup"><span data-stu-id="df3ed-109">For example, you can create a data mining model on one server, and then perform a prediction query against the data mining model by using data stored in another instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], in an Excel data table, or in an external data source such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span></span> <span data-ttu-id="df3ed-110">Cada vez que você acessar uma nova fonte de dados, receberá uma solicitação para criar uma conexão usando uma caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="df3ed-110">Each time that you access a new data source, you will be prompted to create a connection by using a dialog box.</span></span>  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq2"></a> <span data-ttu-id="df3ed-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="df3ed-111">Prerequisites</span></span>  
 <span data-ttu-id="df3ed-112">Esta versão dos suplementos requer que sua instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] seja SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="df3ed-112">This version of the add-ins requires that your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] be SQL Server 2012.</span></span> <span data-ttu-id="df3ed-113">Uma versão separada dos suplementos estará disponível se você quiser se conectar a uma versão anterior do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df3ed-113">A separate version of the add-ins is available if you want to connect to an earlier version of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="df3ed-114">Há versões dos suplementos que oferecem suporte ao SQL Server 2005, ao SQL Server 2008 e ao SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="df3ed-114">There are versions of the add-ins that support SQL Server 2005, SQL Server 2008, and SQL Server 2008 R2.</span></span>  
  
 <span data-ttu-id="df3ed-115">Para se conectar a um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], você deve ter permissões para acessar o servidor do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="df3ed-115">To connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, you must have permissions to access the database server.</span></span> <span data-ttu-id="df3ed-116">Além disso, as sessões de mineração de dados devem ser habilitadas e você deve ter permissões de leitura ou leitura/gravação nos objetos de banco de dados armazenados no servidor.</span><span class="sxs-lookup"><span data-stu-id="df3ed-116">Moreover, data mining sessions must be enabled, and you must have read or read/write permissions on database objects stored on the server.</span></span>  
  
##  <a name="creating-data-mining-server-connections"></a><a name="bkmk_connect"></a><span data-ttu-id="df3ed-117">Criando conexões do servidor de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="df3ed-117">Creating Data Mining Server Connections</span></span>  
 <span data-ttu-id="df3ed-118">O grupo de **conexões** no cliente de mineração de dados para Excel e as ferramentas de análise de tabela para Excel fornecem ferramentas para gerenciar conexões com uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df3ed-118">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel provides tools for managing connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="df3ed-119">Você pode criar a conexão quando instala o suplemento ou pode adicionar uma conexão depois.</span><span class="sxs-lookup"><span data-stu-id="df3ed-119">You can create the connection when you install the add-in, or you can add a connection later.</span></span>  
  
-   <span data-ttu-id="df3ed-120">Você pode criar várias conexões e alterar conexões a qualquer momento, a menos que esteja no processo de criar ou consultar um modelo.</span><span class="sxs-lookup"><span data-stu-id="df3ed-120">You can create multiple connections, and change connections at any time, unless you are in the process of creating or querying a model.</span></span>  
  
     <span data-ttu-id="df3ed-121">Não altere nem feche uma conexão quando um modelo de mineração de dados estiver sendo processado.</span><span class="sxs-lookup"><span data-stu-id="df3ed-121">Do not change or close a connection when a data mining model is being processed.</span></span> <span data-ttu-id="df3ed-122">O modelo de mineração de dados pode perder dados ou se tornar inutilizável.</span><span class="sxs-lookup"><span data-stu-id="df3ed-122">The data mining model might lose data, or the model might become unusable.</span></span>  
  
-   <span data-ttu-id="df3ed-123">Apenas uma conexão pode estar ativa em um determinado momento.</span><span class="sxs-lookup"><span data-stu-id="df3ed-123">Only one connection can be active at a particular time.</span></span>  
  
### <a name="connections-in-the-excel-add-ins"></a><span data-ttu-id="df3ed-124">Conexões nos suplementos do Excel</span><span class="sxs-lookup"><span data-stu-id="df3ed-124">Connections in the Excel Add-ins</span></span>  
 <span data-ttu-id="df3ed-125">O grupo de **conexões** no cliente de mineração de dados para Excel e as ferramentas de análise de tabela para Excel são onde você gerencia conexões com uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df3ed-125">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel is where you manage connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
##### <a name="create-a-new-server-connection-in-the-excel-add-ins"></a><span data-ttu-id="df3ed-126">Criar uma nova conexão de servidor nos suplementos do Excel</span><span class="sxs-lookup"><span data-stu-id="df3ed-126">Create a new server connection in the Excel add-ins</span></span>  
  
1.  <span data-ttu-id="df3ed-127">Clique no botão **conexão** na faixa de medida **analisar** ou **mineração de dados** .</span><span class="sxs-lookup"><span data-stu-id="df3ed-127">Click the **Connection** button on the **Analyze** or **Data Mining** ribbon.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df3ed-128">O texto do botão indica se uma conexão existe.</span><span class="sxs-lookup"><span data-stu-id="df3ed-128">The text of the button indicates if a connection exists.</span></span> <span data-ttu-id="df3ed-129">Quando nenhuma conexão foi feita na planilha, o botão contém o texto " \<No connection> ." Se uma conexão tiver sido feita anteriormente na pasta de trabalho, o nome dessa conexão aparecerá no botão.</span><span class="sxs-lookup"><span data-stu-id="df3ed-129">When no connection has been made in the worksheet, the button contains the text "\<No connection>." If a connection was previously made in the workbook, the name of that connection appears in the button.</span></span>  
  
2.  <span data-ttu-id="df3ed-130">Na caixa de diálogo **Analysis Services conexões** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="df3ed-130">In the **Analysis Services Connections** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="df3ed-131">Na caixa de diálogo **nova conexão Analysis Services** , digite o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="df3ed-131">In the **New Analysis Services Connection** dialog box, type the name of the server.</span></span>  
  
4.  <span data-ttu-id="df3ed-132">Especifique o método de autenticação.</span><span class="sxs-lookup"><span data-stu-id="df3ed-132">Specify the authentication method.</span></span>  
  
5.  <span data-ttu-id="df3ed-133">Selecione um banco de dados na lista suspensa **nome do catálogo** .</span><span class="sxs-lookup"><span data-stu-id="df3ed-133">Select a database from the **Catalog name** drop-down list.</span></span> <span data-ttu-id="df3ed-134">Se não existir nenhum banco de dados na instância, selecione **(padrão)**.</span><span class="sxs-lookup"><span data-stu-id="df3ed-134">If no database exists on the instance, select **(default)**.</span></span>  
  
6.  <span data-ttu-id="df3ed-135">Digite um nome amigável para a conexão.</span><span class="sxs-lookup"><span data-stu-id="df3ed-135">Type a friendly name for the connection.</span></span>  
  
7.  <span data-ttu-id="df3ed-136">Clique em **testar conexão** para verificar se o servidor e o banco de dados estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="df3ed-136">Click **Test Connection** to verify that the server and database are available.</span></span>  
  
8.  <span data-ttu-id="df3ed-137">Clique em **OK**e então clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="df3ed-137">Click **OK**, and then click **Close**.</span></span>  
  
### <a name="connections-using-a-web-service"></a><span data-ttu-id="df3ed-138">Conexões usando um serviço Web</span><span class="sxs-lookup"><span data-stu-id="df3ed-138">Connections using a Web Service</span></span>  
 <span data-ttu-id="df3ed-139">Se você estiver usando uma arquitetura de cliente fino para habilitar a procura de cubos e dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], também poderá configurar uma conexão com um servidor [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] por meio de serviços Web.</span><span class="sxs-lookup"><span data-stu-id="df3ed-139">If you are using a thin-client architecture to enable browsing of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubes and data, you can also configure a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server through Web services.</span></span> <span data-ttu-id="df3ed-140">Para obter informações sobre como definir um cliente com base na Web, consulte os Manuais Online do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df3ed-140">For information about how to define a Web-based client, see [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="df3ed-141">Se você tiver acesso a um servidor que tenha sido configurado para serviços Web, especifique o tipo de conexão ao criá-la.</span><span class="sxs-lookup"><span data-stu-id="df3ed-141">If you have access to a server that has been configured for Web services, you can specify the connection type when you first create the connection.</span></span>  
  
##### <a name="create-an-http-connection-to-analysis-services"></a><span data-ttu-id="df3ed-142">Criar uma conexão HTTP com o Analysis Services</span><span class="sxs-lookup"><span data-stu-id="df3ed-142">Create an HTTP connection to Analysis Services</span></span>  
  
1.  <span data-ttu-id="df3ed-143">Abra a caixa de diálogo **nova conexão Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="df3ed-143">Open the **New Analysis Services Connection** dialog box.</span></span>  
  
2.  <span data-ttu-id="df3ed-144">Para o nome do servidor, digite http:// seguido pela URL atribuída ao servidor [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df3ed-144">For the server name, type http:// followed by the URL assigned to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span>  
  
3.  <span data-ttu-id="df3ed-145">Digite o nome de usuário e a senha necessários para acessar o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="df3ed-145">Type the user name and the password that is required to access the Web service.</span></span>  
  
### <a name="connections-in-the-visio-add-in"></a><span data-ttu-id="df3ed-146">Conexões no suplemento do Visio</span><span class="sxs-lookup"><span data-stu-id="df3ed-146">Connections in the Visio Add-In</span></span>  
 <span data-ttu-id="df3ed-147">Diferente do Excel, o Visio não fornece uma faixa de opções de ferramentas e não há botões especificamente para criar ou monitorar conexões.</span><span class="sxs-lookup"><span data-stu-id="df3ed-147">Unlike Excel, Visio does not provide a tool ribbon, and there are no buttons specifically for creating or monitoring connections.</span></span> <span data-ttu-id="df3ed-148">Em vez disso, a conexão de dados é criada quando você seleciona pela primeira vez uma forma de mineração de dados solta-a em uma página do Visio.</span><span class="sxs-lookup"><span data-stu-id="df3ed-148">Instead, the data connection is created when you first select a data mining shape and drop it onto a Visio page.</span></span> <span data-ttu-id="df3ed-149">Um assistente solicitará que você selecione o modelo para a forma e defina outras opções.</span><span class="sxs-lookup"><span data-stu-id="df3ed-149">A wizard will prompt you to select the model for the shape and to set other options.</span></span>  
  
 <span data-ttu-id="df3ed-150">Caso você tenha usado anteriormente uma conexão com uma fonte de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] no Excel, essas conexões serão listadas como possíveis fontes de dados para selecionar.</span><span class="sxs-lookup"><span data-stu-id="df3ed-150">If you have previously used a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source in Excel, these connections are listed as possible data sources from which to select.</span></span>  
  
##### <a name="create-a-connection-for-a-visio-shape"></a><span data-ttu-id="df3ed-151">Criar uma conexão de dados para uma forma do Visio</span><span class="sxs-lookup"><span data-stu-id="df3ed-151">Create a connection for a Visio shape</span></span>  
  
1.  <span data-ttu-id="df3ed-152">Abra o Modelo de Mineração de Dados e selecione uma das formas de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="df3ed-152">Open the Data Mining Template, and select one of the data mining shapes.</span></span>  
  
2.  <span data-ttu-id="df3ed-153">Arraste e solte a forma para uma página em branco.</span><span class="sxs-lookup"><span data-stu-id="df3ed-153">Drag and drop the shape to a blank page.</span></span>  
  
3.  <span data-ttu-id="df3ed-154">Na caixa de diálogo **selecionar uma fonte de dados** , selecione uma fonte de dados na lista ou clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="df3ed-154">In the **Select a data source** dialog box, select a data source from the list, or click **New**.</span></span>  
  
4.  <span data-ttu-id="df3ed-155">Se você selecionar **novo**, siga o procedimento descrito anteriormente para especificar um nome de servidor e catálogo, ou para se conectar por meio de um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="df3ed-155">If you select **New**, follow the procedure that is described earlier to specify a server and catalog name, or to connect through a Web service.</span></span>  
  
##  <a name="changing-connections"></a><a name="bkmk_change"></a><span data-ttu-id="df3ed-156">Alterando conexões</span><span class="sxs-lookup"><span data-stu-id="df3ed-156">Changing Connections</span></span>  
 <span data-ttu-id="df3ed-157">Você pode criar várias conexões na mesma planilha, mas somente uma conexão pode ficar ativa de cada vez.</span><span class="sxs-lookup"><span data-stu-id="df3ed-157">You can create multiple connections in the same worksheet, but only one connection can be active at a time.</span></span> <span data-ttu-id="df3ed-158">O nome da conexão atual é exibido no botão **conexão** .</span><span class="sxs-lookup"><span data-stu-id="df3ed-158">The name of the current connection is displayed in the **Connection** button.</span></span>  
  
 <span data-ttu-id="df3ed-159">No cliente de mineração de dados para Excel, você também pode verificar a cadeia de conexão e o status da conexão atual clicando em **rastrear** e, em seguida, clicando em **conexão atual**.</span><span class="sxs-lookup"><span data-stu-id="df3ed-159">In the Data Mining Client for Excel, you can also verify the connection string and status for the current connection by clicking **Trace** and then clicking **Current Connection**.</span></span>  
  
#### <a name="use-a-different-server-connection"></a><span data-ttu-id="df3ed-160">Usar uma conexão de servidor diferente</span><span class="sxs-lookup"><span data-stu-id="df3ed-160">Use a different server connection</span></span>  
  
1.  <span data-ttu-id="df3ed-161">Clique em **conexão**.</span><span class="sxs-lookup"><span data-stu-id="df3ed-161">Click **Connection**.</span></span>  
  
2.  <span data-ttu-id="df3ed-162">No painel **conexões Analysis Services** , selecione uma conexão na lista **outras conexões** e clique em **tornar atual**.</span><span class="sxs-lookup"><span data-stu-id="df3ed-162">In the **Analysis Services Connections** pane, select a connection from the **Other Connections** list, and click **Make Current**.</span></span>  
  
3.  <span data-ttu-id="df3ed-163">Clique em **testar conexão** para verificar se a conexão está disponível.</span><span class="sxs-lookup"><span data-stu-id="df3ed-163">Click **Test Connection** to verify that the connection is available.</span></span>  
  
 <span data-ttu-id="df3ed-164">Após a conclusão do processamento de um modelo de mineração, os resultados serão armazenados localmente, e não haverá efeito sobre os dados se você fechar a conexão com um servidor e se conectar a outro servidor.</span><span class="sxs-lookup"><span data-stu-id="df3ed-164">After a mining model has finished processing, the results are stored locally, and there is no effect on the data if you close the connection to one server and then connect to another server.</span></span> <span data-ttu-id="df3ed-165">No entanto, evite alterar as conexões ou perder a conexão quando um modelo de mineração de dados estiver sendo processado, porque isso pode corromper os dados.</span><span class="sxs-lookup"><span data-stu-id="df3ed-165">However, you should avoid changing connections or losing the connection when a data mining model is being processed, because this could corrupt data.</span></span>  
  
#### <a name="modify-an-existing-server-connection"></a><span data-ttu-id="df3ed-166">Modifique uma conexão de servidor existente</span><span class="sxs-lookup"><span data-stu-id="df3ed-166">Modify an existing server connection</span></span>  
  
1.  <span data-ttu-id="df3ed-167">Você não pode alterar uma conexão existente; se quiser se conectar a um banco de dados diferente ou a um servidor diferente, deverá criar uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="df3ed-167">You cannot modify an existing connection; if you want to connect to a different database or a different server, you should create a new connection.</span></span>  
  
2.  <span data-ttu-id="df3ed-168">Se você precisar modificar a cadeia de conexão para aumentar o tempo limite de consulta ou adicionar outros parâmetros específicos para a sua instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], uma opção é editar o arquivo .dmc, onde a cadeia de conexão está armazenada.</span><span class="sxs-lookup"><span data-stu-id="df3ed-168">If you must modify the connection string to increase the query timeout or add other parameters specific to your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], one option is to edit the .dmc file, where the connection string is stored.</span></span>  
  
     <span data-ttu-id="df3ed-169">\<drive:>O \\ \> suplemento de mineração \AppData\Local\Microsoft\Data myusername<</span><span class="sxs-lookup"><span data-stu-id="df3ed-169">\<drive:>\Users\\<myusername\>\AppData\Local\Microsoft\Data Mining Add-in</span></span>  
  
##  <a name="connecting-to-external-data-sources"></a><a name="bkmk_extconnections"></a><span data-ttu-id="df3ed-170">Conectando-se a fontes de dados externas</span><span class="sxs-lookup"><span data-stu-id="df3ed-170">Connecting to External Data Sources</span></span>  
 <span data-ttu-id="df3ed-171">Enquanto as ferramentas na faixa de medida de **análise** funcionam exclusivamente com dados no Excel, as ferramentas na faixa de informações de **mineração de dados** permitem que você se conecte diretamente a fontes de dados externas para usar como entradas para seu modelo ou para amostragem.</span><span class="sxs-lookup"><span data-stu-id="df3ed-171">Whereas the tools in the **Analyze** ribbon work exclusively with data in Excel, the tools in the **Data Mining** ribbon let you connect directly to external data sources to use as inputs for your model, or for sampling.</span></span>  
  
 <span data-ttu-id="df3ed-172">As ferramentas a seguir nesses suplementos dão suporte ao uso de dados externos para mineração de dados:</span><span class="sxs-lookup"><span data-stu-id="df3ed-172">The following tools in these add-ins support use of external data for data mining:</span></span>  
  
-   [<span data-ttu-id="df3ed-173">&#40;de dados de exemplo SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-173">Sample Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](sample-data-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="df3ed-174">Assistente de classificação &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-174">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="df3ed-175">Assistente de estimativa &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-175">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="df3ed-176">Assistente de cluster &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-176">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="df3ed-177">Assistente de previsão &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-177">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="df3ed-178">Crie &#40;de estrutura de mineração SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-178">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="df3ed-179">Gráfico de precisão &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-179">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="df3ed-180">&#40;de gráfico de ganho SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-180">Profit Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](profit-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="df3ed-181">&#40;de matrizes de classificação SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-181">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
### <a name="using-analysis-services-as-a-data-source"></a><span data-ttu-id="df3ed-182">Usando Analysis Services como uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="df3ed-182">Using Analysis Services as a Data Source</span></span>  
 <span data-ttu-id="df3ed-183">Você não pode acessar diretamente os dados armazenados em um cubo ou modelo tabular do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df3ed-183">You cannot directly access data stored in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube or tabular model.</span></span> <span data-ttu-id="df3ed-184">Em vez disso, crie uma conexão no Excel para o servidor do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e use os dados para criar um modelo.</span><span class="sxs-lookup"><span data-stu-id="df3ed-184">Instead, create a connection in Excel to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, and use the data to create a model.</span></span>  
  
### <a name="relational-data-sources"></a><span data-ttu-id="df3ed-185">Fontes de dados relacionais</span><span class="sxs-lookup"><span data-stu-id="df3ed-185">Relational Data Sources</span></span>  
 <span data-ttu-id="df3ed-186">Se quiser usar dados de uma fonte relacional como entrada para o modelo, você poderá se conectar às seguintes versões do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="df3ed-186">If you want to use data from a relational source as input to your model, you can connect to the following versions of SQL Server:</span></span>  
  
-   <span data-ttu-id="df3ed-187">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="df3ed-187">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="df3ed-188">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="df3ed-188">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="df3ed-189">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="df3ed-189">SQL Server 2012</span></span>  
  
 <span data-ttu-id="df3ed-190">Você também pode obter dados de qualquer outra fonte de dados relacional que tem suporte como uma fonte de dados pelo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df3ed-190">You can also get data from any other relational data source that is supported as a data source by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="df3ed-191">Para obter informações sobre as fontes de dados com suporte, consulte [fontes de dados em modelos multidimensionais](multidimensional-models/data-sources-in-multidimensional-models.md)</span><span class="sxs-lookup"><span data-stu-id="df3ed-191">For information about supported data sources, see [Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md)</span></span>  
  
 <span data-ttu-id="df3ed-192">Observe que os seguintes tipos de dados não podem ser usados para mineração de dados e resultarão em um erro se forem incluídos quando você criar um modelo:</span><span class="sxs-lookup"><span data-stu-id="df3ed-192">Note that the following data types cannot be used for data mining and will result in an error if included when you build a model:</span></span>  
  
-   <span data-ttu-id="df3ed-193">ntext</span><span class="sxs-lookup"><span data-stu-id="df3ed-193">ntext</span></span>  
  
-   <span data-ttu-id="df3ed-194">binary</span><span class="sxs-lookup"><span data-stu-id="df3ed-194">binary</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3ed-195">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df3ed-195">See Also</span></span>  
 [<span data-ttu-id="df3ed-196">Rastrear &#40;cliente de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="df3ed-196">Trace &#40;Data Mining Client for Excel&#41;</span></span>](trace-data-mining-client-for-excel.md)  
  
  
