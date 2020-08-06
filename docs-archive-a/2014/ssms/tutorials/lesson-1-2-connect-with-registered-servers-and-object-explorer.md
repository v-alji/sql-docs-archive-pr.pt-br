---
title: Conectar-se com os Servidores Registrados e com o Pesquisador de Objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: d6b3911f-68b4-4483-831b-df89d6400add
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4bc75ad7f3682765dc102064a5621cd541ccd12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678527"
---
# <a name="connect-with-registered-servers-and-object-explorer"></a><span data-ttu-id="896d8-102">Conectar com os Servidores Registrados e o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="896d8-102">Connect with Registered Servers and Object Explorer</span></span>
  <span data-ttu-id="896d8-103">Este tutorial demonstra o uso de Servidores Registrados e do Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="896d8-103">This tutorial demonstrates the use of Registered Servers and Object Explorer.</span></span>  
  
 <span data-ttu-id="896d8-104">Este tutorial usa o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="896d8-104">This tutorial uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="896d8-105">Para reforçar a segurança, os exemplos de bancos de dados não são instalados por padrão.</span><span class="sxs-lookup"><span data-stu-id="896d8-105">To help enhance security, by default, the sample databases are not installed.</span></span> <span data-ttu-id="896d8-106">Para obter mais informações, consulte [Instalando exemplos de SQL Server e bancos de dados de exemplo](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="896d8-106">For more information, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="connecting-to-servers"></a><span data-ttu-id="896d8-107">Conectando a servidores</span><span class="sxs-lookup"><span data-stu-id="896d8-107">Connecting to Servers</span></span>  
 <span data-ttu-id="896d8-108">A barra de ferramentas do componente Servidores Registrados tem botões para o [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896d8-108">The toolbar of the Registered Servers component has buttons for the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="896d8-109">Você pode registrar um ou mais desses tipos de servidor para obter um gerenciamento conveniente.</span><span class="sxs-lookup"><span data-stu-id="896d8-109">You can register one or more of these server types for convenient management.</span></span> <span data-ttu-id="896d8-110">Tente o exercício a seguir para registrar o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="896d8-110">Try the following exercise to register the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
#### <a name="to-register-the-database"></a><span data-ttu-id="896d8-111">Para registrar o banco de dados</span><span class="sxs-lookup"><span data-stu-id="896d8-111">To register the database</span></span>  
  
1.  <span data-ttu-id="896d8-112">Na barra de ferramentas Servidores Registrados, clique em **Mecanismo de Banco de Dados** , se necessário.</span><span class="sxs-lookup"><span data-stu-id="896d8-112">On the Registered Servers toolbar, click **Database Engine** if you have to.</span></span> <span data-ttu-id="896d8-113">(Já pode estar selecionado.)</span><span class="sxs-lookup"><span data-stu-id="896d8-113">(It may already be selected.)</span></span>  
  
2.  <span data-ttu-id="896d8-114">Expanda **Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="896d8-114">Expand **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="896d8-115">Clique com o botão direito do mouse em **Grupos do Servidor Local**e clique em **Novo Registro do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="896d8-115">Right-click **Local Server Groups**, and then click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="896d8-116">Na caixa de diálogo **Registro de Novo Servidor** , na caixa de texto **Nome do Servidor** , digite o nome de sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896d8-116">In the **New Server Registration** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="896d8-117">Na caixa **Nome do servidor registrado** , digite [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896d8-117">In the **Registered server name** box, type [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
6.  <span data-ttu-id="896d8-118">Na guia **Propriedades da conexão** , na lista **conectar ao banco de dados** , selecione **\<Browse server...>** .</span><span class="sxs-lookup"><span data-stu-id="896d8-118">On the **Connection Properties** tab, in the **Connect to database** list, select **\<Browse server...>**.</span></span>  
  
7.  <span data-ttu-id="896d8-119">Na caixa de diálogo **Procurar Bancos de Dados** , clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="896d8-119">In the **Browse for Databases** dialog box, click **Yes**.</span></span>  
  
8.  <span data-ttu-id="896d8-120">Na caixa de diálogo **Procurar Banco de Dados no Servidor** , selecione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="896d8-120">In the **Browse Server for Database** dialog box, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
9. <span data-ttu-id="896d8-121">Para verificar se o servidor foi registrado corretamente, clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="896d8-121">To verify that the server has been registered correctly, click **Test**.</span></span>  
  
10. <span data-ttu-id="896d8-122">Na caixa de diálogo **Novo Registro do Servidor** , clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="896d8-122">In the **New Server Registration** dialog box, click **Save**.</span></span>  
  
## <a name="connecting-with-object-explorer"></a><span data-ttu-id="896d8-123">Conectando com o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="896d8-123">Connecting with Object Explorer</span></span>  
 <span data-ttu-id="896d8-124">Da mesma forma que os Servidores Registrados, o Pesquisador de Objetos pode estabelecer conexão com o [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]e o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896d8-124">Like Registered Servers, Object Explorer can connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
#### <a name="to-connect-with-object-explorer"></a><span data-ttu-id="896d8-125">Para conectar com o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="896d8-125">To connect with Object Explorer</span></span>  
  
1.  <span data-ttu-id="896d8-126">Na barra de ferramentas do Pesquisador de Objetos, clique em **Conectar** para obter uma lista de possíveis tipos de conexão e selecione **Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="896d8-126">On the toolbar of Object Explorer, click **Connect** for a list of possible connection types, and then select **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="896d8-127">Na caixa de diálogo **Conectar ao Servidor** , na caixa de texto **Nome do Servidor** , digite o nome de sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896d8-127">In the **Connect to Server** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="896d8-128">Clique em **Opções** e explore as escolhas.</span><span class="sxs-lookup"><span data-stu-id="896d8-128">Click **Options** and explore the choices.</span></span>  
  
4.  <span data-ttu-id="896d8-129">Para conectar-se ao servidor, clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="896d8-129">To connect to the server, click **Connect**.</span></span> <span data-ttu-id="896d8-130">Se você já estiver conectado, essa ação o retornará ao Pesquisador de Objetos e definirá o foco naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="896d8-130">If you are already connected, this action just returns you to Object Explorer and sets the focus on that server.</span></span>  
  
     <span data-ttu-id="896d8-131">Com o Pesquisador de Objetos, você pode administrar a Segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, a Replicação e o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="896d8-131">With Object Explorer you can administer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Security, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, Replication, and Database Mail.</span></span> <span data-ttu-id="896d8-132">O Pesquisador de Objetos só pode administrar alguns dos recursos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e do [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896d8-132">Object Explorer can only manage some of the features of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span></span> <span data-ttu-id="896d8-133">Cada um desses componentes tem ferramentas especializadas adicionais.</span><span class="sxs-lookup"><span data-stu-id="896d8-133">Each of those components has additional specialized tools.</span></span>  
  
5.  <span data-ttu-id="896d8-134">No Pesquisador de Objetos, expanda a pasta **Bancos de Dados** e selecione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="896d8-134">In Object Explorer, expand the **Databases** folder and select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
     <span data-ttu-id="896d8-135">Observe que o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] apresenta os bancos de dados do sistema em uma pasta separada.</span><span class="sxs-lookup"><span data-stu-id="896d8-135">Notice that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] presents the system databases in a separate folder.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="896d8-136">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="896d8-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="896d8-137">Alterar o layout do ambiente</span><span class="sxs-lookup"><span data-stu-id="896d8-137">Change the Environment Layout</span></span>](lesson-1-3-change-the-environment-layout.md)  
  
  
