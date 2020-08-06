---
title: Como criar e editar um serviço CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1b3d47a5-dc89-482d-bbc7-fff04f194c43
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d90534b475901b08fcd2e09acdc0f7976f0fb6e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678925"
---
# <a name="how-to-create-and-edit-a-cdc-service"></a><span data-ttu-id="ba6ba-102">Como criar e editar um Serviço CDC</span><span class="sxs-lookup"><span data-stu-id="ba6ba-102">How to Create and Edit a CDC Service</span></span>
  <span data-ttu-id="ba6ba-103">Estes procedimentos descrevem como criar e editar um novo Serviço Oracle CDC a partir do Console de Configuração do Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-103">These procedures describe how to create and edit a new Oracle CDC Service from the CDC Service Configuration Console.</span></span>  
  
 <span data-ttu-id="ba6ba-104">Este procedimento exige um usuário do Windows com privilégios de administrador no computador onde o serviço Oracle CDC está configurado.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-104">This procedure requires a Windows user with administrator privileges on the computer where the Oracle CDC service is configured.</span></span>  
  
### <a name="to-create-a-new-cdc-service"></a><span data-ttu-id="ba6ba-105">Para criar um novo serviço CDC</span><span class="sxs-lookup"><span data-stu-id="ba6ba-105">To create a new CDC service</span></span>  
  
1.  <span data-ttu-id="ba6ba-106">No menu **Iniciar** , selecione **Configuração do Serviço CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-106">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="ba6ba-107">No painel esquerdo, clique com o botão direito em Serviços Locais CDC e selecione Novo Serviço</span><span class="sxs-lookup"><span data-stu-id="ba6ba-107">From the left pane, right click Local CDC Services and select New Service</span></span>  
  
     <span data-ttu-id="ba6ba-108">Você também pode clicar em **Novo Serviço** no painel **Ações** .</span><span class="sxs-lookup"><span data-stu-id="ba6ba-108">You can also click **New Service** from the **Actions** pane.</span></span>  
  
3.  <span data-ttu-id="ba6ba-109">Digite ou insira as informações necessárias na caixa de diálogo Novo Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-109">Type or enter the required information in the New Oracle CDC Service dialog box.</span></span> <span data-ttu-id="ba6ba-110">Consulte [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) para obter informações sobre como inserir informações na caixa de diálogo Novo Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-110">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the New Oracle CDC Service dialog box.</span></span>  
  
     <span data-ttu-id="ba6ba-111">O logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornecido na caixa de diálogo Novo Serviço Oracle CDC é usado pelo Serviço Oracle CDC quando o serviço é executado.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login provided in the New Oracle CDC Service dialog box is used by the Oracle CDC Service when the service runs.</span></span> <span data-ttu-id="ba6ba-112">Esse logon somente precisa ser um membro da função pública de servidor fixa, nenhum outro privilégio será necessário.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-112">This login only needs to be a member of the public fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="ba6ba-113">Quando novas Instâncias do Oracle CDC são adicionadas, esse logon recebe acesso **db_owner** aos bancos de dados CDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associados.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-113">Once new Oracle CDC Instances are added, that login receives **db_owner** access to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC databases.</span></span>  
  
4.  <span data-ttu-id="ba6ba-114">Quando você terminar de inserir as informações necessárias, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-114">When you finish entering the required information, click **OK**.</span></span>  
  
     <span data-ttu-id="ba6ba-115">Para criar a definição de Serviço do Windows do Oracle CDC, o programa precisa de acesso de atualização ao banco de dados MSXDBCDC na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associada.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-115">To create the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="ba6ba-116">Quando você clica em **OK**, uma caixa de diálogo solicita que o usuário insira um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com um acesso de atualização para o banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-116">When you click **OK**, a dialog box prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
     <span data-ttu-id="ba6ba-117">Para obter informações sobre os dados que você deverá digitar na caixa de diálogo Conecte-se ao SQL Server, consulte [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba6ba-117">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="ba6ba-118">Clique em **OK** para fechar a caixa de diálogo Novo Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-118">Click **OK** to close the New Oracle CDC Service dialog box.</span></span>  
  
### <a name="to-edit-a-cdc-service"></a><span data-ttu-id="ba6ba-119">Para editar um serviço CDC</span><span class="sxs-lookup"><span data-stu-id="ba6ba-119">To edit a CDC service</span></span>  
  
1.  <span data-ttu-id="ba6ba-120">No menu **Iniciar** , selecione **Configuração do Serviço CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-120">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="ba6ba-121">No painel esquerdo, selecione **Serviços Locais CDC** e clique com o botão direito do mouse no serviço local que você quer editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-121">From the left pane, select **Local CDC Services** then right-click the local service you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="ba6ba-122">Você pode selecionar o serviço com o qual você está trabalhando no meio e, no painel **Ações** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-122">You can also select the service you are working with in the middle and then from the **Actions** pane, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ba6ba-123">Digite ou insira as informações necessárias na caixa de diálogo Propriedades do Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-123">Type or enter the required information in the CDC Service Properties dialog box.</span></span> <span data-ttu-id="ba6ba-124">Consulte [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) para obter informações sobre como inserir informações na caixa de diálogo Propriedades do Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-124">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the CDC Service Properties dialog box.</span></span>  
  
4.  <span data-ttu-id="ba6ba-125">Quando você terminar de inserir as informações necessárias, clique em **OK**e a caixa de diálogo Conecte-se ao SQL Server será aberta.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-125">When you finish entering the required information, Click **OK**, the Connect to SQL Server dialog box opens.</span></span>  
  
     <span data-ttu-id="ba6ba-126">Quando um logon sem permissão de gravação para o banco de dados MSXDBDCDC tenta criar uma nova instância Oracle CDC, uma mensagem de erro é exibida.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-126">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="ba6ba-127">Clique em **OK** nessa caixa de diálogo para exibir a caixa de diálogo Conecte-se ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-127">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span> <span data-ttu-id="ba6ba-128">Nesta caixa de diálogo, você deve inserir as credenciais para um logon que tem permissão de gravação ao banco de dados MSXDBCDC, como a função de banco de dados **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="ba6ba-128">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role.</span></span>  
  
     <span data-ttu-id="ba6ba-129">Para obter informações sobre os dados que você deverá digitar na caixa de diálogo Conecte-se ao SQL Server, consulte [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba6ba-129">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="ba6ba-130">Clique em **OK** na caixa de diálogo Conectar ao Oracle.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-130">Click **OK** in the Connect to Oracle dialog box.</span></span> <span data-ttu-id="ba6ba-131">Ambas as caixas de diálogo fecham e o serviço é atualizado e registrado.</span><span class="sxs-lookup"><span data-stu-id="ba6ba-131">Both dialog boxes close and the service is updated and registered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6ba-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba6ba-132">See Also</span></span>  
 <span data-ttu-id="ba6ba-133">[Change Data Capture Designer para Oracle da Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="ba6ba-133">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="ba6ba-134">Criar e editar um serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="ba6ba-134">Create and Edit an Oracle CDC Service</span></span>](create-and-edit-an-oracle-cdc-service.md)  
  
  
