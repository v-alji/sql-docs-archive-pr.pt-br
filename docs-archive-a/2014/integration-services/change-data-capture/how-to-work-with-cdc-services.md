---
title: Como trabalhar com os serviços CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db5c718a-6e7f-48ec-82a3-9d5b131716e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cfb5a0ed0e9ded8e0be118deb3c819626448896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572641"
---
# <a name="how-to-work-with-cdc-services"></a><span data-ttu-id="09a7b-102">Como trabalhar com os serviços CDC</span><span class="sxs-lookup"><span data-stu-id="09a7b-102">How to Work with CDC Services</span></span>
  <span data-ttu-id="09a7b-103">Este procedimento descreve como usar o Console de Configuração do Serviço CDC para preparar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para trabalhar com os Serviços Oracle CDC e criar um novo serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="09a7b-103">This procedure describes how to use the CDC Service Configuration Console to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to work with Oracle CDC Services and to create a new CDC service.</span></span>  
  
### <a name="to-work-with-cdc-services"></a><span data-ttu-id="09a7b-104">Para trabalhar com serviços CDC</span><span class="sxs-lookup"><span data-stu-id="09a7b-104">To work with CDC services</span></span>  
  
1.  <span data-ttu-id="09a7b-105">No menu **Iniciar** , selecione **Configuração do Serviço CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="09a7b-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="09a7b-106">No painel esquerdo, **Serviços Locais CDC** (o nível raiz).</span><span class="sxs-lookup"><span data-stu-id="09a7b-106">From the left pane, select **Local CDC Services** (the root level).</span></span>  
  
3.  <span data-ttu-id="09a7b-107">Execute uma das seguintes tarefas ou ambas:</span><span class="sxs-lookup"><span data-stu-id="09a7b-107">You carry out the one or both of the following tasks:</span></span>  
  
    -   <span data-ttu-id="09a7b-108">**Preparar SQL Server**</span><span class="sxs-lookup"><span data-stu-id="09a7b-108">**Prepare SQL Server**</span></span>  
  
         <span data-ttu-id="09a7b-109">Selecione esta opção no painel **Ações** no lado direito do Console de Configuração do Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="09a7b-109">Select this option from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="09a7b-110">Você também pode clicar com o botão direito do mouse em **Local CDC Services (Serviços Locais de CDC)** e selecionar **Prepare SQL Server (Preparar SQL Server)** .</span><span class="sxs-lookup"><span data-stu-id="09a7b-110">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
         <span data-ttu-id="09a7b-111">A caixa de diálogo Preparando a Instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para Oracle CDC é aberta.</span><span class="sxs-lookup"><span data-stu-id="09a7b-111">The Preparing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance for Oracle CDC dialog box opens.</span></span>  
  
         <span data-ttu-id="09a7b-112">Para preparar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para os serviços Oracle CDC, o logon deve ter um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com a função de servidor fixa `dbcreator` .</span><span class="sxs-lookup"><span data-stu-id="09a7b-112">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC services, the login must have a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with the `dbcreator` fixed server role.</span></span> <span data-ttu-id="09a7b-113">Este logon é usado para criar o banco de dados MSXDBCDC necessário para adicionar os Serviços Oracle CDC e, posteriormente, Instâncias Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="09a7b-113">This login is used to create the MSXDBCDC database that is required for adding Oracle CDC Services and, later on, Oracle CDC Instances.</span></span>  
  
         <span data-ttu-id="09a7b-114">Para obter informações sobre como usar essa caixa de diálogo, consulte [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="09a7b-114">For information on how to use this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span> <span data-ttu-id="09a7b-115">Para obter informações sobre como habilitar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para CDC, consulte [Como preparar o SQL Server para CDC](how-to-prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="09a7b-115">For information on how to enable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for CDC, see [How to Prepare SQL Server for CDC](how-to-prepare-sql-server-for-cdc.md).</span></span>  
  
    -   <span data-ttu-id="09a7b-116">**Criar um novo serviço CDC**</span><span class="sxs-lookup"><span data-stu-id="09a7b-116">**Create a new CDC service**</span></span>  
  
         <span data-ttu-id="09a7b-117">Clique em **Novo Serviço** no painel **Ações** no lado direito do Console de Configuração do Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="09a7b-117">Click **New Service** from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="09a7b-118">Você também pode clicar com o botão direito do mouse em **Serviços Locais de CDC** e selecionar **Novo Serviço**.</span><span class="sxs-lookup"><span data-stu-id="09a7b-118">You can also right-Click **Local CDC Services** and select **New Service**.</span></span>  
  
         <span data-ttu-id="09a7b-119">O caixa de diálogo Novo Serviço do Oracle CDC é aberta.</span><span class="sxs-lookup"><span data-stu-id="09a7b-119">The New Oracle CDC Service dialog box opens.</span></span>  
  
         <span data-ttu-id="09a7b-120">Para obter informações sobre como usar essa caixa de diálogo, consulte [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="09a7b-120">For information on how to use this dialog box, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span></span> <span data-ttu-id="09a7b-121">Para obter informações sobre como criar ou editar um serviço CDC, consulte [Como criar e editar um Serviço CDC](how-to-create-and-edit-a-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="09a7b-121">For information on how to create or edit a CDC service, see [How to Create and Edit a CDC Service](how-to-create-and-edit-a-cdc-service.md).</span></span>  
  
         <span data-ttu-id="09a7b-122">O logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado pelo Serviço Oracle CDC somente precisa ser um membro da função `public` de servidor fixa, nenhum outro privilégio será necessário.</span><span class="sxs-lookup"><span data-stu-id="09a7b-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Oracle CDC Service only needs to be a member of the `public` fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="09a7b-123">Porém, para criar o Serviço Oracle CDC, o logon deve ter permissão de gravação no banco de dados MSXDBCDC, por exemplo, a função de banco de dados **db_owner** deve ser atribuída ao logon.</span><span class="sxs-lookup"><span data-stu-id="09a7b-123">However, to create the Oracle CDC Service, the login must have write permission to the MSXDBCDC database, for example the **db_owner** database role must be assigned to the login.</span></span> <span data-ttu-id="09a7b-124">Quando um logon sem permissão de gravação para o banco de dados MSXDBDCDC tenta criar uma nova instância Oracle CDC, uma mensagem de erro é exibida.</span><span class="sxs-lookup"><span data-stu-id="09a7b-124">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="09a7b-125">Clique em **OK** nessa caixa de diálogo para exibir a caixa de diálogo Conecte-se ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09a7b-125">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span>  
  
         <span data-ttu-id="09a7b-126">Para obter informações sobre como inserir as credenciais para um logon que tem permissão de gravação ao banco de dados MSXDBCDC, como a função de banco de dados **db_owner** , consulte [Criar e editar um serviço Oracle CDC](create-and-edit-an-oracle-cdc-service.md) e [Conexão com o SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="09a7b-126">For information on how to enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) and [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a7b-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="09a7b-127">See Also</span></span>  
 [<span data-ttu-id="09a7b-128">Trabalhar com serviços CDC</span><span class="sxs-lookup"><span data-stu-id="09a7b-128">Work with CDC Services</span></span>](work-with-cdc-services.md)  
  
  
