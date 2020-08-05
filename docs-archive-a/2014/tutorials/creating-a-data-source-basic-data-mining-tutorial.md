---
title: Criando uma fonte de dados (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d7107c32-69ed-49a8-9b6e-32753eebf42c
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d8d5974c3685476f5d7a5751fb71bfa98384cf36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572292"
---
# <a name="creating-a-data-source-basic-data-mining-tutorial"></a><span data-ttu-id="2f5a2-102">Criando uma fonte de dados (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="2f5a2-102">Creating a Data Source (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="2f5a2-103">Uma *fonte de dados* é uma conexão de dados que é salva e gerenciada em seu projeto e implantada em seu banco de dado [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f5a2-103">A *data source* is a data connection that is saved and managed in your project and deployed to your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="2f5a2-104">A fonte de dados contém os nomes do servidor e o banco de dados em que a sua fonte de dados reside, além das demais propriedades de conexão necessárias.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-104">The data source contains the names of the server and database where your source data resides, in addition to any other required connection properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f5a2-105">O nome do banco de dados é [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f5a2-105">The name of the database is [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="2f5a2-106">Se você ainda não tiver instalado esse banco de dados, consulte a página bancos de dados de [exemplo do Microsoft SQL](https://go.microsoft.com/fwlink/?LinkId=88417) .</span><span class="sxs-lookup"><span data-stu-id="2f5a2-106">If you have not already installed this database, see the [Microsoft SQL Sample Databases](https://go.microsoft.com/fwlink/?LinkId=88417) page.</span></span>  
  
### <a name="to-create-a-data-source"></a><span data-ttu-id="2f5a2-107">Para criar uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="2f5a2-107">To create a data source</span></span>  
  
1.  <span data-ttu-id="2f5a2-108">Em **Gerenciador de soluções**, clique com o botão direito do mouse na pasta **fontes de dados** e selecione **nova fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-108">In **Solution Explorer**, right-click the **Data Sources** folder and select **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="2f5a2-109">Na página **Bem-vindo ao Assistente de Fonte de Dados** , clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-109">On the **Welcome to the Data Source Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2f5a2-110">Na página **Selecione como definir a conexão** , clique em **novo** para adicionar uma conexão ao banco de [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] dados.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-110">On the **Select how to define the connection** page, click **New** to add a connection to the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="2f5a2-111">Na lista **provedor** no **Gerenciador de conexões**, selecione **Native OLE DB Nativo\SQL servidor nativo Client 11,0**.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-111">In the **Provider** list in **Connection Manager**, select **Native OLE DB\SQL Server Native Client 11.0**.</span></span>  
  
5.  <span data-ttu-id="2f5a2-112">Na caixa **nome do servidor** , digite ou selecione o nome do servidor no qual você instalou o [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f5a2-112">In the **Server name** box, type or select the name of the server on which you installed [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span>  
  
     <span data-ttu-id="2f5a2-113">Por exemplo, digite **localhost** se o banco de dados estiver hospedado no servidor local.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-113">For example, type **localhost** if the database is hosted on the local server.</span></span>  
  
6.  <span data-ttu-id="2f5a2-114">No log no grupo **de servidores** , selecione **usar autenticação do Windows**.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-114">In the **Log onto the server** group, select **Use Windows Authentication**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2f5a2-115">Sempre que possível, os implementadores deverão usar a Autenticação do Windows, já que ela oferece um método de autenticação mais seguro do que a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-115">Whenever possible, implementers should use Windows Authentication, as it provides a more secure authentication method than SQL Server Authentication.</span></span> <span data-ttu-id="2f5a2-116">No entanto, a Autenticação do SQL Server é fornecida somente para fins de compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-116">However, SQL Server Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="2f5a2-117">Para obter mais informações sobre métodos de autenticação, consulte [mecanismo de banco de dados configuração – provisionamento de conta](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="2f5a2-117">For more information about authentication methods, see [Database Engine Configuration - Account Provisioning](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span></span>  
  
7.  <span data-ttu-id="2f5a2-118">Na lista **selecionar ou inserir nome de banco de dados** , selecione [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-118">In the **Select or enter a database name** list, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="2f5a2-119">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-119">Click **Next**.</span></span>  
  
9. <span data-ttu-id="2f5a2-120">Na página **informações sobre representação** , clique em **usar a conta de serviço**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-120">On the **Impersonation Information** page, click **Use the service account**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="2f5a2-121">Na página **concluindo o assistente** , observe que, por padrão, a fonte de dados é chamada Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-121">On the **Completing the Wizard** page, notice that, by default, the data source is named Adventure Works DW 2012.</span></span>  
  
10. <span data-ttu-id="2f5a2-122">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-122">Click **Finish**.</span></span>  
  
     <span data-ttu-id="2f5a2-123">A nova fonte de dados, Adventure Works DW 2012, aparece na pasta **fontes de dados** em Gerenciador de soluções.</span><span class="sxs-lookup"><span data-stu-id="2f5a2-123">The new data source, Adventure Works DW 2012, appears in the **Data Sources** folder in Solution Explorer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2f5a2-124">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="2f5a2-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2f5a2-125">Criando uma exibição da fonte de dados &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="2f5a2-125">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="2f5a2-126">Tarefa anterior da lição</span><span class="sxs-lookup"><span data-stu-id="2f5a2-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="2f5a2-127">Criando um projeto de Analysis Services &#40;o tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="2f5a2-127">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f5a2-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f5a2-128">See Also</span></span>  
 <span data-ttu-id="2f5a2-129">[Criar uma fonte de dados &#40;SSAS multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="2f5a2-129">[Create a Data Source &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span></span>  
 <span data-ttu-id="2f5a2-130">[Definindo uma fonte de dados](../analysis-services/lesson-1-2-defining-a-data-source.md) </span><span class="sxs-lookup"><span data-stu-id="2f5a2-130">[Defining a Data Source](../analysis-services/lesson-1-2-defining-a-data-source.md) </span></span>  
 [<span data-ttu-id="2f5a2-131">Definir opções de representação &#40;SSAS – Multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="2f5a2-131">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/set-impersonation-options-ssas-multidimensional)  
  
  
