---
title: 'Etapa 3: adicionar e configurar um gerenciador de conexões OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7b74cba-a0e5-4478-af12-3f81b9484e9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bc4c885ce6c39c72031dd3b528a769cd47ac8f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574146"
---
# <a name="step-3-adding-and-configuring-an-ole-db-connection-manager"></a><span data-ttu-id="58f8f-102">Etapa 3: Adicionar e configurar um gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="58f8f-102">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>
  <span data-ttu-id="58f8f-103">Depois de ter adicionado um gerenciador de conexões de arquivo simples para conectar-se à origem de dados, a próxima tarefa é adicionar um gerenciador de conexões OLE DB para conectar-se ao destino.</span><span class="sxs-lookup"><span data-stu-id="58f8f-103">After you have added a Flat File connection manager to connect to the data source, the next task is to add an OLE DB connection manager to connect to the destination.</span></span> <span data-ttu-id="58f8f-104">Um gerenciador de conexões OLE DB permite que um pacote extraia dados de qualquer fonte de dados compatível com OLE DB ou carregue dados nela.</span><span class="sxs-lookup"><span data-stu-id="58f8f-104">An OLE DB connection manager enables a package to extract data from or load data into any OLE DB-compliant data source.</span></span> <span data-ttu-id="58f8f-105">Usando o gerenciador de conexões OLE DB, você pode especificar o servidor, o método de autenticação e o banco de dados padrão para a conexão.</span><span class="sxs-lookup"><span data-stu-id="58f8f-105">Using the OLE DB Connection manager, you can specify the server, the authentication method, and the default database for the connection.</span></span>  
  
 <span data-ttu-id="58f8f-106">Nesta lição, você aprenderá a criar um gerenciador de conexões OLE DB que usa a Autenticação do Windows para se conectar à instância local do **AdventureWorksDB2012**.</span><span class="sxs-lookup"><span data-stu-id="58f8f-106">In this lesson, you will create an OLE DB connection manager that uses Windows Authentication to connect to the local instance of **AdventureWorksDB2012**.</span></span> <span data-ttu-id="58f8f-107">O gerenciador de conexões OLE DB que você criar também será referenciado por outros componentes que você criar posteriormente neste tutorial, como, por exemplo, a transformação Pesquisa e o destino OLE DB.</span><span class="sxs-lookup"><span data-stu-id="58f8f-107">The OLE DB connection manager that you create will also be referenced by other components that you will create later in this tutorial, such as the Lookup transformation and the OLE DB destination.</span></span>  
  
### <a name="to-add-and-configure-an-ole-db-connection-manager-to-the-ssis-package"></a><span data-ttu-id="58f8f-108">Para adicionar e configurar um Gerenciador de conexões OLE DB no pacote SSIS.</span><span class="sxs-lookup"><span data-stu-id="58f8f-108">To add and configure an OLE DB Connection Manager to the SSIS package</span></span>  
  
1.  <span data-ttu-id="58f8f-109">Clique com o botão direito do mouse em qualquer lugar da área **Gerenciadores de Conexões** e clique em **Nova Conexão OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="58f8f-109">Right-click anywhere in the **Connection Managers** area, and then click **New OLE DB Connection**.</span></span>  
  
2.  <span data-ttu-id="58f8f-110">Na caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="58f8f-110">In the **Configure OLE DB Connection Manager** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="58f8f-111">Em **Nome do servidor**, insira **localhost**.</span><span class="sxs-lookup"><span data-stu-id="58f8f-111">For **Server name**, enter **localhost**.</span></span>  
  
     <span data-ttu-id="58f8f-112">Quando você especifica localhost como o nome do servidor, o gerenciador de conexões se conecta à instância padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="58f8f-112">When you specify localhost as the server name, the connection manager connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="58f8f-113">Para usar uma instância remota do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], substitua localhost pelo nome do servidor ao qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="58f8f-113">To use a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], replace localhost with the name of the server to which you want to connect.</span></span>  
  
4.  <span data-ttu-id="58f8f-114">No grupo **Fazer logon no servidor** , verifique se a opção **Usar Autenticação do Windows** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="58f8f-114">In the **Log on to the server** group, verify that **Use Windows Authentication** is selected.</span></span>  
  
5.  <span data-ttu-id="58f8f-115">No grupo **conectar-se a um banco de dados** , na caixa **selecionar ou inserir um nome de banco de dados** , digite ou selecione `AdventureWorksDW2012` .</span><span class="sxs-lookup"><span data-stu-id="58f8f-115">In the **Connect to a database** group, in the **Select or enter a database name** box, type or select `AdventureWorksDW2012`.</span></span>  
  
6.  <span data-ttu-id="58f8f-116">Clique em **Testar Conexão** para verificar se as configurações de conexão especificadas são válidas.</span><span class="sxs-lookup"><span data-stu-id="58f8f-116">Click **Test Connection** to verify that the connection settings you have specified are valid.</span></span>  
  
7.  <span data-ttu-id="58f8f-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="58f8f-117">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="58f8f-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="58f8f-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="58f8f-119">No painel **Conexões de Dados** da caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** , verifique se a opção **localhost.AdventureWorksDW2012** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="58f8f-119">In the **Data Connections** pane of the **Configure OLE DB Connection Manager** dialog box, verify that **localhost.AdventureWorksDW2012** is selected.</span></span>  
  
10. <span data-ttu-id="58f8f-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="58f8f-120">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="58f8f-121">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="58f8f-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="58f8f-122">Etapa 4: Adicionar uma tarefa de fluxo de dados ao pacote</span><span class="sxs-lookup"><span data-stu-id="58f8f-122">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="58f8f-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58f8f-123">See Also</span></span>  
 [<span data-ttu-id="58f8f-124">Gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="58f8f-124">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
